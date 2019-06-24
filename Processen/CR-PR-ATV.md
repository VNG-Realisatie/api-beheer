---
title: "Change- en Problem Management API-Testvoorziening"
date: '17-6-2019'
weight: 100
---

*Versie 0.1*

## Change- en Problem Management API-Testvoorziening

Het onderstaande diagram beschrijft hoe er wordt om gegaan met issues die in het Service Desk proces zijn binnen gekomen, van het type bug/wens zijn en als onderwerp de API Testvoorziening hebben.

![Change- en Problem Management API-Beheer](https://github.com/VNG-Realisatie/api-beheer/blob/master/Processen/CR-PR-ATV.jpg)

De stappen in het Change- en Problem Management proces van de API-Testvoorziening zijn genummerd met een uniek nummer en hieronder in meer detail beschreven.

| **Stap** | **Omschrijving** |
| -------- | ---------------- |
| **4.1** | Vanuit het Service Desk proces komt een wens of bugmelding binnen. |
| **4.2** | API-Beheer beoordeelt of het gaat om een Operationeel probleem (ga naar 4.3) of om een wens (ga naar 4.13). |
| **4.3** | API-Beheer analyseert het probleem (opnieuw). |
| **4.4** | Is het probleem reproduceerbaar (ga naar 4.7) of niet (ga naar 4.5). |
| **4.5** | Is er een verklaring waarom het probleem niet reproduceerbaar is (ga naar 4.12) of niet (ga naar 4.13). |
| **4.6** | Zit het probleem in een of meer API Testscripte (ga naar 4.7) of niet (ga naar 4.8). |
| **4.7** | Ga naar subproces [**1**](CR-PR-API-Beheer.md). |
| **4.8** | Is het probleem zelf op te lossen (ga naar 4.9) of niet (ga naar 4.13). |
| **4.9** | API-Beheer lost het probleem op. |
| **4.10** | API-Beheer meldt aan de indiener van het probleem dat het probleem is opgelost en vraagt de indiener of dat naar wens is. |
| **4.11** | Is het probleem naar wens opgelost (ga naar 4.12) of niet (ga naar 4.3). |
| **4.12** | Het issue wordt gesloten. |
| **4.13** | Het issue wordt doorverwezen naar ATV-beheer. |
