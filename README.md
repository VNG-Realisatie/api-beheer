API-Beheer
=====
[![Build Status](https://jenkins.nlx.io/job/gemma-zaken-build-and-test/badge/icon?style=plastic)](https://jenkins.nlx.io/) ![Repo Status](https://img.shields.io/badge/status-concept-lightgrey.svg?style=plastic)

## Doel

Deze repository bevat alles wat nodig is om de GEMMA ZDS 2.0 Open API standaard in beheer te kunnen nemen en om dat beheer goed uit te kunnen voeren.

> _**Nog te beantwoorden vragen:**_
> - _De ZDS 2.0 standaard is het geheel van standaarden voor het zaakgericht werken. Is het doel van dit project nu de in beheername van al deze standaarden of alleen van een van die standaarden?_
> - _Blijkbaar kun je standaarden clusteren. Moeten we daarvoor in GEMMA Online voorzieningen treffen?_

Het dient daarnaast tevens als aanzet om te komen tot een generieke methode voor het in beheer nemen en uitvoeren van dat beheer van andere (nog te ontwikkelen) Open API standaarden.
De inhoud van deze repository zal op een later moment mogelijk worden opgenomen in een repositroy waarin het beheer van Open API standaarden of van staandarden in het algemeen worden beschreven.

**Visie API-Beheer** 

Het beheer van Open API standaarden waarborgt de ondersteuning van de standaard nadat deze is ontwikkeld.
Zo worden er vragen beantwoord, problemen met de standaard vastgelegd, vindt er doorontwikkeling plaats, etc... 

Bij het beheer van een Open API standaard onderkennen we 2 fases en elke fase kent een aantal aspecten:
* In beheername fase.
  De Open API standaard moet voldoen aan een aantal criteria voordat het in beheer genomen kan worden.
  Deze worden in deze fase gecheckt en aan de hand van die check volgt de in beheername tenzij er niet aan de
  criteria wordt voldaan. Idealiter hebben de ontwikkelaars van een standaard de criteria natuurlijk al tijdens de
  ontwikkeling van de standaard in het oog. Daarnaast zijn de beheerders stakeholders bij de ontwikkeling van een standaard 
  en houden zij dit aspect ook goed in de gaten. Dit zou dus slechts een formele slag moeten zijn.

  Na acceptatie van de standaard volgt de overdracht van de standaard naar de beheerders.

>   _**Nog te beantwoorden vragen:**_ 
>  - _is bij de overdracht een standaard al gepubliceerd?_
>  - _is bij de overdracht het door de leveranciers en gemeenten te gebruiken kanaal al ingericht?_
>  - _is bij de overdracht de standaard al geconfigureerd in de testvoorziening?_
>  - _het inrichten van een communicatiekanaal waarop leveranciers en gemeenten hun vragen en problemen kunnen stellen moet voor elke standaard op dezelfde wijze gebeuren. Dus bijv. allemaal op dezelfde locatie, of allemaal binnen de eigen GitHub repository, of nog een andere variant zolang het maar generiek is. Aangezien je n.m.m. niet bij ontwikkeling een ander kanaal wil inrichten dan bij beheer moet dit bij de start van de ontwikkeling van een nieuwe standaard al goed worden gedaan. Dit is dus een beheercriteria dat al speelt bij de aanvang van een ontwikkelproject. Welke criteria kunnen we nog meer onderkennen waarvoor dat geldt?_
>  - _..._

* Beheerfase.
  Dit is de fase waarin een standaard daadwerkelijk in beheer is genomen
  - aspecten die betrekking hebben op de werkzaamheden van de beheerders.
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

## Vragen en bijdragen
...

## Documentatie
...

## Rollen

- Opdrachtgever: [@TheoVNGPeters](https://github.com/TheoVNGPeters)
- Delivery Manager: [@wishalg](https://github.com/wishalg)
- Product Owner: [@melsk-r](https://github.com/melsk-r)
- Scrum Master:  [@TCIMEddy](https://github.com/TCIMEddy)

