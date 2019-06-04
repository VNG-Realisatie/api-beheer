---
title: "Beheer"
date: '10-5-2019'
weight: 100
---

*Versie 0.1*

## API Beheerlandschap

Het beheren van de API standaarden van VNG Realisatie behelst meer dan alleen het beheer van alle componenten in de GitHub omgeving van VNG Realisatie. Het landschap bevat meerdere omgevingen waar API Beheer een rol te spelen heeft of waarin anderen wijzigingen aan moeten brengen n.a.v. wijzigingen in de andere omngevingen. Naast de GitHub omgeving onderkennen we nog de volgende omgevingen:

- ref.tst.vng.cloud
- hub.docker.com
- API testvoorziening
- test.developer.overheid.nl
- www.softwarecatalogus.nl

De relatie tussen deze omgevingen is gevisualiseerd in de onderstaande image:

![API Beheerlandschap](https://github.com/VNG-Realisatie/api-beheer/blob/master/API%20Beheerlandschap.jpg)

In GitHub bestaat voor elke API een repository maar ook voor enkele andere componenten. Zo hebben we nog een repository voor 'Zaken volgens GEMMA 2.0' dat dient als portaal naar alle gerelateerde GitHub repositories.
Daarnaast bestaan er ook nog repositories voor de API testvoorziening, voor een tutorial over het werken met GitHub en voor API Beheer (waar dit document deel van uitmaakt).

Het daadwerkelijk vervaardigen van de API standaarden en coderen van de Referentie Implementaties gebeurt in de GitHub repositories van de API's.
Voor het publiekelijk kenbaar maken van de API standaarden en bijbehorende tooling zijn de volgende omgevingen in gebruik:

* Zo is er voor elke API in de GitHub omgeving ook een duidelijke beschrijving opgenomen in de ref.tst.vng.cloud omgeving.
https://ref.tst.vng.cloud/zrc/api/v1/schema/ bevat bijvoorbeeld informatie over alle API's in de zaakregistratiecomponent en https://ref.tst.vng.cloud/drc/api/v1/schema/ over alle API's in de documentregistratiecomponent. Deze omgeving wordt ook door API Beheer beheerd.
_TODO: beschrijven hoe deze omgeving precies technisch samenhangt met de GitHub omgeving. Wordt deze automatisch gegenereerd (bijv. middels een nightly build) en/of behoeft de creatie handmatige slagen._

* Voor elke Referentie Implementatie die in GitHub is vervaardigd bestaat in hub.docker.com een docker file. Aangezien er voor elke API een Referentie component is, is er ook voor elke API een docker file.
Er zijn echter ook docker files voor de volgende componenten: vng-referentielijsten, demo-api en  gemma-zaken-docs.
Op korte termijn zal de hub.docker.com omgeving worden vervangen door de Haven omgeving. T.z.t. zal een uitleg daarvan en van de (technische) relatie met de andere omgeving hier worden geplaatst. Ook voor deze omgevng geldt dat deze wordt beheerd door API Beheer.
_TODO: beschrijven hoe deze omgeving precies technisch samenhangt met de GitHub omgeving. Wordt deze automatisch gegenereerd (bijv. middels een nightly build) en/of behoeft de creatie handmatige slagen._

* API testvoorziening: 
_TODO: beschrijven hoe deze omgeving precies technisch samenhangt met de GitHub omgeving. Wordt deze automatisch gegenereerd (bijv. middels een nightly build) en/of behoeft de creatie handmatige slagen._
Hoewel de API testvoorziening op dit moment draait in de hub.docker.com omgeving en in de toekomst in de Haven omgeving hebben we deze hier toch als een aparte omgeving neergezet. Het is immers een omgeving die API Beheer apart moet beheren en configureren.
LET OP! API Beheert slechts de configuratie van de testscripts van de API standaarden die zij beheert. API Beheer beheert dus niet de API testvoorziening zelf.

* developer.overheid.nl is een portaal waar ontwikkelaars informatie kunnen vinden over alle API's die in overheidsland gebruikt worden. Beheerders van overheids API's melden zelf hun eigen API's aan en beheren die aanmeldingen ook zelf.

* Aangezien GEMMA Online voor velen de ingang is naar meer informatie over de VNG Realisatie standaarden is er in die omgeving ook voorzien in informatie over de API standaarden.
Dit is echter tot een minimum beperkt, vanuit GEMMA Online wordt slechts globale informatie verstrekt over deze standaarden en voor meer informatie wordt daar verwezen naar de ref.tst.vng.cloud omgeving.

Tenslotte speelt ook de softwarecatalogus (SWC) binnen het API Beheerlandschap een rol. De SWC is een product van en voor gemeenten die helpt het applicatielandschap in beeld te brengen. De API's maken daar ook deel van uit en moeten dus in de SWC binnen dit landschap geconfigureerd kunnen worden. Beheer van de SWC is geen verantwoordelijkheid van API Beheer maar API Beheer zal de beheerders van de SWC wel van informatie moeten voorzien zodat zij de configuratie kunnen regelen. 

Daarnaast kan het zijn dat, zoals met het StUF TestPlatform, de resultaten van de testen op de API TestVoorziening moeten worden ingelezen in de SWC. Die relatie is echter nog niet helder.







