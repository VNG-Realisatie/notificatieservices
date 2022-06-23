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

Gebeurtenissen doen zich in vele vormen en binnen vele contexten voor. Bij uitvoering van het project is gekozen voor een afbakening van de scope om te voorkomen dat er teveel vraagstukken tegelijkertijd zouden moeten worden opgelost. Een belangrijke afbakening is bijv. dat het project zich richt op geautomatiseerd notifceren tussen applicaties. Overigens is de verwachting dat veel projectresultaten ook bruikbaar zullen zijn voor zaken die nu buiten scope zijn geplaatst. U vindt hier een toelichting op de binnen project Notificatieservices gehanteerde [scope van notificeren](https://github.com/VNG-Realisatie/notificatieservices/blob/main/docs/achtergronddocumentatie/Notificatieservices_Scope.pdf).

## Producten

### NL GOV profile for CloudEvents

Het NL GOV profile for CloudEvents is een specificatie voor het gestandaardiseerd
beschrijven en kunnen uitwisselen van plaatsgevonden gebeurtenissen tussen applicaties.
Het profiel is gebaseerd op de [CloudEvents](https://cloudevents.io/) specificatie die is ontwikkeld door de [Serverless Working Group](https://github.com/cncf/wg-serverless) van de
[Cloud Native Computing Foundation](https://www.cncf.io/). CloudEvents is een
specificatie voor beschrijven van gebeurtenisgegevens in gangbare formaten
om interoperabiliteit tussen services, platforms en systemen te bieden.

Een van de uitgangspunten van het project was om zoveel mogelijk aan te sluiten bij wat wereldwijd gebruikelijk is (bijv. notificeren via het [publish-subscribe patroon](https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern) en om voort te bouwen op wat al ontwikkeld is (bijv. [CloudEvents](https://cloudevents.io/). In plaats van al uitgevonden wielen opnieuw, en waarschijnlijk slechter, te gaan uitvinden is aangesloten bij wat
wereldwijd op dit gebied gebeurt en maken aanvullende afspraken waar dit binnen de context van de Nederlandse overheid nodig of wenselijk is.

**De huidige werkversie van het profiel staat op: [https://vng-realisatie.github.io/NL-GOV-profile-for-CloudEvents/](https://vng-realisatie.github.io/NL-GOV-profile-for-CloudEvents)** Wilt u op feedback geven op het concept-profiel of op een andere manier meehelpen het profiel te verbeteren kijk dan op: [https://github.com/VNG-Realisatie/NL-GOV-profile-for-CloudEvents](https://github.com/VNG-Realisatie/NL-GOV-profile-for-CloudEvents)

### Technische handreikingen

Onderstaande meer 'technische handreikingen' beschrijven hoe het NL GOV profiel gestandaardiseerd kan worden toegepast bij gebruik van een
aantal vaak gebruikte gegevensformaten, transportprotocollen en patronen:

- [JSON-gegevensformaat](https://github.com/VNG-Realisatie/NL-GOV-profile-for-CloudEvents/blob/main/NL-GOV-Guideline-for-CloudEvents-JSON.md)
- [HTTP-protocol](https://github.com/VNG-Realisatie/NL-GOV-profile-for-CloudEvents/blob/main/NL-GOV-Guideline-for-CloudEvents-HTTP.md)
- [Webhook interactiepatroon](https://github.com/VNG-Realisatie/NL-GOV-profile-for-CloudEvents/blob/main/NL-GOV-Guideline-for-CloudEvents-Webhook.md).

# Functionele handreikingen

Onderstaande meer 'functionele handreikingen' beschrijven op een toegankelijke manieren belangrijke aspecten van gebeurtenisgedreven werken en notificeren:

- [Introductie van notificeren](https://github.com/VNG-Realisatie/notificatieservices/blob/main/docs/achtergronddocumentatie/introductie_van_notificeren.pdf)
- [Het waarom van notificeren](https://github.com/VNG-Realisatie/notificatieservices/blob/main/docs/achtergronddocumentatie/waarom_notificeren.pdf)
- [Definieren van gebeurtenistypes](https://github.com/VNG-Realisatie/notificatieservices/blob/main/docs/achtergronddocumentatie/gebeurtenistypes_definieren.pdf)
- [Randvoorwaardelijke aspecten](https://github.com/VNG-Realisatie/notificatieservices/blob/main/docs/achtergronddocumentatie/randvoorwaarden_notificeren.pdf)
- [Notificatiescenario's](https://github.com/VNG-Realisatie/notificatieservices/blob/main/docs/achtergronddocumentatie/notificatiescenarios.pdf)


# Architectuur handreiking

- [Notificatieservices Architectuur](https://github.com/VNG-Realisatie/notificatieservices/blob/main/docs/achtergronddocumentatie/notificatieservices_architectuur.pdf) - De handreiking beschrijft een breed scala aan architectuuraspecten met betrekking tot gebeurtenisgedreven werken en notificeren. De handreiking is bedoeld om kennis die tijdens het project Notificatieservices is opgedaan beschikbaar te stellen voor toekomstig gebruik. Er is hierbij dankbaar gebruik gemaakt van wat wereldwijd aan kennis en ervaring op dit vlak aanwezig is.

## Verwijzingen

Tijdens de uitvoering van Project Notificatieservices is een Pleio-groep als samenwerkingsomgeving gebruikt. U vindt daar onder andere:

- [Samenwerkingsruimte voor project Notificatieservices](https://samenwerken.pleio.nl/groups/view/1fde4814-ec84-49bd-a67a-935eb712e7a2/notificatieservices): de plaats waar in 2021 binnen het project met een commmunity van medewerkers van overheidsorganisaties en leveranciers is samengewerkt.
- [Community presentaties](https://samenwerken.pleio.nl/groups/view/1fde4814-ec84-49bd-a67a-935eb712e7a2/notificatieservices/files/e49f6a1d-c1ae-4128-95c9-edc3d3e89caf): alle presentaties die gebruikt zijn tijdens
  communitybijeenkomsten
- [Werkgroep Berichtenstandaard presentaties](https://samenwerken.pleio.nl/groups/view/1fde4814-ec84-49bd-a67a-935eb712e7a2/notificatieservices/files/4ff096f5-ba66-4c60-a9d1-44dcd9798897): alle presentaties die gebruikt zijn tijdens
  de werkgroep waarmee de berichtenstandaard is ontwikkeld.
- [Hackathon verslagen](https://samenwerken.pleio.nl/groups/view/1fde4814-ec84-49bd-a67a-935eb712e7a2/notificatieservices/files/710ac2c8-bdd3-49bc-8b76-10646ab93ddf): dagverslagen van een in november 2021
  gehouden hackathon waarbij een eerste beproeving van de concept berichtenstandaard is gedaan.

Beheerder van deze repository is Ad Gerrits (VNG): ad.gerrits@vng.nl

Voor projectgerelateerde vragen kunt u contact opnemen met Stijn Schrijvers (VNG): stijn.schrijvers@vng.nl
