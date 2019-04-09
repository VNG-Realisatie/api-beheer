---
title: "Beheer"
date: '10-12-2018'
weight: 100
---

*Versie 0.1*

## Inleiding

In dit document worden allerlei procedures en overzichten beschreven die van belang zijn bij het in beheer nemen dan wel het uitvoeren van het beheer van een standaard.

## Inhoudsopgave

- [Overdracht van API-development naar API-beheer](#overdracht-van-api-development-naar-api-beheer)
- [Starten van API ontwerp en ontwikkeling](#starten-van-api-ontwerp-en-ontwikkeling)
- [Criteria voor in beheername](#criteria-voor-in-beheername)
- [Resultaat criteria check](#resultaat-criteria-check)
- [Verantwoordelijkheden van Beheer](#verantwoordelijkheden-van-beheer)
- [Lijst van deelnemende partijen en personen](#lijst-van-deelnemende-partijen-en-personen)
- [Overdracht van backlog](#overdracht-van-backlog)
- [Openen Slack kanaal](#openen-slack-kanaal)
- [Openen OpenAPI standaard pagina op GEMMA Online](#openen-openapi-standaard-pagina-op-gemma-online)
- [Openen GEMMA Online discussieforum](#openen-gemma-online-discussieforum)
- [Publicatie op developer.overheid.nl](#publicatie-op-developer.overheid.nl)
- [Klankbordgroepen](#klankbordgroepen)


## Overdracht van API-development naar API-beheer
* _Er moet een template komen van hoe een API standaard wordt overgedragen! Nu ontbraken bijvoorbeeld linkjes naar documentatie._

## Starten van API ontwerp en ontwikkeling
Beheer helpt API developers/designers door:
* Beheer geeft toegang tot Dockerhub voor pushen van images aan devs
* Beheer vraagt aan devs: Voordat je oplevert, hang in test platform met deze credentials
* Documenteer altijd bepaalde onderwerpen; als het n.v.t. is, moet dat er ook staan (bijv. afhankelijkheden van andere APIs)
* Geef via email naar "..." aan dat de standaard in beheer genomen moet worden.

_Ik begrijp deze sectie niet. Wat is hiervan de bedoeling?_

## Criteria voor in beheername
Voordat API standaarden in beheer genomen kunnen worden, worden deze gecheckt a.d.h.v. de checklist [`checklist_inbeheer_nemen.md`](checklist_inbeheer_nemen.md). De checklist bevat acties die door API Beheer moeten worden uitgevoerd maar het bevat ook een aantal eisen waaraan de standaard moet voldoen. De volgende standaarden gelden:

**Over te dragen onderdelen**
De volgende onderdelen moeten aanwezig zijn:
* Het OAS3 bestand (yaml bestand);
* De Github repositories, inclusief de backlog;
* De Referentie Implementatie (RI) als docker container;
* Documentatie, zowel functioneel als technisch. Daarbij is aandacht voor verschillende doelgroepen/doeleinden.
  - ontwikkelaars van provider en consumer applicaties
  - informatiemanagers
  - evt. transitie management (bijv. mapping documentatie)
  - ...
* Een beschrijving van de business logica die in de standaard van toepassing is.
* Een overzicht van wijzigingen (bijv. CHANGELOG.rst in de repository) met daarin per versie wat is toegevoegd, gewijzigd en hoe te migreren van de voorgaande naar deze versie.
* Een overzicht waarin wordt aangegeven welke versies van de betreffende API standaard met welke versies van andere API standaarden compatible zijn.
* Een overzicht van alle partijen en personen die bij de ontwikkeling van de standaard betrokken zijn (geweest).
* Een testomgeving voor de API standaard met testscripts.

**Eisen aan de onderdelen**
De onderdelen moeten aan de volgende eisen voldoen:
* De OAS3 moet voldoen aan de landelijke API strategie, of er is gedocumenteerd en beargumenteerd afgeweken;
* De OAS3 moet foutloos te raadplegen zijn in tools als Swaggerhub of Redoc;
* De OAS3 en de RI sluiten naadloos op elkaar aan.
  * Dit kan door het steekproefsgewijs testen van Openapi.yaml vs test omgeving, vergelijk de resource.
* De standaard is formeel goedgekeurd, concreet gemaakt.
_Het forum voor standaardisatie stelt als eis dat er een openbare consultatie is geweest. De vraag is alleen hoe die openbare consultatie moet worden ingericht. Volgende acties zouden i.i.g. moeten zijn genomen:_
  * Er moet minstens één API-lab gehouden zijn van deze API om de ervaringen van de gebruikers te verzamelen.
  * Er moeten één of meer tussentijdse (sprint) demo's zijn geweest van deze API.
  * ...
* De docker container met de RI moet beschikbaar zijn op DockerHub in de VNG namespace;
* De documentatie omvat minimaal:
  * Een UML model van het informatiemodel (de objecttypen en onderlinge relaties) zoals deze in de API gebruikt wordt.
  * Een overzicht van welke gegevens worden ontsloten in de vorm van een tabel van de resource + bijzonderheden. 
  * Installatie instructies van de RI (bijv. INSTALL.rst in de repository).
* De testomgeving met een implementatie van de RI moet probleemloos draaien. Dit betekent ook dat:
  * De testscripts voor de RI, waarmee we al het gewenst gedrag zoals beschreven in standaard testen, ook beschikbaar zijn gesteld. Beheer zal dit bij doorontwikkeling weer nodig hebben en tevens zullen zij deze beschikbaar stellen aan de leveranciers/gemeenten. 

**Informatievoorziening**
Daarnaast worden er ook eisen gesteld aan de informatievoorziening over de API standaard. Zo moet:
* de Github repositories behorende bij de standaard publiekelijk beschikbaar zijn;
* de OAS zonder restricties op te vragen zijn;
* er een mechanisme zijn om vragen te kunnen stellen aan beheer, (bijvoorbeeld via Slack);
* de website http://ref.tst.vng.cloud/ een pagina over de standaard bevatten;
* gemma Online http://www.gemmaonline.nl/ een pagina over de standaard bevatten;
* de website http://developer.overheid.nl/ een pagina over de standaard bevatten.

## Resultaat criteria check
Het resultaat wordt terug gemaild, met een lijst van verbeteringen door te voeren OF dat de API in beheer wordt genomen.

## Verantwoordelijkheden van Beheer
API Beheer heeft bij het in beheer nemen en bij het uitvoeren van het beheer een aantal verantwoordelijkheden/taken. Sommige taken worden daadwerkelijk zelf uitgevoerd andere alleen in regie. Hieronder een conceptverse:

Taak | Beheer ja/nee |Aard van beheer
--- | --- | ---
Beheren Slack VNG API Community | Ja | Zelf
Beheren onderhoudsverzoeken per API standaard | Ja | Zelf
Beheren GitHub omgevingen | Ja | Zelf
Aanpassen functionele documentatie | Ja| Zelf
Aanpassen technische documentatie | Ja | ?
Aanpassen Referentie Implementaties | Ja | Regie
Wijzigingen UML informatiemodellen/berichtmodellen | Ja | Zelf
Genereren OAS3 m.b.v. Imvertor | Ja | Zelf
Genereren OAS3 vanuit Referentie Implementatie | Ja | Regie
Kwaliteitscheck OAS3 | Ja | ?
Beheren tabel met compatible API's | Ja |Zelf
Beheren testscenario's | Ja | ?
Publiceren nieuwe versie van een API standaard (incl. RI) | Ja |Zelf
Oplossen Bug's | Ja | Regie
Toevoegen nieuwe functionaliteiten | Ja | Regie
Beheren backlog | Ja | Zelf
Beheren DockerHub omgeving | Ja | Regie
Beheren Docker containers in DockerHub omgeving | Ja | Zelf
Beheren publicatie op developer.overheid.nl | Ja | Zelf
Beheren publicatie op GEMMA Online | Ja | Zelf

## Lijst van deelnemende partijen en personen
Bij de ontwikkeling van Open API standaarden nemen diverse partijen deel. Het is handig voor ontwikkelaars maar ook voor beheerders om daar een overzicht van te hebben. Daarom dient de project manager of scrum master bij de aanvang van een ontwikkelproject maar ook tijdens het project als de teamsamenstelling wijzigt de [lijst met Deelnemende partijen](https://github.com/VNG-Realisatie/api-beheer/blob/master/Deelnemende%20partijen.md) in te vullen. Ook de beheerder of beheerders van de standaard moeten na in beheername van een standaard of bij wijziging van de beheerder op deze lijst worden vermeldt.

## Beheerproces
Zodra een Open API standaard is ontwikkeld en goedgekeurd moet het worden overgedragen aan een beheerteam. Teneinde de API standaard breed gedragen en ondersteund te laten worden is een community van belang. Deze community wordt gevormd door gemeenten, leveranciers en beheer. 
Vanuit en samen met die community wordt dat beheerteam daarna voor die betreffende standaard verantwoordelijk voor:
1. beantwoorden van vragen;
2. het oplossen van problemen;
3. doorontwikkeling van de standaard.

**Beantwoorden van vragen**
Vragen mbt. de betreffende standaard kunnen beheer op verschillende manieren bereiken:
* Mail/telefoon
* Slack
* Issue in Github/Gitlab

Vragen via mail of telefoon hebben niet de voorkeur maar dit gaat ongetwijfeld voorkomen. Bij kleinere vragen hoeft dit geen probleem te zijn maar omwille van de openheid en de herbruikbaarheid van antwoorden kan het nuttig zijn deze alsnog via Github/Gitlab of Slack te delen. Een andere optie om de vragen en antwoorden langdurig te delen is een veelgestelde vragenlijst samenstellen die in de loop van de tijd groeit. Zo'n lijst moet ergens goed vindbaar gepubliceerd worden, bijvoorbeeld op GEMMA Online of in de repository van de betreffende standaard. 

Voor het beantwoorden van vragen m.b.t. de betreffende standaard zijn twee kanalen beschikbaar:
1. Het specifiek voor de standaard beschikbaar gestelde kanaal in de Slack workspace [VNG API Community](https://vngapicommunity.slack.com) 
2. Een eveneens specifiek voor (deze versie van) de standaard beschikbaar gestelde GitHub/GitLab omgeving.


Slack leent zich niet zo goed voor het gestructureerd voeren van een discussie aangezien in het kanaal meerdere onderwerpen door elkaar heen kunnen gaan lopen en (in de basis variant) historie slechts tot een x aantal reacties beperkt blijft. Slack is vooral geschikt voor het snel stellen en beantwoorden van enkelvoudige vragen. Laagdrempelig contact dus.

Voor het diepgaand bediscusieren van issues en ter sprake stellen van problemen in de standaard waarbij de discussies een lange(re) tijd beschikbaar moeten blijven kan beter gebruik gemaakt worden van GitHub/GitLab. De meeste vragen en opmerkingen zullen een specifieke versie van een standaard betreffen maar soms ook generiek van aard zijn. Deze vragen, opmerkingen, issues en pull requests moeten vastgelegd worden in de master repository van de standaard, niet in een publicatie repository voor een specifieke versie van de standaard.

Zodra het van belang is om een in Slack gevoerde discussie toch voor langere tijd te bewaren kunnen de beheerders de betreffende discussie alsnog onderbrengen in GitHub/GitLab waarna het evt. meteen aan de juiste persoon toegewezen kan worden. Indien de discussie vragen over het gebruik en toepassing van de standaard betreft dienen de beheerders zich steeds af te vragen of het niet beter is de documentatie van de standaard zo aan te passen dat eenzelfde vraag in de toekomst voorkomen wordt.

Vragen in beide kanalen moeten binnen xx dagen beantwoord zijn.

**Probleemoplossing/Doorontwikkeling**
De initiator voor probleemoplossing en doorontwikkeling van een standaard zijn altijd een of meer in GitHub/GitLab ingebrachte issues. 
Indien het wijzigingsverzoek via Slack binnenkomt verzoekt de beheerder de persoon die het probleem heeft ingediend deze alsnog in GitHub/GitLab in te dienen. Het is immers beter om het probleem of wens uit de eerste hand vastgelegd te hebben.

Na opvoering van het issue beoordeelt de beheerder of het een valide issue is. Indien dat niet het geval is wordt dat gemeld in het issue met de reden daarvoor waarna de melder enkele weken (_hoeveel?_) de tijd krijgt om de reden te weerleggen en zijn verzoek nog nader toe te lichten.

Indien het wel een valide issue is wordt gekeken of het een bug dan wel een feature betreft (_nog kijken naar de termen_).
* Een feature is een wens tot nieuwe functionaliteit binnen een standaard.
Er is dus een bepaalde behoefte.
* Een bug is een foutje in de bestaande functionaliteit van een standaard.
In het geval van een bug is er dus geen sprake van een gewijzigde behoefte maar slechts van een fout in de behoeftevoorziening of documentatie.

Het proces om bugs danwel features in de standaard of een van de deliverables te verwerken verschilt eigenlijk niet zo veel van elkaar.
In beide gevallen kent de Product Owner een prioriteit toe. Daarna wordt in samenwerking met de ontwikkelaars bepaald hoeveel tijd het kost een bug danwel feature te verwerken. Wanneer bij het issue een Pull request met daarin een uitgewerkte oplossing voor het issue ingediend wordt moeten ontwikkelaars deze uitwerking in het PR beoordelen. In geval van een bug wordt tevens nog gekeken of deze backwards compatible opgelost kan worden of niet. Op basis daarvan en de beschikbare financiele ruimte kan de Product Owner nu de roadmap gaan aanpassen.
Vooralsnog is daarbij uitgangspunt dat er 2 x per jaar een nieuwe versie van de API standaard wordt gepubliceerd.
Als de roadmap gereed is wordt eigenlijk ook pas duidelijk of het bij de geplande versies gaat om een nieuwe PATCH, MINOR of MAJOR.  

>Indien volgens de roadmap op 1 moment in het jaar zowel backwards compatible bugs als features in de API standaard moeten worden verwerkt worden eerst de bugs opgelost in de huidige versie (wat leidt tot een PATCH op die versie). Op basis van die versie wordt dan weer een MAJOR/MINOR vervaardigd. (_<-- Misschien opnemen in het versie-beheer verhaal._)
Dit voorkomt dat een leverancier verplicht wordt de nieuwe functionaliteit te implementeren terwijl voor hem op dat moment wellicht alleen het oplossen van de bug van belang is.

_Op dit moment is versiebeheer zo omschreven dat zowel een bug als een feature incompatible en compatible kan zijn. Een bug kan nu opgelost worden met een PATCH maar ook met een MAJOR. In dat laatste geval kun je heel goed zien aan het versienummer dat het niet compatible is met een voorgaande versie. Dat voelt voor mij echter erg vreemd. Het is een geheel andere definitie van MAJOR dan gebruikelijk in de SW wereld._

Wanneer tezamen met een issue een pullrequest (PR) wordt ingediend wordt niet alleen bevinding of wens maar ook een uitwerking ingediend. Dan is het van belang naast de inhoud en urgentie van het issue (zie boven) ook te kijken naar:
* Wat is de kwaliteit van de PR? Om de RI niet te vervuilen moet de PR in ieder geval beoordeeld worden op kwaliteit en duurzaamheid. Mogelijk moet de PR alleen dienen als voorbeeld en moet het issue gere-engineered worden door de ontwikkelaars van de RI.

Overigens is een PR niet altijd een urgent issue. Het kan zijn dat een minder urgent issue al in de praktijk opgelost is en de PR gewoon in de bestaande roadmap opgenomen kan worden en de wijziging te zijner tijd doorgevoerd kan worden.

## Openen Slack kanaal
Het kunnen communiceren met stakeholders van een Open API standaard is belangrijk voor de kwaliteit van de Open API standaard. Het is tevens een manier om een zo hoog mogelijk draagvlak voor de Open API standaard te creeren. Daarom dient de project manager of scrum master bij de aanvang van een ontwikkelproject direct een Slack kanaal m.b.t. de Open API standaard binnen de VNG API Community workspace te (laten) creeren. Zo'n kanaal moet public zijn zodat geinteresseerden zelf kunnen bepalen of ze bijdragen willen posten in het kanaal.

Op GEMMA Online wordt op de pagina die gerelateerd is aan de Open API standaard een link opgenomen waarmee een geinteresseerde zich kan aanmelden voor de workspace waarna hij/zij zelf het gewenste kanaal aan zijn lijst met channels kan toevoegen.

Het Slack kanaal is overigens geen vervanging van de forum-functionaliteit op de GitHub/GitLab repository van de betreffende standaard. In Slack gebeurt het voeren van een discussie op een meer ongestructureerde wijze waardoor het terugvinden van een discussie lastig wordt. Daarnaast bewaart Slack in de standaard versie slechts een x-aantal laatste reacties waardoor historie langzaamaan wordt gewist. 

## Openen OpenAPI standaard pagina op GEMMA Online
Op [deze pagina](https://github.com/VNG-Realisatie/api-beheer/blob/master/doc/gemma_online.md) staat een voorzet van een algemene GEMMA Online API pagina. Wanneer deze voor akkoord bevonden wordt kan deze op GEMMA Online gepubliceerd worden.

## Overdracht van backlog
Bij de overdracht van een standaard van ontwikkeling naar beheer moeten ook de nog in de backlog staande issues overgedragen worden. Dit gebeurt mondeling om de beheerders de gelegenheid te geven vragen te stellen over de issues. Zo moet o.a. duidelijk worden of er afspraken gemaakt zijn met de indiener van het issue m.b.t. de invulling van het issue in toekomstige versies van het koppelvlak.
Aangezien bij overdracht van ontwikkeling naar beheer de GitHub repository as-is wordt overgenomen kan de backlog zelf blijven waar deze is.

Overdracht van de backlog en GitHub repository is een officieel moment en moet plaatsvinden voordat er sprake kan zijn van in beheername van een Open API

## Publicatie op developer.overheid.nl
De API standaard moet op developer.overheid.nl (voorlopig https://test.developer.overheid.nl) worden gepubliceerd. Daartoe moet deze daar worden aangemeld. Dit kan op 2 manieren. Beide manieren staan beschreven op https://test.developer.overheid.nl/api-toevoegen. 

## Klankbordgroepen
Voor de afstemming met stakeholders is het noodzakelijk klankbordgroepen te vormen. Zowel gemeenten/klanten als leveranciers moeten hier zitting in hebben. Om te voorkomen dat net als met de huidige werkgroepen voornamelijk leveranciers deelnemen moet hier speciaal aandacht voor zijn. Een mogelijkheid kan zijn aparte klankbordgroepen voor zowel gemeenten als leveranciers.

De leden van de klankbordgroepen hebben als taken in ieder geval:
* Het monitoren van ingebrachte issues en PRs.
* Het zo mogelijk beantwoorden  en/of verduidelijken van vragen.
* Het mede bepalen van de prioriteiten van de ingebrachte issues en dientengevolge ook de roadmap.
* Communicatie met en vanuit de achterban. Voor het snel en grootscheeps adopteren van de API standaarden is het van belang dat ideeën en plannen verspreid worden. Andersom is het goed om ook "vertegenwoordigers dichtbij" te hebben die feedback opvangen die niet direct als issue ingediend wordt.
