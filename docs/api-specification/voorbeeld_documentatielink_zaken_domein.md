# Notificaties

**Documentatie over notificaties binnen het domein Zaken**

Via een notificatiecomponent kunnen consumers zich abonneren op notificaties uit het domein Zaken.

** Todo **
- Als voorbeeld url naar referentie implementatie opnemen.
- Verwijzing naar documentatie over notificeren en de notificatiecomponent.

## Domein

Namespace van het domein is `nl.vng.zaken`.

## Filterattributen (_Voorheen Kenmerken_)

- `bronorganisatie`: Het RSIN van de Niet-natuurlijk persoon zijnde de organisatie die de zaak heeft gecreeerd. Dit moet een geldig RSIN zijn van 9 nummers en voldoen aan https://nl.wikipedia.org/wiki/Burgerservicenummer#11-proef
- `zaaktype`: URL-referentie naar het ZAAKTYPE (in de Catalogi API) in de CATALOGUS waar deze voorkomt
- `vertrouwelijkheidaanduiding`: Aanduiding van de mate waarin het zaakdossier van de ZAAK voor de openbaarheid bestemd is.

## Eventtypes (_Voorheen Resources en acties_)

Voorbeelden van events. 

** Todo ** Definitieve typenamen moeten nog worden vastgesteld.

<table>
  <tr>
      <td></td>
      <td colspan="2"><i>Voorheen</i></td>
      <td></td>
  </tr>
  <tr>
      <td><b>Eventtype</b></td>
      <td><b>Resource</b></td>
      <td><b>Actie</b></td>
      <td><b>Toelichting</b></td>
  </tr>
  <tr>
      <td>nl.vng.zaken.zaak_gecreerd</td>
      <td>zaak</td>
      <td>create</td>
      <td>Taalgebruik: Aangemaakt of gecreerd?</td>
  </tr>
  <tr>
      <td>nl.vng.zaken.zaak_gewijzigd</td>
      <td>zaak</td>
      <td>update</td>
      <td>?</td>
  </tr>
  <tr>
      <td>nl.vng.zaken.zaak_verwijderd</td>
      <td>zaak</td>
      <td>destroy</td>
      <td>?</td>
  </tr>
  <tr>
      <td>nl.vng.zaken.status_gewijzigd</td>
      <td>status</td>
      <td>create</td>
      <td>Is de status nu in functionele zin gewijzigd of is er een nieuwe aangemaakt?</td>
  </tr>
    
</table>


** Todo ** Nog om te zetten:

    zaakobject: create, update, destroy
    zaakinformatieobject: create
    zaakeigenschap: create, update, destroy
    klantcontact: create
    rol: create, destroy
    resultaat: create, update, destroy
    zaakbesluit: create
    zaakcontactmoment: create
    zaakverzoek: create
