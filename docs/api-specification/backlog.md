# Backlog

## Overzicht

## Algemeen / Alle API's

Naam | Aard | Korte beschrijving | Prio
| :--- | :--- | :--- | :---
CE statuscodes | Afmaken | Uitzoeken wat CE zegt over http statuscodes (zie toelichting) | Must
Media type in header | Afmaken | Uitzoeken of media type application/cloudevents+json in http header opgenomen kan worden | Must
Charset header | Afmaken | Uitzoeken of charset=UTF-8 in http header opgenomen kan worden | Must
Attribuut beschrijvingen | Keuze | Verwijzen we naar GOV NL profile of nemen we integrale tekst op? | Must
Autorisatie | Afmaken | Autorisatie aspecten goed verwerken in OAS | Must
Publicatie | Afmaken | Publicatie op finale lokatie | Must

### Toelichting: CE Statuscodes
Resources:
- https://github.com/cloudevents/spec/tree/main
- https://github.com/cloudevents/spec/tree/main/cloudevents/bindings
- Slide uit 6e bijeenkomst berichtenwerkgroep (Titel: CloudEvents HTTP 1.1 Web Hooks for Event Delivery - Version 1.0.1)
- Webhooks specificatie (in 1.0.1 versie van CE)

## Notification API

Naam | Aard | Korte beschrijving | Prio
| :--- | :--- | :--- | :---
Source format | Keuze | Waarom is Source in GOV NL profile niet 'MUST be URN'? | Should
Json schema GOV NL | Afmaken | Json schema van CE moet aangepast worden voor GOV NL profile | Should
Pull | Uitbreiding | Implementeren van GET op Events resource | Could

## Subscription API

Naam | Aard | Korte beschrijving | Prio
| :--- | :--- | :--- | :---
Conceptueel | Afmaken | Abonneren uitwerken vanuit enkele veel voorkomende scenario's | Could
Operaties | Afmaken | Welke operaties zijn zinvol/gewenst | Could

## Catalog API

Naam | Aard | Korte beschrijving | Prio
| :--- | :--- | :--- | :---
Conceptueel | Afmaken | Hoe zinvol is deze API? Is een tekstuele beschrijving voorlopig niet voldoende? | Should
Conceptueel | Afmaken | Bij welk detailniveau trek je de grens? | Should

