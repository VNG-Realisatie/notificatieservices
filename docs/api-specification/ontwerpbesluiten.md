# Ontwerpbesluiten

## GOV NL profile for CloudEvents (berichtstandaard)

### Events resource, overzicht van attributen

Alle attributen volgen de [GOV NL profile for CloudEvents](https://vng-realisatie.github.io/NL-GOV-profile-for-CloudEvents/) specificatie tenzij expliciet is aangegeven dat er een aanvulling of afwijking is. 

Attribuut           | Opmerkingen
| :--- | :--- 
id                  | Formaat MOET UUID zijn.
source              | Formaat MOET URN zijn.
specversion         | De OAS specificatie heeft al een versie numnmer. De CloudEvents versie zou afgeleid kunnen worden uit de beschrijving van de OAS. Om compatible te zijn met de CloudEvents berichtstandaard is besloten `specversion` toch expliciet op te nemen.
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

### events.yana.domain

Optioneel attribuut. Kan opgenomen worden om het domein waartoe events behoren aan te geven.

Voorbeeld: Conceptueel is besloten om zaken en documenten van elkaar te scheiden. Beiden vormen een apart domein. Er zijn zaaksystemen en documentsystemen. Het kan ook zijn dat een systeem functionaliteit voor beiden aanbied. In die situatie biedt een systeem (source) events over twee domeinen.

### events.yana.subscriptionId

Referentie naar de subscription op basis waarvan de notificatie doorgestuurd is. (Ofwel het door de notificatie component ontvangen event voldeed aan de criteria van deze subscription).

### events.data

Er is besloten om geen onderverdeling aan te brengen binnen het data attribuut. Indeling hiervan wordt overgelaten aan de verschillende domeinen.
(Achtergrond: Er is een discussie geweest of het zinvol zou zijn om binnen het data attribuut onderscheid te maken tussen identificerende gegevens en overige gegevens over een gebeurtenis).

## JSON Event Format for CloudEvents

Conform handreiking in GOV NL profile for CloudEvents.
Aanscherping:
- The _GOV NL profile for CloudEvents JSONSchema_ for the spec can be used to validate events in JSON.
- JSON Batch Format is niet toegestaan.

## HTTP Protocol Binding for CloudEvents

Conform handreiking in GOV NL profile for CloudEvents

Een aantal variaties is niet toegestaan. Om deze expliciet aan te geven zijn is de tekst uit de handreiking integraal overgenomen en zijn niet toegestane variaties doorgehaald.

Aanscherping:
- Event should be transferred using the YANA notifications_post operation.
  - ~~Events can be transferred with all standard or application-defined HTTP request methods that support payload body transfers. Events can be also be transferred in HTTP responses and with all HTTP status codes that permit payload body transfers.~~
- Only the structured mode is allowed.
  - structured (required): HTTP message body contains both event data and metadata attributes; an appropriate event format is used (non-batching) JSON is the only event format that MUST be supported)
  - ~~batched (optional): HTTP message body contains event data and metadata attributes from multiple events; an appropriate event format is used.~~
  - ~~binary (required): HTTP message body contains event data as-is; event attributes mapped to HTTP-headers; HTTP Content-Type header declares the media type.~~
- Received Content-Type header value is application/cloudevents+json
  - ~~application/cloudevents(+xxxx): structured mode (xxx denotes the used event format)~~
  - ~~application/cloudevents-batch: batched mode~~
  - ~~Otherwise: binary mode (Content-Type header declares the media type.)~~
- Structured content mode:
  - The HTTP message body MUST contain both event data and metadata attributes.
  - The HTTP Content-Type header MUST be set to the media type of an event format (E.g. application/cloudevents+json; charset=UTF-8)
  - The chosen event format defines how all attributes, and data, are represented in the HTTP message body.
  - ~~Implementations MAY include the same HTTP headers as defined for the binary mode (E.g. ce-id).~~
- Batched content mode: Niet toegestaan. Pas toestaan als er use cases voor zijn.
- Binary content mode: Niet toegestaan. Pas toestaan als er use cases voor zijn.


