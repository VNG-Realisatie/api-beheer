---
title: "Service Desk proces"
date: '17-6-2019'
weight: 100
---

*Versie 0.1*

## Service Desk proces.

In het onderstaande diagram is het Service Desk proces weergegeven zoals dit door API Beheer wordt gehanteerd.

![Service Desk](https://github.com/VNG-Realisatie/api-beheer/blob/master/Processen/ServiceDesk.jpg)

Het Service Desk proces beschrijft hoe een issue aangemeld kan worden en hoe dit dan verder verwerkt wordt door API Beheer.
Het kent de volgende subprocessen die in de documenten in de onderliggende links worden beschreven:
* [Change- en Problem Management API-Beheer](https://github.com/VNG-Realisatie/api-beheer/blob/master/Processen/CR-PR-API-Beheer.md)
* [Release Management API-Beheer](https://github.com/VNG-Realisatie/api-beheer/blob/master/Processen/RM-API-Beheer.md)
* [Change- en Problem Management API Testvoorziening](https://github.com/VNG-Realisatie/api-beheer/blob/master/Processen/CR-PR-ATV.md)
* [Release Management API Testvoorziening](https://github.com/VNG-Realisatie/api-beheer/blob/master/Processen/RM-ATV.md)
* [Change- en Problem Management Haven](https://github.com/VNG-Realisatie/api-beheer/blob/master/Processen/CR-PR-Haven.md)

De stappen in het Service Desk proces zijn genummerd met een uniek nummer en hieronder in meer detail beschreven.

| **Stap** | **Omschrijving** |
| -------- | ---------------- |
| **1.1** | Er wordt een issue ingebracht in GitHub. Dit kan als Userstory, Bug, Taak of ... zijn ingebracht. Een vraag kan ook een bug aan het licht brengen of aanleiding zijn voor een wens (1.18). In dat geval wordt eveneens een (nieuw) GitHub issue aangemaakt ook al was eerder voor de vraag al een GitHub issue ingebracht. In dat issue wordt dan een link naar de vraag geplaatst tenzij dat niet mogelijk is omdat de vraag in Redmine is ingebracht. |
| **1.2** | In het Slack-kanaal VNG API Community (vngapicommunity.slack.com) wordt melding gemaakt van een probleem of wens of er is een vraag gesteld. |
| **1.3** | Er wordt per e-Mail (standaarden.ondersteuning@vng.nl) een probleem of wens gemeld of er is een vraag gesteld. |
| **1.4** | Er wordt mondeling (via de telefoon of in de wandelgangen) melding gemaakt van een probleem of wens of er is een vraag gesteld. |
| **1.5** | API-Beheer beoordeelt of de melding een implementatie vraag (ga naar 1.7) is of juist een bug//wens (ga naar 1.18). |
| **1.6** | Bij een vraag wordt gekeken of discretie gewenst is (ga naar 1.7) of niet (ga naar 1.12). |
| **1.7** | Indien discretie gewenst is wordt de vraag in een afgesloten, niet-publieke omgeving (nu: Redmine) vastgelegd. Daarmee verzekeren we dat er een vervolgactie op de vraag wordt genomen zonder dat dit voor iedereen zichtbaar is. |
| **1.8** | Een vraag waarop discretie gewenst is wordt offline beantwoord. Dit kan telefonisch maar ook via e-Mail. Deze stap bestaat niet per definitie alleen uit het geven van een antwoord. Hij kan ook uitmonden in een correspondentie met de vraagsteller die pas eindigt als de vraag is beantwoord. |
| **1.9** | Betreft het een vraag die al vaker gesteld is en nog niet in een FAQ is opgenomen (ga naar 1.10) of niet (ga naar 1.11)? |
| **1.10** | Zo ja, dan wordt de vraag en het antwoord aan de FAQ toegevoegd. |
| **1.11** | Het issue wordt in de niet-publieke omgeving (nu: Redmine) gesloten. |
| **1.12** | Is voor een vraag geen discretie gewenst dan wordt gekeken of deze al vastgelegd is in Github (ga naar 1.14) of nog niet (ga nar 1.13). |
| **1.13** | Is de vraag nog niet vastgelegd in GitHub dan wordt de indiener van de vraag gevraagd dit alsnog te doen. |
| **1.14** | De vraag wordt op Github beantwoord. |
| **1.15** | Betreft het een vraag die al vaker gesteld is en nog niet in een FAQ is opgenomen (ga naar 1.16) of niet (ga naar 1.17)? |
| **1.16** | Zo ja, dan wordt de vraag en het antwoord aan de FAQ toegevoegd. |
| **1.17** | Het Github issue wordt afgesloten. |
| **1.18** | Komt er uit de vraag alsnog een bug of wens naar voren?. |
| **1.19** | Zo nee, dan is het proces afgesloten. |
| **1.20** | Bij een melding van een bug of wens wordt gekeken of deze al in Github is vastgelegd (ga naar 1.22) of nog niet (ga nar 1.21). |
| **1.21** | Zo niet dan wordt de indiener van de bug of wens gevraagd dit alsnog te doen. Dit verdient altijd de voorkeur zodat interpretatieverschillen worden voorkomen. Alleen als het echt niet anders kan zal het GitHub issue door API Beheer worden ingebracht. |
| **1.22** | Is het onderwerp van de bug of wens een API standaard of Referentie Implementatie (ga naar 1.23), de API Testvoorziening (ga naar 1.24) of is het Haven (ga naar 1.25)? |
| **1.23** | Indien het een API standaard of Referentie Implementatie betreft ga dan naar het subproces 'Change en Problem management API standaarden' [1]. |
| **1.24** | Indien het de API Testvoorziening betreft ga dan naar 'Change en Problem management API Testvoorziening' [2]. |
| **1.25** | In'dien het Haven betreft ga dan naar 'Change en Problem management Haven' [3]. |
