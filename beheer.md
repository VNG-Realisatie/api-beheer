---
title: "Beheer"
date: '10-12-2018'
weight: 100
---

*Versie 0.1*

## Inleiding

In dit document worden allerlei procedures en overzichten beschreven die van belang zijn bij het in beheer nemen dan wel het uitvoeren van het beheer van een standaard.

## Inhoudsopgave

- [Lijst van deelnemende partijen en personen](#lijst-van-deelnemende-partij-en-personen)
- [Overdracht van backlog](#overdracht-van-backlog)
- [Werken met Docker](#werken-met-docker)

## Lijst van deelnemende partijen en personen
Bij de ontwikkeling van Open API standaarden nemen diverse partijen deel. Het is handig voor ontwikkelaars maar ook voor beheerders om daar een overzicht van te hebben. Daarom dient de project manager of scrum master bij de aanvang van een ontwikkelproject maar ook tijdens het project als de teamsamenstelling wijzigt de [lijst met Deelnemende partijen](https://github.com/VNG-Realisatie/api-beheer/blob/master/Deelnemende%20partijen.md) in te vullen. Ook de beheerder of beheerders van de standaard moeten na in beheername van een standaard of bij wijziging van de beheerder op deze lijst worden vermeldt.

## Overdracht van backlog
Bij de overdracht van een standaard van ontwikkeling naar beheer moeten ook de nog in de backlog staande issues overgedragen worden. Dit gebeurd mondeling om de beheerders de gelegenheid te geven vragen te stellen over de issues. Zo moet o.a. duidelijk worden of er beloftes gedaan zijn naar de indiener van het issue m.b.t. de invulling van het issue in toekomstige versies van het koppelvlak.
Aangezien bij overdracht van ontwikkeling naar beheer de GitHub repository as-is wordt overgenomen kan de backlog zelf blijven waar deze is.

Overdracht van de backlog en GitHub repository is een officieel moment en moet plaatsvinden voordat er sprake kan zijn van in beheername van een Open API

## Werken met Docker

Zie https://docs.docker.com/get-started/ en specifiek https://docs.docker.com/get-started/part2/ en https://docs.docker.com/get-started/part3/ voor een diepere uitleg over Docker.

Voor het vervaardigen van Docker images heb je het volgende nodig:

* een goed werkende Docker installatie;
* een folder met daarin:
  - een Dockerfile (met de naam 'Dockerfile');
  - een requirements file (met de naam requirements.txt);
  - een python applicatie;
  - evt. een 'docker-compose.yml' file.
* een account op 'hub.docker.com'

>_Hebben we ook authorisatie nodig op hub.docker.com om de docker files in de juiste repository weg te kunnen schrijven?_

In deze procedure is alleen een uitleg m.b.t. het beschikbaar stellen van Docker images en de configuratie daarvan in DocckerHub opgenomen. Het runnen van Docker containers behoort niet tot de scope van deze procedure. Dit betekent niet dat beheerders dat niet moeten kunnen. Dit is zeker van belang ter controle van de Docker image.
Tevens ga ik er vanut dat de 'Dockerfile' aangeleverd wordt en (voorlopig) niet hoeft te worden gewjzigd. ndien dat wel het geval is moet ook daar vaardigheid in worden opgedaan. Voor de evt. 'docker-compose.yml' geldt hetzelfde.
In hoeverre Kubernetes nog een rol moet spelen binnen deze procedure is me op dit moment nog niet duidelijk. Vooralsnog heb ik Kubernetes dus buiten beschouwing gelaten.

Ga als volgt te werk:
1. Open een commandprompt menu en ga naar de folder waarin de python applicatie staat;
2. Type in 'docker build -t [applicatie-naam] .' en enter. Er wordt nu een image gecreeerd;
3. Login op 'hub.docker.com' d.m.v. 'docker login'. Let op! Waar je in de browser omgeving als usernaam je emailadres gebruikt om in te loggen moet je hier echt je ID gebruiken;
4. Type 'docker tag [image-naam] [username]/[repo-name]:[tag]' en enter waarmee de image wordt voorbereid om naar de repository op docker hub te worden getransporteerd;
5. Type 'docker push [username]/[repo-name]:[tag]' en enter om de image daadwerkelijk op docker hub te plaatsen.
   De image kan nu door andere partijen worden gebruikt.

Indien scalling van belang is doe dan als volgt:
6. Creeer een 'docker-compose.yml' bestand met de gewenste content waaronder het aantal stacks;
7. Type 'docker swarm init';
8. Type 'docker stack deploy -c docker-compose.yml [applicatie-naam]' om de instellingen in de compose file te activeren;
9. Indien gewenst kan het aantal stacks on the fly gewijzigd worden in 'docker-compose.yml' en meteen geactiveerd worden door het commando in stap 8 weer opnieuw uit te voeren.

>_Ik vermoed dat stap 6 t/m 9 net door de beheerders wordt uitgevoerd maar alleen biij het runnen van de Docker containers. indien dat het geval is dan kunnen deze stappen uit deze procedure worden verwijderd._ 

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
