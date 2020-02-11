# Checklist van activiteiten en vereiste onderdelen voor het in beheer nemen van een standaard.

De vereiste onderdelen zijn aanwezig:
* [ ] OAS3/yaml; 
* [ ] De Github repositories, inclusief de backlog;
* [ ] Referentie Implementatie (RI) als docker container;
* [ ] Documentatie, functioneel en technisch, geschikt voor verschillende soorten gebruikers;
* [ ] Overzicht van de business logica;
* [ ] Overzicht compatibiliteit met welke versies van andere standaarden;
* [ ] Wijzigingenoverzicht per versie;
* [ ] Overzicht van de betrokken partijen en personen;
* [ ] Testomgeving met testscripts.
* [ ] Demo/test applicatie consumer moet aanwezig zijn.
* [ ] Slack workspaces en en andere communicatie middelen die gebruikt worden tijdens het (door)ontwikkelen moeten overgedragen worden aan VNG.

* [ ] Er moet een productowner per API standaard zijn. Hetzij extern (vanuit ontwikkelteam) hetzij intern (VNG) 
* [ ] Afstemming met stakeholders


## OAS3/Yaml
* [ ] MUST OAS publiek toegankelijk 
* [ ] MUST OAS voldoet aan landelijke API strategie => momenteel geen mogelijkheid dit te controleren, issue/vraag van maken voor Henri
* [ ] MUST OAS foutloos leesbaar in Swaggerhub/Redoc => Joeri vraag stellen wat verschil is tussen Redoc en Swaggerhub. Ook vraag wat "beter is" en waarom. Kunnen Redoc en Swaggerhub een aanvulling op elkaar zijn? Zijn er nog alternatieven? We willen niet teveel tools voor deze controle hoeven te gebruiken.
* [ ] => issue aanmaken, meer mensen vragen of er nog zaken van belang zijn bij de OAS? Johan, Joeri, Sergei, Henri, Hugo, Roderick


## Github repositories
* [ ] MUST Github ontwikkel repositorie voor standaard voor admin toegankelijk
* [ ] MUST Github ontwikkel repositorie voor referentie implementatie voor admin toegankelijk
* [ ] MUST Admin rechten op ontwikkelrepositories, bv voor bepalen prioriteiten doorontwikkeling=> Joeri vragen beheerrechten op demo repos
* [ ] MUST Geen openstaande PR's meer (werk aan de over te dragen versie is afgerond)
* [ ] SHOULD Projectstructuur, wel moet duidelijk zijn wat is backlog, wat is onderhanden/huidige sprint (moet leeg zijn) en wat is afgerond
* [ ] Wat doen we met branches die tijdens het ontwikkelen ontstaan zijn?

## Backlog
* [ ] Backlog opgenomen in de ontwikkel-repositories
* [ ] 

## Referentie Implementatie provider
* [ ] MUST Github repositorie(s) overgedragen => Of opnemen RI in aparte beheer-repository?
* [ ] MUST De RI mag geen fouten/foutmeldingen geven => Foutmeldingen in Github, compileerfouten?, Fouten in Docker container?
* [ ] MUST Geen openstaande bugs/werkzaamheden voor de over te dragen versie
* [ ] MUST Referentie implementatie gelijk aan de OAS3 => hoe controleren we dit? BV importeren OAS in Postman en genereren testscript om te testen tegen RI. Dan is aangetoond dat de OAS van de standaard ondersteund wordt door de RI. Amdere mogelijkheid is exporteren OAS uit RI en vergelijken met OAS van standaard.
* [ ] MUST RI is beschikbaar als een docker container.
* [ ] MUST RI is centraal gehost op Haven.

## Referentie implementatie consumer
* [ ] MUST Github repositorie(s) overgedragen => Of opnemen RI in aparte beheer-repository?
* [ ] MUST De RI mag geen fouten/foutmeldingen geven => Foutmeldingen in Github, compileerfouten?, Fouten in Docker container?
* [ ] MUST Geen openstaande bugs/werkzaamheden voor de over te dragen versie
* [ ] MUST RI Consumer moet matchen met de RI van de provider


## Documentatie
* [ ] MUST Technische documentatie compleet
* [ ] MUST Functionele documentatie compleet
* [ ] MUST Informatiemodel van de API beschreven en voorzien van UML model/diagram
* [ ] MUST Een pagina op GEMMA Online

## voorwaarden waarop afgeweken kan worden van de eisen/criteria
* [ ] TODO: beschrijven wat de procedure is om ondanks afwijkingen een standaard toch in beheer te kunnen nemen.
* [ ] Beschrijven wat te doen wanneer afwijkingen niet opgelost worden binnen afgesproken termijn

## Overzicht van de business logica
* [ ] MUST beschrijving van relaties, afhankelijkheden, processen etc. zoals beschreven in de user stories en/of in de informatie modellen

## Overzicht compatibiliteit met welke versies van andere standaarden
* [ ] MUST Overzicht compatibiliteit met andere (voorgaande) versies van de eigen standaard
* [ ] MUST Overzicht compatibiliteit met versies van andere standaarden 


## Wijzigingenoverzicht per versie
* [ ] MUST moet er zijn

## Overzicht van de betrokken partijen en personen;
* [ ] MUST volgens template


## Testomgeving met testscripts.
* [ ] MUST Testscenario's (inclusief testdata) moeten aanwezig zijn
* [ ] MUST De testscenarios moeten aantoonbaar correct uitgevoerd kunnen worden
* [ ] MUST De testscenarios (inclusief testdata en procesflow) moeten gedocumenteerd zijn


## Eén van de beheerders moet eigenaar van de API standaard zijn.
* [ ] MUST => Verantwoordelijkheden vastleggen

## Afstemming met stakeholders
* [ ] MUST Werkgroepstructuur? Issues, RFC's etc. indienen via Github. Monitoring van de community, contactpersoon voor doorontwikkeling developers
* [ ] MUST roadmap
* [ ] MUST evangeliseren naar gemeentes toe
* [ ] MUST Demo's en API Labs/hackaton (virtueel?) bij een nieuwe versie
