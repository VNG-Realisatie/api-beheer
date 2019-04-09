# Werken met Docker
Onderstaande uitleg is bedoeld voor het gebruik van Docker in de API beheer situatie.

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
