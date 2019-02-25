API-Beheer
=====
[![Build Status](https://jenkins.nlx.io/job/gemma-zaken-build-and-test/badge/icon?style=plastic)](https://jenkins.nlx.io/) ![Repo Status](https://img.shields.io/badge/status-concept-lightgrey.svg?style=plastic)

## Doel

Deze repository bevat alles wat nodig is om de GEMMA ZDS 2.0 Open API standaard in beheer te kunnen nemen en om dat beheer goed uit te kunnen voeren.

> _**Nog te beantwoorden vragen:**_
> - _De ZDS 2.0 standaard is het geheel van standaarden voor het zaakgericht werken. Is het doel van dit project nu de in beheername van al deze standaarden of alleen van een van die standaarden?_
> - _Blijkbaar kun je standaarden clusteren. Moeten we daarvoor in GEMMA Online voorzieningen treffen?_

Het dient daarnaast tevens als aanzet om te komen tot een generieke methode voor het in beheer nemen en uitvoeren van dat beheer van andere (nog te ontwikkelen) Open API standaarden.
De inhoud van deze repository zal op een later moment mogelijk worden opgenomen in een repository waarin het beheer van Open API standaarden of van standaarden in het algemeen worden beschreven.

**Visie API-Beheer** 

Het beheer van Open API standaarden waarborgt de ondersteuning van de standaard nadat deze is ontwikkeld.
Voor een Open API standaard die in beheer is betreft dat het beantwoorden van vragen, het vastleggen van problemen met de standaard, het oplossen van kleine problemen, het opnieuw beschikbaar stellen van alle componenten van de door beheer aangepaste standaard, etc... 

Er kan op een gegeven moment behoefte ontstaan om een API standaard door te ontwikkelen. Die doorontwikkeling dient in projectvorm te worden opgepakt en is geen taak van API-beheer.

Bij het beheer van een Open API standaard onderkennen we 2 fases en elke fase kent een aantal aspecten:
* In beheername fase.
  + De Open API standaard moet voldoen aan een aantal criteria voordat deze in beheer genomen kan worden.
    Deze worden in deze fase gecheckt en aan de hand van die check volgt de in beheername tenzij er niet aan de
    criteria wordt voldaan. Idealiter hebben de ontwikkelaars van een standaard de criteria natuurlijk al tijdens de
    ontwikkeling van de standaard in het oog. Daarnaast zijn de beheerders stakeholders bij de ontwikkeling van een standaard 
    en houden zij dit aspect ook goed in de gaten. Dit zou dus slechts een formele slag moeten zijn.
  + Al het materiaal, documentatie en omgevingen die bij de ontwikkeling van de API standaard zijn aangemaakt wordt in deze fase overgedragen. Het gaat om een officieel moment waarop de beheerders aangeven dat de standaard officieel onder hun beheer valt maar mzo nodig betreft het ook het regelen van de juiste rechten.

>   _**Nog te beantwoorden vragen:**_ 
>  - _Is bij de overdracht het door de leveranciers en gemeenten te gebruiken kanaal al ingericht?_

* Beheerfase.
  Dit is de fase waarin (de componenten van) een standaard daadwerkelijk in beheer is genomen
  - aspecten die betrekking hebben op de werkzaamheden van de beheerders.
    + Wat is de aard van het beheer van de diverse componenten. Voeren de beheerders de werkzaamheden zelf uit of voeren zij alleen de regie uit.
    + over welke vaardigheden en kennis dienen beheerders te beschikken? 
    Dit wordt (mede) bepaald door de taken die de beheerders hebben. Wel/niet zelf aanpassen van de referentie implementatie, genereren van API's uit referentie implementatie en/of een UML model, etc.
    + hoe dienen zij te handelen in de diverse situaties?
    + welke software hebben zij nodig voor het uitvoeren van hun taken?
    + welke afspraken zijn er gemaakt om terug te kunnen vallen op specialistische kennis wanneer de bij de beheerder(s) aanwezige 
      kennis niet voldoet of bij onvoldoende beheercapaciteit?
    + etc...
  - aspecten die betrekking hebben op leveranciers en gemeenten.
    Welke voorzieningen moeten er ingericht worden, of in geval dat al gebeurd is welke voorzieningen moeten
    beheerd worden, voor de leveranciers en gemeenten zodat zij:
    + de standaard kunnen gebruiken?
    + de standaard kunnen testen? 
    + zij vragen en problemen kunnen melden?
    + etc...
  - aspecten die betrekking hebben op het configureren van de standaard in de test-voorziening.
    + waar kan informatie voor het configureren van de testvoorziening gevonden worden?
    + ...
    
Enkele aspecten die van belang zijn bij het beheer van een standaard spelen ook al een rol bij de ontwikkeling van een standaard.
Denk daarbij aan:
* de inrichting van een communicatiekanaal waarop leveranciers en gemeenten hun vragen en problemen kunnen stellen.
Dit moet voor elke standaard op dezelfde wijze gebeuren. Dus bijv. allemaal op dezelfde locatie, of allemaal binnen de eigen GitHub repository, of nog een andere variant zolang het maar generiek is.
* een lijst met aan het ontwikkelproject deelnemende partijen en personen.
Een overzicht van de personen en organisaties die hebben bijgedragen aan de ontwikkeling van een standaard is niet alleen handig tijdens de ontwikkeling van de standaard maar ook bij het beheer van een standaard.

Aangezien je deze aspecten niet bij de in beheername opnieuw wil inrichten moet dit bij de start van de ontwikkeling van een nieuwe standaard al meteen zo worden gedaan dat zowel ontwikkelaars als beheerders er mee uit de voeten kunnen.

**Beheer en standaard creatie methodiek**

Er zijn 2 methodieken die in projecten gebruikt kunnen worden bij het vervaardigen van API standaarden.

De eerste methode gaat uit van een (nagenoeg) blanco domeinmodel. Het domeinmodel (het model waarin duidelijkheid wordt geschept over de te gebruiken entiteiten, de daarbinnen benodigde attributen en de relaties tussen de entiteiten) moet dus nog helemaal opgebouwd worden.
Aangezien we in snel op elkaar volgende sprints de nieuwe standaard willen ontwikkelen wordt er niet voor gekozen eerst een informatiemodel te ontwikkelen en daarna pas de andere benodigde componenten. Alle componenten worden tegelijkertijd ontwikkelt waardoor de mate van volwassenheid van de componenten en dus de standaard in de tijd langzamerhand toeneemt. Het OAS3 bestand wordt in dit geval gegenereerd uit de Referentie Implementatie waardoor beide in sync blijven.

De tweede methode gaat uit van een MDD aanpak. Op basis van een of meer bestaande informatiemodellen wordt een Bericht Structuurmodel vervaardigd en wordt van daaruit het OAS3 bestand gegenereerd m.b.v. specialistische tooling. Het gegenereerde OAS3 bestand is de basis voor code generatie waardoor ook in dit geval geldt dat de code in sync is met het OAS3 bestand. Ook in dit geval wordt echter niet gewacht totdat de het Bericht Structuurmodel helemaal gereed is. Nee, tussentijdse resultaten van dit proces kunnen al heel goed dienen als basis voor codegeneratie.

Welke methode door een project wordt gehanteerd wordt binnen het project beslist en hangt bijv. af van de vraag of er al een (domein)model aanwezig is. Beide methodieken kennen elk hun eigen voordelen.

Het bestaan van 2 verschillende methodieken voor het vervaardigen van API standaarden betekent natuurlijk wat voor het beheer van deze standaarden. Als beheer hebben we er belang bij om het beheerproces zo uniform mogelijk in te richten.

>   _**Nog aan te vullen**_ 

## Vragen en bijdragen
...

## Documentatie
...

## Rollen

- Opdrachtgever: [@TheoVNGPeters](https://github.com/TheoVNGPeters)
- Delivery Manager: [@wishalg](https://github.com/wishalg)
- Product Owner: [@melsk-r](https://github.com/melsk-r)
- Scrum Master:  [@TCIMEddy](https://github.com/TCIMEddy)

