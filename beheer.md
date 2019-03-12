---
title: "Beheer"
date: '10-12-2018'
weight: 100
---

*Versie 0.1*

## Inleiding

In dit document worden allerlei procedures en overzichten beschreven die van belang zijn bij het in beheer nemen dan wel het uitvoeren van het beheer van een standaard.

## Inhoudsopgave

- [Overdragen van API-development naar API-beheer](#overdragen-van-api-development-naar-api-beheer)
- [Starten van API ontwerp en ontwikkeling](#starten-van-api-ontwerp-en-ontwikkeling)
- [Criteria voor in beheername](#criteria-voor-in-beheername)
- [Resultaat criteria check](#resultaat-criteria-check)
- [Verantwoordelijkheden van Beheer](#verantwoordelijkheden-van-beheer)
- [Lijst van deelnemende partijen en personen](#lijst-van-deelnemende-partijen-en-personen)
- [Overdracht van backlog](#overdracht-van-backlog)
- [Openen Slack kanaal](#openen-slack-kanaal)
- [Openen OpenAPI standaard pagina op GEMMA Online](#openen-openapi-standaard-pagina-op-gemma-online)
- [Openen GEMMA Online discussieforum](#openen-gemma-online-discussieforum)
- [Werken met Docker](#werken-met-docker)



## Overdragen van API-development naar API-beheer
* Er moet een template komen van hoe een API standaard wordt overgedragen! Nu ontbraken bijvoorbeeld linkjes naar documentatie.
* Criteria (checklist) moet ook naar API-developers

## Starten van API ontwerp en ontwikkeling
Beheer helpt API developers/designers door:
* Beheer geeft toegang tot Dockerhub voor pushen van images aan devs
* Beheer vraagt aan devs: Voordat je oplevert, hang in test platform met deze credentials
* Documenteer altijd bepaalde onderwerpen; als het n.v.t. is, moet dat er ook staan (bijv. afhankelijkheden van andere APIs)
* Geef via email naar "..." aan dat de standaard in beheer genomen moet worden.

## Criteria voor in beheername
Voordat API standaarden in beheer genomen kunnen worden moeten deze voldoen aan een aantal eisen. Hieronder staat een eerste aanzet daartoe:

* Er moet een testomgeving draaien van de implementatie. Dit betekent ook dat:
  * De testscripts voor de referentie-implementaties waarmee we al het gewenst gedrag zoals beschreven in standaard ook beschikbaar worden gesteld. Beheer zal dit bij doorontwikkeling weer nodig hebben en tevens zullen zij deze beschikbaar stellen aan de leveranciers/gemeenten. 
*  Is de standaard (deze bestaat uit de OAS, referentieimplementatie, documentatie) formeel goedgekeurd, concreet gemaakt:
  * Er moet een API-lab gehouden zijn van deze API
  * Er moeten één of meer tussentijdse (sprint) demo's zijn geweest van deze API
  * De API moet beschikbaar zijn in het VNG test platform
* De standaard moet publiekelijk beschikbaar zijn:
  * De OAS moet zonder restricties op te vragen zijn in de browser
* Kwaliteitscheck op OAS:
  * De standaard moet voldoen aan de landelijke API strategie, of er is gedocumenteerd en beargumenteerd afgeweken.
  * Openen in Swaggerhub ter dubbelcheck
* Documentatie omvat minimaal:
  * Een UML model van het informatiemodel (de objecttypen en onderlinge relaties) zoals deze in de API gebruikt wordt.
  * Een overzicht van welke gegevens worden ontsloten in de vorm van een tabel van de resource + bijzonderheden. 
  * Installatie instructies van de referentie implementatie (bijv. INSTALL.rst in de repository).
  * Een beschrijving van de business logica die in de standaard van toepassing is.
  * Een overzicht van wijzigingen (bijv. CHANGELOG.rst in de repository) met daarin per versie wat is toegevoegd, gewijzigd en hoe te migreren van de voorgaande naar deze versie.
  * De standaard bevat een overzicht waarin wordt aangegeven welke versies van de betreffende API standaard met welke versies van andere API standaarden compatible zijn.
 * De standaard bevat een overzicht van alle partijen en personen die bij de ontwikkeling van de standaard betrokken zijn (geweest).
* De referentie-implementatie moet gereed en up-to date zijn met de dan geldende OAS3
  * Steekproefsgewijs testen van Openapi.yaml vs test omgeving, vergelijk de resource
* De docker container met de referentie-implementatie moet beschikbaar zijn op DockerHub in de VNG namespace.

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
Aanpassen technische documentatie | ? | ?
Aanpassen Referentie Implementaties | Ja | Regie
Wijzigingen UML informatiemodellen/berichtmodellen | Ja | Zelf
Genereren OAS3 m.b.v. Imvertor | Ja | Zelf
Beheren tabel met compatible API's | Ja |Zelf
Beheren testscenario's | ? | ?
Publiceren nieuwe versie van een API standaard (incl. RI) | Ja |Zelf
Oplossen Bug's | ? | ?
Toevoegen nieuwe functionaliteiten | ? | ?
Beheren backlog | ? | ?
... | ...


## Lijst van deelnemende partijen en personen
Bij de ontwikkeling van Open API standaarden nemen diverse partijen deel. Het is handig voor ontwikkelaars maar ook voor beheerders om daar een overzicht van te hebben. Daarom dient de project manager of scrum master bij de aanvang van een ontwikkelproject maar ook tijdens het project als de teamsamenstelling wijzigt de [lijst met Deelnemende partijen](https://github.com/VNG-Realisatie/api-beheer/blob/master/Deelnemende%20partijen.md) in te vullen. Ook de beheerder of beheerders van de standaard moeten na in beheername van een standaard of bij wijziging van de beheerder op deze lijst worden vermeldt.

## Beheerproces
Zodra een Open API standaard is ontwikkeld en goedgekeurd moet het worden overgedragen aan een beheerteam.
Voor die betreffende standaard wordt dat beheerteam daarna verantwoordelijk voor:
1. beantwoorden van vragen;
2. het oplossen van problemen.

Doorontwikkeling van de standaard hoort daar dus niet bij.

*Beantwoorden van vragen*
Voor het beantwoorden van vragen m.b.t. de betreffende standaard zijn twee kanalen beschikbaar. Ten eerste het specifiek voor de standaard beschikbaar gestelde kanaal in de Slack workspace [VNG API Community](https://vngapicommunity.slack.com) en ten tweede het eveneens specifiek voor de standaard beschikbaar gestelde GitHub/GitLab omgeving.

Slack leent zich niet zo goed voor het gestructureerd voeren van een discussie aangezien in het kanaal meerdere onderwerpen door elkaar heen kunnen gaan lopen en (in de basis variant) historie slechts tot een x aantal reacties beperkt blijft. Slack is vooral geschikt voor het snel stellen en beantwoorden van enkelvoudige vragen. Laagdrempelig contact dus.

Voor het diepgaand bediscusieren van issues en ter sprake stellen van problemen in de standaard waarbij de discussies een lange(re) tijd beschikbaar moeten blijven kan beter gebruik gemaakt worden van GitHub/GitLab.

Zodra het van belang is om een in Slack gevoerde discussie toch voor langere tijd te bewaren kunnen de beheerders de betreffende discussie alsnog onderbrengen in GitHub/GitLab waarna het evt. meteen aan de juiste persoon assigned kan worden. Indien de discussie vragen over het gebruik en toepassing van de standaard betreft dienen de beheerders zich steeds af te vragen of het niet beter is de documentatie van de standaard zo aan te passen dat eenzelfde vraag in de toekomst voorkomen wordt.

Vragen in beide kanalen moeten binnen xx dagen beantwoord zijn.

*Probleemoplossing*
De initiator voor probleemoplossing van een standaard is altijd een in GitHub/GitLab ingebracht issue. 
Indien het wijzigingsverzoek via Slack binnenkomt verzoekt de beheerder de persoon die het probleem heeft ingediend alsnog in GitHub/GitLab in te dienen. 

Na opvoering van het issue beoordeelt de beheerder of het een valide issue is. Indien dat niet het geval is wordt dat gemeld in het issue met de reden daarvoor waarna de melder enkele weken (_hoeveel?_) de tijd krijgt om de reden te weerleggen en zijn verzoek nog nader toe te lichten.

Indien het wel een valide issue is wordt gekeken of het een bug dan wel een feature betreft (_nog kijken naar de termen_).

Features worden niet door de beheerders opgepakt maar blijven staan totdat er een nieuw project wordt opgestart voor de doorontwikkeling van de standaard. Daar wordt besloten of het feature wordt meegenomen in de nieuwe versie van de standaard.
Beheerders geven in het feature wel aan hoe hoog naar hun mening de prioriteit is.

_Een feature is gebaseerd op een behoefte. In het geval van een probleem is er geen sprake van een gewijzigde behoefte maar slechts van een fout in de behoeftevoorziening of documentatie. Een feature kan dus nooit de basis zijn voor een patch. Patches zijn dus altijd gebasseerd op issues._

## Openen Slack kanaal
Het kunnen communiceren met stakeholders van een Open API standaard is belangrijk voor de kwaliteit van de Open API standaard. Het is tevens een manier om een zo hoog mogelijk draagvlak voor de Open API standaard te creeren. Daarom dient de project manager of scrum master bij de aanvang van een ontwikkelproject direct een Slack kanaal m.b.t. de Open API standaard binnen de VNG API Community workspace te (laten) creeren. Zo'n kanaal moet public zijn zodat geinteresseerden zelf kunnen bepalen of ze bijdragen willen posten in het kanaal.

Op GEMMA Online wordt op de pagina die gerelateerd is aan de Open API standaard een link opgenomen waarmee een geinteresseerde zich kan aanmelden voor de workspace waarna hij/zij zelf het gewenste kanaal aan zijn lijst met channels kan toevoegen.

Het Slack kanaal is overigens geen vervanging van het GEMMA Online discussieforum van de betreffende standaard. In Slack gebeurt het voeren van een discussie op een meer ongestructureerde wijze waardoor het terugvinden van een discussie lastig wordt. Daarnaast bewaart Slack in de standaard versie slechts een x-aantal laatste reacties waardoor historie langzaamaan wordt gewist. 

## Openen OpenAPI standaard pagina op GEMMA Online
Op [deze pagina](https://github.com/VNG-Realisatie/api-beheer/blob/master/doc/gemma_online.md) staat een voorzet van een algemene GEMMA Online API pagina. Wanneer deze voor akkoord bevonden wordt kan deze op GEMMA Online gepubliceerd worden.

## Openen GEMMA Online discussieforum
_nog in te vullen_

## Overdracht van backlog
Bij de overdracht van een standaard van ontwikkeling naar beheer moeten ook de nog in de backlog staande issues overgedragen worden. Dit gebeurt mondeling om de beheerders de gelegenheid te geven vragen te stellen over de issues. Zo moet o.a. duidelijk worden of er afspraken gemaakt zijn met de indiener van het issue m.b.t. de invulling van het issue in toekomstige versies van het koppelvlak.
Aangezien bij overdracht van ontwikkeling naar beheer de GitHub repository as-is wordt overgenomen kan de backlog zelf blijven waar deze is.

Overdracht van de backlog en GitHub repository is een officieel moment en moet plaatsvinden voordat er sprake kan zijn van in beheername van een Open API

## Werken met Docker

Zie https://docs.docker.com/get-started/ en specifiek https://docs.docker.com/get-started/part2/ en https://docs.docker.com/get-started/part3/ voor een diepere uitleg over Docker.

Voor het vervaardigen van Docker images heb je het volgende nodig:

* een goed werkende Docker installatie;
* een folder met daarin:
  - een Dockerfile (met de naam 'Dockerfile');
  - een repository met de applicatie (lokaal);
  - evt. een 'docker-compose.yml' file. Deze brengt meerdere Docker containers samen. Typisch voorbeeld is een database en een applicatie, elk hun eigen Docker.
* een account op 'hub.docker.com'

>_Om de build van de Docker files naar Dockerhub te kunnen pushen hebben we authorisatie nodig. Hetzelfde geldt voor de repository waar het te builden component staat._

In deze procedure is alleen een uitleg m.b.t. het beschikbaar stellen van Docker images en de configuratie daarvan in DocckerHub opgenomen. Het runnen van Docker containers behoort niet tot de scope van deze procedure. Dit betekent niet dat beheerders dat niet moeten kunnen. Dit is zeker van belang ter controle van de Docker image.

Als een bouwer een referentie implementatie of wijziging daarop aanlevert, gaat dat gepaard gaan met een Dockerfile. Het is dan aan beheer om daar (al dannietgeautomatiseerd) een built mee te maken. Voor de evt. 'docker-compose.yml' geldt hetzelfde.

>_In hoeverre Kubernetes nog een rol moet spelen binnen deze procedure is me op dit moment nog niet duidelijk. Vooralsnog heb ik Kubernetes dus buiten beschouwing gelaten._

Ga als volgt te werk:
1. Open een commandprompt menu en ga naar de folder waarin de applicatie staat;
2. Type in 'docker build -t [applicatie-naam] .' en enter. Er wordt nu een image gecreeerd;
3. Login op 'hub.docker.com' d.m.v. 'docker login'. Let op! Waar je in de browser omgeving als usernaam je emailadres gebruikt om in te loggen moet je hier echt je ID gebruiken;
4. Type 'docker tag [image-naam] [username]/[repo-name]:[tag]' en enter waarmee de image wordt voorbereid om naar de repository op docker hub te worden getransporteerd;
5. Type 'docker push [username]/[repo-name]:[tag]' en enter om de image daadwerkelijk op docker hub te plaatsen.
   De image kan nu door andere partijen worden gebruikt.

Indien scaling van belang is doe dan als volgt:
6. Creeer een 'docker-compose.yml' bestand met de gewenste content waaronder het aantal stacks;
7. Type 'docker swarm init';
8. Type 'docker stack deploy -c docker-compose.yml [applicatie-naam]' om de instellingen in de compose file te activeren;
9. Indien gewenst kan het aantal stacks on the fly gewijzigd worden in 'docker-compose.yml' en meteen geactiveerd worden door het commando in stap 8 weer opnieuw uit te voeren.

>_Ik vermoed dat stap 6 t/m 9 net door de beheerders wordt uitgevoerd maar alleen bij het runnen van de Docker containers. Indien dat het geval is dan kunnen deze stappen uit deze procedure worden verwijderd. Deze stappen moeten handmatig uitgevoerd kunnen worden maar zo mogelijk wordt dit geautomatiseerd._ 

**Enkele belangrijke Docker commando's**

Commando | Beschrijving 
--- | ---
docker build -t [applicatie-naam] . | Compile een image van de applicatie in de folder.
docker image ls | Lijst met alle lokale images.
docker images | idem.
docker images --all | Uitgebreide lijst met lokale images.
docker login | Login op docker hub. Let op! Waar je in de browser omgeving als usernaam je emailadres gebruikt om in te loggen moet je hier echt je ID gebruiken.
docker tag [image-naam] [username]/[repo-name]:[tag] | Koppelen van image aan te creeren docker hub repository.
docker push [username]/[repo-name]:[tag] | Publiceren van image op docker hub. Nu kan de applicatie overal gedraaid worden waar docker geinstalleerd is. Als hij niet lokaal aanwezig is wordt deze op docker hub gezocht.
docker run -p 4000:80 [image-naam] | start een lokale container running het image met de image-naam. Deze kan vervolgens gedraaid worden door http://localhost:4000. Je kunt uit de shell gaan d.m.v. CTRL+C.
docker run -d -p 4000:80 [image-naam] | start een lokale container running het image met de image-naam in background mode. Deze kan vervolgens gedraaid worden in een browser door http://localhost:4000. De shell wordt in dit geval meteen verlaten.
docker run -p 4000:80 [username]/[repository]:[tag] | Start een container vanaf de docker hub.
docker container ls | Lijst met alle lokale containers.
docker ps -a | idem.
docker container stop [container-id] | Stop de container met id.
docker rm [container-id] | Verwijder lokale container met id .
docker rmi [image-id] | Verwijder lokale image met id.
docker swarm init | Docker o.a. configureren voor het gebruik van een docker-compose file.
docker stack deploy -c docker-compose.yml getstartedlab | deploy de docer-compose.yml.
docker service ls | Haal de gegevens van de service.
docker service ps getstartedlab_web | Haal de gegevens op van alle tasks die de service draaien.
docker stack rm getstartedlab | Afsluiten van de applicatie.
docker swarm leave --force | Afsluiten van de swarm.
