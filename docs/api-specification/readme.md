# YANA - Yet Another Notification API

Dit is een tijdelijke locatie om te kunnen werken aan API-specificatie voor een generieke notificatiecomponent.
De API-specificatie is work in progress. _Alles kan nog op ieder moment wijzigen!_

## Quick reference: OAS3 Specificaties

Nieuwe geconsolideerde versie: (Catalogus beperkt tot domain en filterAttributes)
[ReDoc](http://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/VNG-Realisatie/notificatieservices/main/docs/api-specification/Notifications.yaml)

Onderdeel | Links
| :--- | :---
YANA Notification API | [ReDoc](http://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/VNG-Realisatie/notificatieservices/main/docs/api-specification/YANA_Notification_API.yaml), [Swagger](https://petstore.swagger.io/?url=https://raw.githubusercontent.com/VNG-Realisatie/notificatieservices/main/docs/api-specification/YANA_Notification_API.yaml) of [YAML](https://raw.githubusercontent.com/VNG-Realisatie/notificatieservices/main/docs/api-specification/YANA_Notification_API.yaml)
YANA Subscription API | [ReDoc](http://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/VNG-Realisatie/notificatieservices/main/docs/api-specification/YANA_Subscription_API.yaml), [Swagger](https://petstore.swagger.io/?url=https://raw.githubusercontent.com/VNG-Realisatie/notificatieservices/main/docs/api-specification/YANA_Subscription_API.yaml) of [YAML](https://raw.githubusercontent.com/VNG-Realisatie/notificatieservices/main/docs/api-specification/YANA_Subscription_API.yaml)
YANA Catalog API | [ReDoc](http://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/VNG-Realisatie/notificatieservices/main/docs/api-specification/YANA_Catalog_API.yaml), [Swagger](https://petstore.swagger.io/?url=https://raw.githubusercontent.com/VNG-Realisatie/notificatieservices/main/docs/api-specification/YANA_Catalog_API.yaml) of [YAML](https://raw.githubusercontent.com/VNG-Realisatie/notificatieservices/main/docs/api-specification/YANA_Catalog_API.yaml)

## Toelichting

### De API is opgedeeld in drie onderdelen:

Onderdeel | Beschrijving
| :--- | :---
YANA Notification API | Voor het aanleveren van events bij de notificatiecomponent. Ook clients dienen deze API te implementeren om events te kunnen ontvangen.
YANA Subscription API | Voor het aanmaken en onderhouden van abonnementen. Dit is een eerste concept gebaseerd op de voorlopige resultaten van de CloudEVents werkgroep voor abonneren. Op dit onderdeel moeten nog diverse use cases worden uitgewerkt.
YANA Catalog API | Om een beschrijving van een domein en de daarbinnen gebruikte typen en filterattributen te kunnen specificeren. Dit is een ruw prototype met vooral de vraag 'moeten we dit wel zo willen?'. Deze structuren zijn vooral bedoeld voor validatie van binnenkomende events en niet zo zeer voor consumptie door mensen. Wel zou er uit dit soort structuren eenvoudig eenduidige documentatie gegenereerd kunnen worden.

### Documentatie

- [Backlog](./backlog.md)
- [Samenvatting ontwerpbesluiten](./ontwerpbesluiten.md)
- [Mapping op ZGW Notificatie Routing Component API](./mapping_zgw_nrc.md)


