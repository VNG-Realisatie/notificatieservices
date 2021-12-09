# Project Notificatieservices

## Inleiding

Project Notificatieservices wil het mogelijk maken dat Nederlandse overheidsorganisaties
vaker en beter gebeurtenisgedreven ('event driven') werken en applicaties via
gestandaardiseerde notificaties op de hoogte stellen als zich relevante gebeurtenissen
hebben voorgedaan. Project Notificatieservices heeft samen met een aantal overheidsorganisaties en leveranciers een specificatie opgeleverd waarmee eenduidig gegevens over plaatsgevonden gebeurtenissen tusssen applicaties zijn uit te wisselen: het NL GOV profile for CloudEvents.

## Organisatie

Het project is in 2021 uitgevoerd in opdracht van het Ministerie van Binnenlandse Zaken
met als opdrachtnemer VNG Realisatie. Bij de uitvoering zijn zowel overheidsorganisaties (bijv. gemeenten) als uitvoeringsorganisaties (bijv. Logius) als marktpartijen betrokken.
Het project loopt tot medio 2022 en zal naar verwachting een vervolg krijgen in een
andere vorm.

## Scope

Gebeurtenissen doen zich in vele vormen en binnen vele contexten voor. Bij uitvoering van het project is gekozen voor een afbakening van de scope om te voorkomen dat er teveel vraagstukken tegelijkertijd zouden moeten worden opgelost. Een belangrijke afbakening is bijv. dat het project zich richt op geautomatiseerd notifceren tussen applicaties. Overigens is de verwachting dat veel projectresultaten ook bruikbaar zullen zijn voor zaken die nu buiten scope zijn geplaatst. ([Toelichting op projectscope](./projectscope))

## NL GOV profile for CloudEvents

Het NL GOV profile for CloudEvents is een specificatie voor het gestandaardiseerd
beschrijven en kunnen uitwisselen van plaatsgevonden gebeurtenissen tussen applicaties.
Het profiel is gebaseerd op de [CloudEvents](https://cloudevents.io/) specificatie die is ontwikkeld door de [Serverless Working Group](https://github.com/cncf/wg-serverless) van de
[Cloud Native Computing Foundation](https://www.cncf.io/). CloudEvents is een
specificatie voor beschrijven van gebeurtenisgegevens in gangbare formaten
om interoperabiliteit tussen services, platforms en systemen te bieden.

Een van de uitgangspunten van het project was om zoveel mogelijk aan te sluiten bij wat wereldwijd gebruikelijk is (bijv. notificeren via het [publish-subscribe patroon](https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern) en om voort te bouwen op wat al ontwikkeld is (bijv. [CloudEvents](https://cloudevents.io/). In plaats van al uitgevonden wielen opnieuw, en waarschijnlijk slechter, te gaan uitvinden is aangesloten bij wat
wereldwijd op dit gebied gebeurt en maken aanvullende afspraken waar dit binnen de context van de Nederlandse overheid nodig of wenselijk is.

**De huidige werkversie van het profiel: [https://vng-realisatie.github.io/NL-GOV-profile-for-CloudEvents/](https://vng-realisatie.github.io/NL-GOV-profile-for-CloudEvents/)**

## Andere producten

Naast het NL GOV profiel, ook wel genoemd 'de berichtstandaard', zijn ook een
aantal andere producten ontwikkeld:

- technische handreikingen zoals hoe het NL GOV profiel gestandaardiseerd kan worden gebruikt met het JSON-gegevensformaat, HTTP-protocol en Webhook interactiepatroon.
- functionele handreikingen waarin bijv. is beschreven welke belemmeringen en knelpunten er zijn om als overheid meer gebeurtenisgedreven te kunnen werken en hoe daar verbetering in kan worden gebracht
- achtergronddocumentatie waarin bijv. architectuurstijlen en implementatiepatronen worden beschreven die bruikbaar zijn bij het meer gebeurtenisgedreven gaan werken.

## Verwijzingen

In deze Github-repository vindt u:

- [Guideline for JSON, HTTP en Webhook](./docs/Use-of-json-http-webhook.md): een handreiking hoe het profiel gestandaardiseerd is te gebruiken bij oplossingen die gebruik maken van JSON, HTTP en/of Webhook.
- [Achtergrond documentatie](./docs/Achtergrond-documentatie): verschillende producten
  die tijdens de uitvoering van het project zijn ontwikkeld en als achtergronddocumentatie beschikbaar zijn (o.a. architectuur en een analyse van bestaande knelpunten en oplossingsrichtingen).

Op Pleio vind u onder andere:

- [Samenwerkingsruimte voor project Notificatieservices](https://samenwerken.pleio.nl/groups/view/1fde4814-ec84-49bd-a67a-935eb712e7a2/notificatieservices): de plaats waar in 2021 binnen het project met een commmunity van medewerkers van overheidsorganisaties en leveranciers is samengewerkt.
- [Community presentaties](https://samenwerken.pleio.nl/groups/view/1fde4814-ec84-49bd-a67a-935eb712e7a2/notificatieservices/files/e49f6a1d-c1ae-4128-95c9-edc3d3e89caf): alle presentaties die gebruikt zijn tijdens
  communitybijeenkomsten
- [Werkgroep Berichtenstandaard presentaties](https://samenwerken.pleio.nl/groups/view/1fde4814-ec84-49bd-a67a-935eb712e7a2/notificatieservices/files/4ff096f5-ba66-4c60-a9d1-44dcd9798897): alle presentaties die gebruikt zijn tijdens
  de werkgroep waarmee de berichtenstandaard is ontwikkeld.
- [Hackathon verslagen](https://samenwerken.pleio.nl/groups/view/1fde4814-ec84-49bd-a67a-935eb712e7a2/notificatieservices/files/710ac2c8-bdd3-49bc-8b76-10646ab93ddf): dagverslagen van een in november 2021
gehouden hackathon waarbij een eerste beproeving van de concept berichtenstandaard is gedaan.

Beheerder van deze repository is Ad Gerrits (VNG). Bereikbaar via email: ad.gerrits@vng.nl
