---
title: "Change- en Problem Management API-Beheer"
date: '17-6-2019'
weight: 100
---

*Versie 0.1*

## Change- en Problem Management API-Beheer

Het onderstaande diagram beschrijft hoe er wordt om gegaan met issues die in het Service Desk proces zijn binnen gekomen, van het type bug/wens zijn en als onderwerp een API standaard hebben.

![Change- en Problem Management API-Beheer](https://github.com/VNG-Realisatie/api-beheer/blob/master/Processen/CR-PR-API-Beheer.jpg)

De stappen in het Change- en Problem Management proces van API-Beheer zijn genummerd met een uniek nummer en hieronder in meer detail beschreven.

| **Stap** | **Omschrijving** |
| -------- | ---------------- |
| **2.1** | Vanuit het Service Desk proces komt een wens of bugmelding binnen. |
| **2.2** | API-Beheer beoordeelt of het gaat om een bug (ga naar 2.3) of om een wens (ga naar 2.16). |
| **2.3** | API-Beheer analyseert het probleem dat door de bug wordt veroorzaakt. Daarbij proberen ze o.a. het probleem te reproduceren. Zo nodig wordt er meer informatie opgehaald bij de persoon die de bug heeft gemeld. Dit kan via diverse media gaan maar altijd wordt hiervan rapportage gedaan in het betreffende GitHub issue. |
| **2.4** | API Beheer beoordeelt of het issue reeel (de oorzaak ligt bij de API standaard) en reproduceerbaar is (ga naar 2.5) of niet (ga naar 2.19). |
| **2.5** | Zo nodig wordt het issue beter beschreven zodat de kern van het probleem voor iedereen duidelijk is. Tevens wordt aangegeven hoe het probleem opgelost kan worden. Het issue wordt dus ready gemaakt. |
| **2.6** | Betreft het een kritisch probleem (ga naar 2.7) of niet (ga naar 2.9)? |
| **2.7** | Levert de oplossing van het probleem een probleem op met de backwardse compatibiliteit (ga naar 2.8) of niet (ga naar 2.9)? |
| **2.8** | API-Beheer laat het probleem z.s.m. oplossen door een ontwikkelaar. |
| **2.9** | API-Beheer prioriteert het issue en bepaald of het naar haar idee moet worden opgelost in de volgende release. |
| **2.10** | Is het belang laag en hoeft het niet mee in de komende sprint (ga naar 2.11), of is het hoog en moet het juist wel mee in de komende sprint (ga naar 2.25) of er is helemaal geen belang en is oplossing niet noodzakelijk (ga naar 2.18)? |
| **2.11** | Aan de melder van het probleem wordt teruggekoppeld dat het belang van het oplossen van het issue laag is en dat het niet op korte termijn wordt opgelost. |
| **2.12** | Het issue wordt in de product backlog geplaatst. |
| **2.13** | API-Beheer analyseert de wens. Zo nodig wordt er meer informatie opgehaald bij de persoon die de wens heeft opgevoerd. Dit kan via diverse media gaan maar altijd wordt hiervan rapportage gedaan in het betreffende GitHub issue. Indien bekend is dat de wens ook bj andere partijen leeft wordt dat ook vermeld. |
| **2.14** | Zo nodig wordt het issue beter beschreven zodat de kern voor iedereen duidelijk is. |
| **2.15** | Het issue wordt in de product backlog geplaatst. |
| **2.16** | De PO prioriteert het issue en bepaalt of het naar zijn/haar idee moet worden meegenomen in de volgende release. |
| **2.17** | Is het belang laag en hoeft het niet mee in de komende sprint (ga naar 2.22), of is het hoog en moet het juist wel mee in de komende sprint (ga naar 2.23) of er is helemaal geen belang en is implementatie niet noodzakelijk (ga naar 2.18)? |
| **2.18** | Aan de melder van het probleem wordt teruggekoppeld dat er geen belang is bij het oplossen van de bug of implementatie van de wens. | 
| **2.19** | Is de melder akkoord (ga naar 2.20) of juist niet (ga naar 2.21)? |
| **2.20** | Het issue wordt afgesloten in GitHub. |
| **2.21** | Er volgt een escalatie naar .... [**7**] |
| **2.22** | Aan de indiener van de wens wordt teruggekoppeld dat het belang van de implementatie laag is en dat het niet op korte termijn wordt geimplementeerd. |
| **2.23** | De PO bebaald of het issue al ready is (ga naar 2.25) of niet (ga naar 2.24)? |
| **2.24** | Indien het issue nog niet Ready is maakt de PO hem ready. |
| **2.25** | Het issue wordt geplaatst in de Release Backlog zodat er een overzicht is van alles wat mee moet in de komende release. |  
| **2.26** | De issues in de Release backlog worden meegenomen in het Scrum proces voor de nieuwe release. Dat betekent dat voor elke sprint in de backlog refinement wordt bepaald welke issues worden meegenomen. Het aantal sprints duurt in principe net zo lang als er nog issues in de Release backlog staan. |
| **2.27** | Er is een nieuwe API standaard release (ga naar [**4**](RM-API-Beheer.md)) en/of er zijn aangepaste testscripts (ga naar [**6**](RM-ATV.md)) | vervaardigd.
