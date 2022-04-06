# Mapping op ZGW Notificatie Routering Component API

## Events resource

ZGW Attribuut | Events resource attribuut | Opmerkingen
| :--- | :--- | :---
kanaal        | domain | -
hoofdObject   | data.resourceUrl | Notificaties beperkeen tot de hoofdresource. Deze noemen we voortaan 'resource'. Uit het eventtype blijkt welke subresource(s) betrokken zijn.
actie         | type | Format voor conversie van bestaande typen: <hoofdobject>_<resource>_<actie>. Bijvoorbeeld Zaak_status_gewijzigd
aanmaakdatum  | time | -
kenmerken     | nl.vng.zgw.<domain>.<naam> = <value> | -

Deprecated attributen voor backwards compatibility:

ZGW Attribuut | Events resource attribuut | Opmerkingen
| :--- | :--- | :---
hoofdobject | events.data.deprecated_hoofdObject | Let op `hoofdObject` moet ook naar `events.data.resource` 
resource    | events.data.deprecated_resource | -
resourceUrl | events.data.deprecated_resourceUrl | -

## Subscription resource

ZGW Attribuut | Subscription resource attribuut | Opmerkingen
| :--- | :--- | :---
callbackUrl     | subscription.sink | -
auth            | subscription.sinkcredential | -
kanalen.filters | subscription.filter | Niet backwards compatible.
kanalen.naam    | subscription.yana.domain | Niet backwards compatible.

## Topic resource

ZGW Attribuut | Subscription resource attribuut | Opmerkingen
| :--- | :--- | :---
url              | - | Niet gemapped
naam             | domains.name | -
documentatieLink | domains.documentationLink | _
filters          | attributes resource | -
