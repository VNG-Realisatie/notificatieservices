# Beschrijving gedrag van API

## events.post

- Het binnengekomen event wordt opgeslagen.
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

In het afleveren kunnen naar eigen inzicht zekerheden rond de aflevering ingebouwd worden. Bijvoorbeeld herhaling van aflevering indien een node tijdelijk niet beschikbaar is. En inzet van deadletter queue's als een node bij herhaling niet bereikbaar is.

### Beoordelen filtercriteria

Een subscription kent vier attributen voor filtering: `source`, `domain`, `types` en `filters`. De attributen `source` en `domain` kunnen 1 waarde bevatten. Het attribuut `types` kan een array van typen bevatten. Daarbij voldoet het event als het een type heeft dat in deze array voorkomt. Het `filters` attribuut kan een geneste logische structuur bevatten (nadere toelichting volgt).

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

De attributen `source`, `domain` en `types` zijn eigenlijk niet nodig. De filters die met deze attributen te maken zijn kunnen namelijk ook met behulp van het filters attribuut uitgedrukt worden.

**TODO** hiervan moet nog een voorbeeld uitgewerkt worden. 

## subscriptions.post

**TODO** validatie van sink beschrijven (conform CE webhooks voorstel).
