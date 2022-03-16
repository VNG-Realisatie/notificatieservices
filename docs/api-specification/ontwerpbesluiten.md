# Ontwerpbesluiten

## Event attributen

### Overzicht

Alle attributen volgen de [GOV NL profile for Cloud Events](https://vng-realisatie.github.io/NL-GOV-profile-for-CloudEvents/) specificatie tenzij expliciet is aangegeven dat er een aanvulling of afwijking is. 

Attribuut           | Opmerkingen
| :--- | :--- 
id                  | Formaat MOET UUID zijn.
source              | Formaat MOET URN zijn.
specversion         | De OAS specificatie heeft al een versie numnmer. De Cloud Events versie zou afgeleid kunnen worden uit de beschrijving van de OAS. Om compatible te zijn met de Cloud Events berichtstandaard is besloten `specversion` toch expliciet op te nemen.
type                | -
datacontenttype     | Waarde MOET 'application/json' zijn.
dataschema          | -
~~subject~~         | Niet toegestaan.
time                | -
dataref             | Deze Cloud Events extensie is toegestaan.
sequence            | Deze Cloud Events extensie is toegestaan.
sequencetype        | Deze Cloud Events extensie is toegestaan.
data                | -
data_base64         | Zoals gespecificeerd in the _JSON Event Format for CloudEvents_.
yana.domain         | Toelichting volgt na tabel.
yana.subscriptionId | Toelichting volgt na tabel.

### yana.domain

Optioneel attribuut. Kan opgenomen worden om het domein waartoe events behoren aan te geven.

Voorbeeld: Conceptueel is besloten om zaken en documenten van elkaar te scheiden. Beiden vormen een apart domein. Er zijn zaaksystemen en documentsystemen. Het kan ook zijn dat een systeem functionaliteit voor beiden aanbied. In die situatie biedt een systeem (source) events over twee domeinen.

### yana.subscriptionId

Referentie naar de subscription op basis waarvan de notificatie doorgestuurd is. (Ofwel het door de notificatie component ontvangen event voldeed aan de criteria van deze subscription).

