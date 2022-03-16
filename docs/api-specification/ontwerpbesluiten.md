# Ontwerpbesluiten

## Event attributen

### Overzicht

Alle attributen volgen de [GOV NL profile for Cloud Events](https://vng-realisatie.github.io/NL-GOV-profile-for-CloudEvents/) specificatie tenzij expliciet is aangegeven dat er een aanvulling of afwijking is. 

Attribuut           | Opmerkingen
| :--- | :--- 
id                  | Formaat MOET UUID zijn.
source              | Formaat MOET URN zijn.
specversion         | De OAS specificatie heeft al een versie numnmer. De Cloud Events versie zou afgeleid kunnen worden uit de beschrijving van de OAS. Om compatible te zijn met de Cloud Events berichtstandaard is besloten het `specversion` attribuut toch expliciet als attribuut op te nemen.
type                | -
datacontenttype     | Value MUST be application/+json
dataschema          | -
~~subject~~         | Not allowed !
time                | -
dataref             | This Cloud Events extension is allowed.
sequence            | This Cloud Events extension is allowed.
sequencetype        | This Cloud Events extension is allowed.
data                | -
data_base64         | As specified in the _JSON Event Format for CloudEvents_.
yana.domain         | See explanation below.
yana.subscriptionId | See explanation below.

### yana.domain

This is an optional attribute to specify the domain of the events.
Example: A system might offer functionality for case handling and for document handling. In such a situation a single source might offer events within both domains: cases and documents.

### yana.subscriptionId

Referentie naar de subscription op basis waarvan de notificatie doorgestuurd is. (Ofwel het door de notificatie component ontvangen event voldeed aan de criteria van deze subscription).

