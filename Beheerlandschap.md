---
title: "API Beheerlandschap"
date: '10-5-2019'
weight: 100
---

*Versie 0.1*

## API Beheerlandschap

Het beheren van de API standaarden van VNG Realisatie behelst meer dan alleen het beheer van alle componenten in de GitHub omgeving van VNG Realisatie. Het landschap bevat meerdere omgevingen waar API Beheer een rol te spelen heeft of waarin anderen wijzigingen aan moeten brengen n.a.v. aanpassingen in een of meer van deze omgevingen. Naast de GitHub omgeving onderkennen we nog de volgende omgevingen:

- ref.tst.vng.cloud
- hub.docker.com
- API testvoorziening
- test.developer.overheid.nl
- JWT generator
- www.softwarecatalogus.nl
- GEMMA Online

De relatie tussen deze omgevingen is gevisualiseerd in de onderstaande image:

![API Beheerlandschap](https://github.com/VNG-Realisatie/api-beheer/blob/master/API%20Beheerlandschap.jpg)

Voor elke API bestaat in GitHub een repository (soms bevat een repository zelfs meerdere API's). Ook voor enkele andere componenten bestaan echter repositories. Zo hebben we nog een repository voor 'Zaken volgens GEMMA 2.0' dat dient als portaal naar alle gerelateerde GitHub repositories.
Daarnaast bestaan er ook nog repositories voor de API testvoorziening, voor een tutorial over het werken met GitHub en voor API Beheer (waar dit document deel van uitmaakt).

Het daadwerkelijk vervaardigen van de API standaarden en realiseren van de Referentie Implementaties gebeurt in de GitHub repositories van de API's. De andere omgevingen spelen een andere rol. Hieronder beschrijven we die rol en de relatie tussen die omgevingen.
* In de ref.tst.vng.cloud omgeving wordt algemene informatie m.b.t. de Zaakgericht werken API's ter beschikking gesteld zoals de context waarbinnen en de wijze waarop de API's zijn ontwikkeld. Daarnaast bevat het echter ook documentatie over de inhoudelijke/technische kant van de API's. Zo bevat 
https://ref.tst.vng.cloud/zrc/api/v1/schema/ bijvoorbeeld inhoudelijk/technische informatie over de zaakregistratiecomponent API en https://ref.tst.vng.cloud/drc/api/v1/schema/ over de documentregistratiecomponent API.<br/><br/>De algemene informatie wordt direct vanuit GitHub m.b.v. scripts in het tool Hugo gegenereerd (pijl 1 in het bovenstaande diagram). 
De inhoudelijk/technische documentatie wordt vanuit de docker images in hub.docker.com/u/vngr gegenereerd (pijl 10). Daarmee wordt gewaarborgd dat de documentatie in ref.tst.vng.cloud altijd in sync loopt met de laatste versie van de gepubliceerde docker bestanden. De bron daarvoor isn echter ook de GitHub omgeving wat betekent dat de GitHub omgeving in feite de content management omgeving is voor ref.tst.vng.cloud.<br/><br/>Deze omgeving wordt door API Beheer beheerd.<br/><br/>
* Voor elke Referentie Implementatie die in GitHub is vervaardigd bestaat in hub.docker.com een docker file. Aangezien er voor elke API een Referentie component is, is er ook voor elke API een docker file. De docker files worden vanuit GitHub gegenereerd (pijl 2).<br/><br/>_Er zijn echter ook docker files voor de volgende componenten: vng-referentielijsten, demo-api en  gemma-zaken-docs._<-- Zijn hiervoor dan geen RI's?<br/><br/>Ook voor deze omgeving geldt dat deze wordt beheerd door API Beheer.<br/><br/>
* API testvoorziening:<br/> 
Hoewel de API testvoorziening op dit moment draait in de hub.docker.com omgeving en in de toekomst in de Haven omgeving hebben we deze hier toch als een aparte omgeving neergezet. Het is immers een omgeving die API Beheer apart moet beheren en configureren.<br/><br/>
De testvoorziening maakt gebruik van de docker files die beschikbaar worden gesteld via hub.docker.com. Dit kan op 3 manieren. Ten eerste kan de ATV gebruik maken van de docker files (pijl 12) via ref.tst.vng.cloud (pijl 11), dit is de default. Het gevolg is dan wel dat alle data die in deze docker worden geplaatst zichtbaar ook is voor anderen. De kans dat hier junk bij zit is redelijk groot aangezien deze wijze ook gebruikt wordt voor het leren omgaan met de API's. De ATV kan echter ook direct gebruik maken van de docker files op hub.docker.com (pijl 8). Daarbij heeft men volledige controle over de data. Dit zal een gebruiker zelf moeten configureren. Tenslotte kan de ATV nog gebruik maken van docker files die lokaal bij de gebruiker waardoor men nog meer controle heeft (niet uitgewerkt in het overzicht). Zo kan men er voor kiezen om een eigen applicatie aan de ATV te hangen en zo de werking van deze applicatie te testen.<br/><br/>
Bij elke API standaard worden ook de bijbehorende testscripts ontwikkeld. De bron van deze scripts staan in GitHub en deze scripts moeten in de ATV geconfigureerd worden (pijl 3).<br/><br/>
**LET OP!** API Beheer beheert slechts de gebruikersadministratie en de configuratie van de testscripts van de API standaarden die zij beheert. API Beheer beheert dus niet de API testvoorziening zelf.<br/><br/>
* ref.tst.vng.cloud/tokens is een tool waarmee een JWT token kan worden gegenereerd dat kan worden gebruikt in de ATV. Daartoe moet het in de ATV (pijl 9) en in ref.tst.vng.cloud (pijl 7) worden geconfigureerd. De configuratie in de ATV betreft een copy en past slag, de configuratie in ref.tst.vng.cloud is echter onderhevig aan authorisaties. Vandaar dat er voor gekozen is die rechten aan het tool toe te kennen. Configuratie kan dus alleen via het tool. API Beheer heeft verder geen rol bij het configureren. In de situatie dat men de ATV gebruikt met een directe koppeling naar Hub.docker.com of een lokale docker file kan men er overigens voor kiezen om een eigen token te gebruiken.<br/><br/>
* developer.overheid.nl is een portaal waar ontwikkelaars informatie kunnen vinden over alle API's die in overheidsland gebruikt worden. Beheerders van overheids API's melden zelf hun eigen API's aan en beheren die aanmeldingen ook zelf (pijl 4). Daarbij wordt een link gelegd naar de met de API gerelateerde informatie in ref.tst.vng.cloud (lijn 5).<br/><br/>
* Aangezien GEMMA Online voor velen de ingang is naar meer informatie over de VNG Realisatie standaarden is er in die omgeving ook voorzien in informatie over de API standaarden. Dit is echter tot een minimum beperkt, vanuit GEMMA Online wordt slechts globale informatie verstrekt over deze standaarden en voor meer informatie wordt daar verwezen naar de ref.tst.vng.cloud omgeving (lijn 6).<br/><br/>GEMMA Online is eveneens in beheer bij API Beheer.<br/><br/>
* Tenslotte speelt ook de softwarecatalogus (SWC) binnen het API Beheerlandschap een rol. De SWC is een product van en voor gemeenten die helpt het applicatielandschap in beeld te brengen. De API's maken daar in principe ook deel van uit en zouden dus ook in de SWC binnen dit landschap geconfigureerd moeten kunnen worden. Op dit moment is nog niet duidelijk of de SWC daarvoor gebruikt gaat worden.<br/>Hoe dan ook, beheer van de SWC is geen verantwoordelijkheid van API Beheer maar API Beheer zal de beheerders van de SWC wel van informatie moeten voorzien zodat zij de configuratie kunnen regelen.<br/><br/>Daarnaast kan het zijn dat, zoals met het StUF TestPlatform, de resultaten van de testen op de API TestVoorziening moeten worden ingelezen in de SWC. Die relatie is echter nog niet helder.
