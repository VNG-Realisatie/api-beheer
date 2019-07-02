---
title: "Release Management API-Beheer"
date: '17-6-2019'
weight: 100
---

*Versie 0.1*

## Release Management API-Beheer

In het onderstaande diagram wordt beschreven hoe wordt omgegaan met een nieuwe release van een API standaard en/of Referentie Implementatie. Welke handelingen moeten er in dat geval worden uitgevoerd.

![Release Management API-Beheer](https://github.com/VNG-Realisatie/api-beheer/blob/master/Processen/RM-API-Beheer.jpg)

De stappen in het Release Management proces van API-Beheer zijn genummerd met een uniek nummer en hieronder in meer detail beschreven.

| **Stap** | **Omschrijving** |
| -------- | ---------------- |
| **3.1** | Vanuit het Change- en Problem Management API-Beheer proces komt een nieuwe release voor de API standaard en/of Referentie Implementatie binnen. |
| **3.2** | Zijn er naast de nieuwe OAS3 standaard en/of Referentie Implementatie ook nieuwe testscripts (ga naar 3.3) of niet (ga naar 3.4).  |
| **3.3** | Ga naar [**5** Release Management API Testplatform](RM-ATV.md). |
| **3.4** | API-Beheer test of de Docker containers inderdaad vervangen zijn en of deze correct werken. |
| **3.5** | API-Beheer checkt of de documentatie daar waar dat n.a.v. de aangebrachte wijzigingen nodig is ook is aangepast. |
| **3.6** | API-Beheer voert indien nodig aanpassingen uit op de gegevens van de betreffende API op developer.overheid.nl |
| **3.7** | API-Beheer past indien nodig GEMMA Online aan. |
| **3.8** | Voor elke opgeloste bug geeft API-Beheer een terugkoppeling naar de melder van het probleem. Ook iedereen die een wens heeft aangebracht die in de release is opgenomen ontvangt een terugkoppeling. |
| **3.9** | De beschikbaarheid van de nieuwe release wordt bekend gemaakt door middel van: |
|  | * Een nieuwsbericht in de VNG Realisatie Nieuwsbrief. |
|  | * De Slack community. |
|  | * GEMMA Online. |
|  | * VNG Realisatie website. |
