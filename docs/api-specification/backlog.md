# Backlog

Hieronder zijn alleen werkzaamheden opgenomen om te komen tot een eerste release candidate.

## Afmaken OAS

Naam | Aard | Korte beschrijving | Prio
| :--- | :--- | :--- | :---
_CE statuscodes_ | Afmaken | Uitzoeken wat CE zegt over http statuscodes (zie toelichting) | Must
_Media type in header_ | Afmaken | Uitzoeken of media type application/cloudevents+json in http header opgenomen kan worden | Must
_Charset header_ | Afmaken | Uitzoeken of charset=UTF-8 in http header opgenomen kan worden. [Referentie CE spec](https://github.com/cloudevents/spec/blob/v1.0.1/http-protocol-binding.md) | Must
Filters correct? | Controle | Is filters attribuut in de subscriptions resource goed gedeclareerd. Dit attribuut is recursief. In de oorspronkelijke spec van CE stond bij ieder subtype van filter steeds: $ref: "#/components/schemas/Filter". Dit is weggehaald. Achteraf was deze constructie mogelijk opgenomen om een oneindige loop in software die de OAS leest te voorkomen. Mogelijk dus toch weer opnemen in de specificatie. | Must
Autorisatie | Afmaken | Autorisatie aspecten goed verwerken in OAS | Must

### Toelichting bij issue van CE Statuscodes
Resources:
- https://github.com/cloudevents/spec/tree/main
- https://github.com/cloudevents/spec/tree/main/cloudevents/bindings
- Slide uit 6e bijeenkomst berichtenwerkgroep (Titel: CloudEvents HTTP 1.1 Web Hooks for Event Delivery - Version 1.0.1)
- Webhooks specificatie (in 1.0.1 versie van CE)

## Aanvullende specificaties / documentatie

Naam | Aard | Korte beschrijving | Prio
| :--- | :--- | :--- | :---
Gedrag beschrijven | Schrijven | Gedrag van de API, voor zover niet duidelijk uit OAS/triviaal, beschrijven. | Must
Verificatie sink | Keuze | Wat willen we hierbij overnemen van de CloudEvents draft? Tekst is al opgenomen in onderdeel ontwerpbesluiten en kan daar direct aangepast worden. | Should
Attribuut beschrijvingen | Schrijven | Uitbreiden en controleren attribuut beschrijvingen. Verwijzen we naar GOV NL profile of nemen we integrale tekst op? | Should
Filters beschrijven | Schrijven | Beschrijven hoe filters werken | Should
Scenario's gebruik abonneren | Schrijven | Abonneren uitwerken vanuit enkele veel voorkomende scenario's | Could
Mapping ZGW acties | Schrijven | Patroon voor mapping van de op https://github.com/vng-Realisatie/zaken-api/blob/1.2.0/src/notificaties.md genoemd acties beschrijven.

## Potentiele wijzigingen aan GOV NL profile for CloudEvents
- Waarom is Source in GOV NL profile niet 'MUST be URN'? 

## Na eerste release candidate
Beknopt beschreven en nog niet geprioriteerd.
- Json schema van CE moet aangepast worden voor GOV NL profile
- Pull specificeren voor de events resource (?)
- Publicatie op juiste lokatie en in juiste template.

