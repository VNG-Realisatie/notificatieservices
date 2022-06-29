## Inleiding

Het project Notificatieservices is in 2021 uitgevoerd door VNG Realisatie in opdracht van het Ministerie van Binnenlandse Zaken. Doel van het project was om geautomatiseerd notificeren van applicaties binnen de Nederlandse overheid te standaardiseren. Meer algemeen was het doel om als overheid beter en vaker gebeurtenisgedreven ('event driven') te kunnen werken. 

Een aanleiding voor het project was de wens om als overheid effectiever gebruik te gaan maken van bronregistraties en daarmee lokale datakopieen overbodig te maken. Naast het opvragen van gegevens via gestandaardiseerde API's zijn daarvoor notificaties nodig als er gebeurtenissen hebben plaatsgevonden die wijzigingen in bronregistraties als gevolg hebben.

Bij de uitvoering hebben verschillende soorten overheidsorganisaties, uitvoeringsorganisaties en marktpartijen in communityverband samengewerkt. Het project is uitgevoerd van junuari 2021 tot juli 2022. 

## Scope

Gebeurtenissen vinden continu en in allelei vormen plaats. Bij de start van het project Notificaties heeft een noodzakelijke afbakening plaatsgevonden. Het project richtte zich bijv. uitsluitend op geautomatiseerd notifceren van applicaties (en dus niet op notificeren van mensen). Wat overigens niet wil zeggen dat projectresultaten niet bruikbaar zijn voor zaken die buiten de projectscope vallen. U vindt een toelichting  in de notitie ['projectscope'](https://github.com/VNG-Realisatie/notificatieservices/blob/main/docs/achtergronddocumentatie/Notificatieservices_Scope.pdf).

## Producten

### NL GOV profile for CloudEvents

Het [NL GOV profile for CloudEvents](https://vng-realisatie.github.io/NL-GOV-profile-for-CloudEvents/) is een specificatie voor het gestandaardiseerd beschrijven en uitwisselen van gegevens over plaatsgevonden gebeurtenissen. Het profiel bouwt voort op de [CloudEvents](https://cloudevents.io/) specificatie die is ontwikkeld door de [Serverless Working Group](https://github.com/cncf/wg-serverless) van de
[Cloud Native Computing Foundation](https://www.cncf.io/). 

De basis van CloudEvents is een specificatie voor het gestandaardiseerd beschrijven van gebeurtenisgegevens. Aanvullend daarop zijn (en worden) standaarden ontwikkeld die beschrijven hoe de specificatie is toe te passen bij gebruik van specifieke gegevensformaten en transportprotocollen. Doelstelling is om wereldwijd de [interoperabiliteit](https://nl.wikipedia.org/wiki/Interoperabiliteit) van services, platforms en voorzieningen te vergroten.

Het [NL GOV profile for CloudEvents](https://vng-realisatie.github.io/NL-GOV-profile-for-CloudEvents/) bevat afspraken over het gebruik van de CloudEvents-specificatie binnen de Nederlandse overheid. Bijvoorbeeld door af te spreken hoe overheidsorganisaties bepaalde attributen gebruiken. Zo maken we als overheid gebruik van internationale standaardisatie en vullen we die aan met afspraken die binnen de Nederlandse context nodig of wenselijk zijn. 

## Handreikingen

Binnen project Notificatieservices zijn naar aanleiding van de opgedane ervaringen een aantal handreikingen ontwikkeld als hulpmiddel voor organisaties die hun informatievoorziening meer event-driven willen inrichten. 

### Technisch

Onderstaande handreikingen beschrijven hoe het NL GOV profiel gestandaardiseerd is te gebruiken in combinatie met een
aantal, ook binnen de overheid, gangbare gegevensformaten, transportprotocollen en patronen. Ze zijn te zien als een logisch verlengstuk van het NL GOV profiel bij het ontwerpen en realiseren van oplossingen. 

- [JSON-gegevensformaat](https://github.com/VNG-Realisatie/NL-GOV-profile-for-CloudEvents/blob/main/NL-GOV-Guideline-for-CloudEvents-JSON.md)
- [HTTP-protocol](https://github.com/VNG-Realisatie/NL-GOV-profile-for-CloudEvents/blob/main/NL-GOV-Guideline-for-CloudEvents-HTTP.md)
- [Webhook interactiepatroon](https://github.com/VNG-Realisatie/NL-GOV-profile-for-CloudEvents/blob/main/NL-GOV-Guideline-for-CloudEvents-Webhook.md).

### Functioneel

Onderstaande handreikingen beschrijven op een toegankelijke manier een aantal belangrijke aspecten van gebeurtenisgedreven werken in het algemeen en notificeren in het bijzonder:

- [Introductie van notificeren](https://github.com/VNG-Realisatie/notificatieservices/blob/main/docs/achtergronddocumentatie/introductie_van_notificeren.pdf)
- [Het waarom van notificeren](https://github.com/VNG-Realisatie/notificatieservices/blob/main/docs/achtergronddocumentatie/waarom_notificeren.pdf)
- [Definieren van gebeurtenistypes](https://github.com/VNG-Realisatie/notificatieservices/blob/main/docs/achtergronddocumentatie/gebeurtenistypes_definieren.pdf)
- [Randvoorwaardelijke aspecten](https://github.com/VNG-Realisatie/notificatieservices/blob/main/docs/achtergronddocumentatie/randvoorwaarden_notificeren.pdf)
- [Notificatiescenario's](https://github.com/VNG-Realisatie/notificatieservices/blob/main/docs/achtergronddocumentatie/notificatiescenarios.pdf)

### Architectuur

De uitgebreide handreiking [Notificatieservices Architectuur](https://github.com/VNG-Realisatie/notificatieservices/blob/main/docs/achtergronddocumentatie/notificatieservices_architectuur.pdf) beschrijft een breed scala aan architectuuraspecten met betrekking tot gebeurtenisgedreven werken. De handreiking is bedoeld om kennis die tijdens het project Notificatieservices is opgedaan beschikbaar te stellen voor toekomstig gebruik. Er is hierbij dankbaar gebruik gemaakt van wat wereldwijd aan kennis en ervaring op dit vlak bestaat.

## Verwijzingen

- [Samenwerkingsruimte voor project Notificatieservices](https://samenwerken.pleio.nl/groups/view/1fde4814-ec84-49bd-a67a-935eb712e7a2/notificatieservices): de plaats waar in 2021 binnen het project met een commmunity van overheids- en uitvoeringsorganisaties en leveranciers is samengewerkt.
- [Community presentaties](https://samenwerken.pleio.nl/groups/view/1fde4814-ec84-49bd-a67a-935eb712e7a2/notificatieservices/files/e49f6a1d-c1ae-4128-95c9-edc3d3e89caf): alle presentaties die gebruikt zijn tijdens
  communitybijeenkomsten
- [Werkgroep Berichtenstandaard presentaties](https://samenwerken.pleio.nl/groups/view/1fde4814-ec84-49bd-a67a-935eb712e7a2/notificatieservices/files/4ff096f5-ba66-4c60-a9d1-44dcd9798897): alle presentaties die gebruikt zijn tijdens
  de werkgroep waarmee de berichtenstandaard is ontwikkeld.

## Informatie en vervolg

Het project Notificatieservices is beeindigd per 30 juni 2022. Naar alle waarschijnlijkheid wordt het beheer van het NL GOV profiel en de ontwikkelde handreikingen binnenkort belegd bij een uitvoeringsorganisatie.

Wilt u feedback geven of vragen stellen dan kunt u daarvoor gebruik maken van Github-issues. Omdat er nog geen strucureel beheer is geregeld kan het zijn dat er niet direct een reactie op volgt:
- Issues m.b.t. project Notificiatieservices: https://github.com/VNG-Realisatie/notificatieservices/issues
- Issues m.b.t. het NL GOV profile for CloudEvents: https://github.com/VNG-Realisatie/NL-GOV-profile-for-CloudEvents/issues/ 


