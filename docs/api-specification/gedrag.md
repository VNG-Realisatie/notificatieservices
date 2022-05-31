# Beschrijving gedrag van API

## events.post

- Het binnengekomen event wordt opgeslagen. (Mag na doorsturen verwijderd worden).
- Direct na het opslaan wordt statuscode `200` geretourneerd.

Zie _processen in de notificatie component_ voor de verdere verwerking van het event.

## Processen in de notificatie component

In hoofdlijnen worden de volgende stappen uitgevoerd:
1. Bepalen welke subscriptions in aanmerking komen om het binnengekomen event te ontvangen
2. Event klaarmaken voor aflevering
3. Afleveren van event

In de implementatie kunnen deze stappen mogelijk los van elkaar/deels parallel uitgevoerd worden. Hierbij is het belangrijk dat events altijd op volgorde van binnenkomst bij een afnemer afgeleverd worden.

De drie stappen worden hieronder stuk voor stuk beschreven:

### 1 Bepalen relevante subscriptions

- Alle subscriptions worden langsgelopen
- Per subscription wordt gekeken of het event voldoet aan de opgegeven filtercriteria (zie specificatie _beoordelen filtercriteria_)
- Als een event voldoet kan dit event klaargemaakt worden voor aflevering (stap 2)

### 2 Event klaarmaken voor aflevering

- Maak een copy van het event
- Vul in het attribuut `subscription` het id van de subscription van de afnemer in
- Vul in het attribuut `subscriberReference` de subscriber reference van de subscription van de afnemer in. Is er in de subscription geen subscriber reference opgenomen, maak het attribuut dan leeg.
- Het event kan nu afgeleverd worden bij de afnemer (Stap 3)

### 3 Event afleveren

- Het event wordt afgeleverd door een POST te doen op het door de afnemer opgegeven endpoint. Dit endpoint is te vinden in het `sink` attribute van de subscription.
- Als de afnemer in de protocolSettings http headerattributes heeft opgenomen dan moeten deze worden overgenomen in de POST

In het afleveren kunnen naar eigen inzicht zekerheden rond de aflevering ingebouwd worden. Bijvoorbeeld herhaling van aflevering indien een node tijdelijk niet beschikbaar is. En inzet van deadletter queue's als een node bij herhaling niet bereikbaar is. Et cetera.

### Beoordelen filtercriteria

Een subscription kent vier attributen voor filtering: `source`, `domain`, `types` en `filters`. De attributen `source` en `domain` kunnen 1 waarde bevatten. Het attribuut `types` kan een array van typen bevatten. Daarbij voldoet het event als het een type heeft dat in deze array voorkomt. Het `filters` attribuut kan een geneste logische structuur bevatten (zie specificatie _Toelichting subscription.filters attribuut_).

Regels:
- Een event mag pas doorgestuurd worden als aan de criteria van al deze filterattributen voldaan is.
- Geen van de attributen is verplicht.
  - Als geen enkel attribuut is ingevuld voldoet ieder event
  - Als bijvoorbeeld alleen `domain` en `types` zijn ingevuld voldoet een event als het domain overeenkomt en het typen voorkomt in de opgegeven lijst met typen.

De werking is het meest eenvoudig te illustreren aan de hand van een voorbeeld. Stel een afnemer wil alleen events ontvangen uit het 'personen' domein en dan alleen de events van het type 'persoon_verhuisd' en 'persoon_overleden'. Dit filter kan als volgt opgegeven worden:

`{
	"domain": "personen",
	"types": [
		"persoon_verhuisd",
		"persoon_overleden"
	]
}`

als logische expressie ziet dit filer er alsvolgt uit:

`(domain = "persoon") AND ( (type = "persoon_verhuisd") OR (type = "persoon_overleden"))`

### Het `filters` attribuut

De attributen `source`, `domain` en `types` zijn eigenlijk niet nodig. De filters die met deze attributen te maken zijn kunnen namelijk ook met behulp van het filters attribuut uitgedrukt worden. Via het filters attribuut kan een logische espressie doorgegeven worden. Om dit te illustreren is hieronder een voorbeeld uitgewerkt:

Stel we alleen events ontvangen die:
of afkomstig zijn uit het zaken domein en dan alleen als een status is gewijzigd of een zaak gesloten is,
of afkomstig zijn uit het documenten domein waarbij ons beperken tot vertrouwelijke documenten.

Als logische expressie ziet dit criterium er alsvolgt uit:

```
(
  domain = "nl.vng.zaken" 
  and 
  (
    type = "nl.vng.zaken.status_gewijzigd" 
    or 
    type = "nl.vng.zaken.zaak_gesloten"
  )
)

or 

(
  domain = "nl.vng.documenten" 
  and 
  vertrouwelijkheid = "normaal"
)
```

In deze vorm is het voor mensen redelijk leesbaar. Voor executie door software is een andere structurering echter handiger. Daarbij wordt eerst de operator opgegeven (AND, OR...) en dan de operanden. (Zie [Polish Notation](https://en.wikipedia.org/wiki/Polish_notation))

De expressie komt er, zonder allerlei haakjes maar met zorgvuldig inspringen, alsvolgt uit te zien:

```
Any
  All
    Equals
      Attribute = "domain"
      Value = "nl.vng.zaken"
    Any
      Equals
        Attribute = "type" 
        Value = "nl.vng.zaken.status_gewijzigd"
      Equals
        Attribute = "type"
        Value = "nl.vng.zaken.zaak_gesloten"
  All
    Equals
      Attribute = "domain"
      Value = "nl.vng.documenten"
    Equals
      Attribute = "vertrouwelijkheid"
      Value = "normaal"
```

vertaald naar een Json structuur krijgen we vervolgens:

```json
{
    "id": "....",
    "filters": [
        {
            "any": [
                {
                    "all": [
                        {
                            "exact": {
                                "attribute": "domain",
                                "value": "nl.vng.zaken"
                            }
                        },
                        {
                            "any": [
                                {
                                    "exact": {
                                        "attribute": "domain",
                                        "value": "nl.vng.zaken"
                                    }
                                },
                                {
                                    "exact": {
                                        "attribute": "type",
                                        "value": "nl.vng.zaken.zaak_gesloten"
                                    }
                                }
                            ]
                        }
                    ]
                },
                {
                    "all": [
                        {
                            "exact": {
                                "attribute": "domain",
                                "value": "nl.vng.zaken"
                            }
                        },
                        {
                            "exact": {
                                "attribute": "type",
                                "value": "nl.vng.zaken.zaak_gesloten"
                            }
                        }
                    ]
                }
            ]
        }
    ]
}
```
In deze laatste vorm zal de expressie aangeleverd moeten worden.

Waarschijnlijk is deze vorm door de CE werkgroep gekozen omdat de expressie in deze vorm direct uit te voeren is (en niet eerst geparseerd hoeft te worden). Het zou wel bijzonder handig zijn als er iets van een hulpmiddel zou komen waarmee logische expressie omgezet zouden kunnen worden in dit soort json structuren.

## subscriptions.post

**TODO** validatie van sink beschrijven (conform CE webhooks voorstel).
