# Mapping op ZGW Notificatie Routering Component API

## Events resource

ZGW Attribuut | Events resource attribuut | Opmerkingen | Voorbeeld
| :--- | :--- | :--- | :---
| specversion | ... | ...
| id | ... | ...
| source | ... | ...
| datacontenttype | ... | ...
kanaal        | domain | - | nl.vng.zgw.zaken of nl.vng.zgw.documenten
hoofdObject   | data.resourceUrl | Notificaties beperkeen tot de hoofdresource. Deze noemen we voortaan 'resource'. Uit het eventtype blijkt welke subresource(s) betrokken zijn.
actie         | type | Format voor conversie van bestaande typen: <hoofdobject>_<resource>_<actie>. Bijvoorbeeld Zaak_status_gewijzigd
aanmaakdatum  | time | -
kenmerken     | &lt;domain&gt;.&lt;naam&gt; = &lt;value&gt; | - | nl.vng.zgw.zaken.vertrouwelijkheid

Deprecated attributen voor backwards compatibility:

ZGW Attribuut | Events resource attribuut | Opmerkingen
| :--- | :--- | :---
hoofdobject | data.deprecated_hoofdObject | Let op `hoofdObject` moet ook naar `events.data.resource` 
resource    | data.deprecated_resource | -
resourceUrl | data.deprecated_resourceUrl | -

## Subscription resource

ZGW Attribuut | Subscription resource attribuut | Opmerkingen
| :--- | :--- | :---
callbackUrl     | sink | -
auth            | sinkcredential | -
kanalen.filters | filter | Niet backwards compatible.
kanalen.naam    | domain | Niet backwards compatible.

## Topic resource

ZGW Attribuut | Domain resource attribuut | Opmerkingen
| :--- | :--- | :---
url              | - | Niet gemapped
naam             | name | -
documentatieLink | documentationLink | _
filters          | filterAttributes | -
