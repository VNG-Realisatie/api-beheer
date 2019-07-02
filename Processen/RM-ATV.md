---
title: "Release Management API-Testvoorziening"
date: '17-6-2019'
weight: 100
---

*Versie 0.1*

## Release Management API-Testvoorziening

In het onderstaande diagram wordt beschreven hoe wordt omgegaan met een nieuwe release van de API-Testvoorziening. Welke handelingen moeten in dat geval worden uitgevoerd.

![Release Management API-Testvoorziening](https://github.com/VNG-Realisatie/api-beheer/blob/master/Processen/RM-ATV.jpg)

De stappen in het Release Management proces vande API Testvoorziening zijn genummerd met een uniek nummer en hieronder in meer detail beschreven.

| **Stap** | **Omschrijving** |
| -------- | ---------------- |
| **5.1** | Vanuit het Release Management API standaarden proces komen een of meer nieuwe testscrips binnen. |
| **5.2** | De testscripts worden geconfigureerd in de API Testvoorziening.  |
| **5.3** | De regressietest wordt opnieuw geconfigureerd. |
| **5.4** | Vanuit het Change en Problem Management API standaarden komen een of meer nieuwe testscenario's of aangepaste testscripts binnen of komt een verzoek tot verwijdering van een testscript binnen. |
| **5.5** | Betreft het een nieuw testscenario (ga naar 5.6) of niet (ga naar 5.7). |
| **5.6** | Voeg de nieuwe testscenario('s) toe aan de bestaande testset. |
| **5.7** | Moet er een testscript worden vervangen (ga naar 5.8) of niet (ga naar 5.9). |
| **5.8** | Vervang de bestaande testscripts door de nieuw ontvangen. |
| **5.9** | Moeten er testscripts verwijderd worden (ga naar 5.10) of niet (ga naar 5.11). |
| **5.10** | Verwijder de betreffende testscripts. |
| **5.11** | Pas de regressietest aan. |
| **5.12** | Draai de regressietest zodat deze weer de laatste status weergeeft. |
| **5.13** | Is de test geslaagd (keer terug naar 3.4 indien binnen gekomen via 5 (Release Management API standaarden) of beeindig het proces indien binnengekomen via 6 (Change en Problem Management API standaarden) of niet (ga naar 5.14). |
| **5.14** | Er is een probleem met de nieuwe componenten of met de API Testvoorziening zelf. Maak een issue aan voor het API scrum team of voor API Testvoorziening Beheer. |
