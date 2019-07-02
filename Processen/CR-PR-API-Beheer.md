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
| **2.2** | API-Beheer beoordeelt of het gaat om een bug (ga naar 2.5) of om een wens (ga naar 2.3). |
| **2.3** | API-Beheer analyseert de wens. Zo nodig wordt er meer informatie opgehaald bij de persoon die de wens heeft opgevoerd. Dit kan via diverse media gaan maar altijd wordt hiervan rapportage gedaan in het betreffende GitHub issue. Indien bekend is dat de wens ook bij andere partijen leeft wordt dat ook vermeld. |
| **2.4** | Zo nodig wordt het issue beter beschreven zodat de kern voor iedereen duidelijk is. |
| **2.5** | API-Beheer analyseert het probleem dat door de bug wordt veroorzaakt. Daarbij proberen ze o.a. het probleem te reproduceren. Zo nodig wordt er meer informatie opgehaald bij de persoon die de bug heeft gemeld. Dit kan via diverse media gaan maar altijd wordt hiervan rapportage gedaan in het betreffende GitHub issue. |
| **2.6** | API Beheer beoordeelt of het issue reeel (de oorzaak ligt bij de API standaard) en reproduceerbaar is (ga naar 2.7) of niet (ga naar 2.14). |
| **2.7** | Zo nodig wordt het issue beter beschreven zodat de kern van het probleem voor iedereen duidelijk is. |
| **2.8** | Betreft het een kritisch probleem (ga naar 2.9) of niet (ga naar 2.11)? |
| **2.9** | Levert de oplossing van het probleem een probleem op met de backwardse compatibiliteit (ga naar 2.10) of niet (ga naar 2.11)? |
| **2.10** | API-Beheer laat het probleem z.s.m. oplossen door een ontwikkelaar. |
| **2.11** | Het issue wordt in de product backlog geplaatst. |
| **2.12** | De issues in de Product backlog worden meegenomen in het Scrum proces voor de nieuwe release. Dat betekent dat voor elke sprint in de backlog refinement wordt bepaald welke issues worden meegenomen. Het scrum-team bepaalt in overleg met de PO en API-Beheer welke issues mee moeten gaan in de volgende release en hoeveel sprints nodig zijn om die release te vervaardigen. Indien een issue niet wordt meegenomen in de komende release dan wordt dat teruggekoppeld naar de melder. |
| **2.13** | Er is een nieuwe API standaard release (ga naar [**4** Release Management API Beheer](RM-API-Beheer.md)) en/of er zijn aangepaste testscripts (ga naar [**6** Release Management API Testplatform](RM-ATV.md)) |
| **2.14** | Aan de melder wordt teruggekoppeld dat zijn issue wordt afgevoerd met de reden daarvan. |
| **2.15** | Is de melder akkoord (ga naar 2.16) of juist niet (ga naar 2.17)? |
| **2.16** | Het issue wordt afgesloten in GitHub. |
| **2.17** | Er volgt een escalatie naar .... [**7**] (nog in te vullen). |
