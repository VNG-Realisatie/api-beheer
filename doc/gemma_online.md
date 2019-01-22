## GEMMA Online API pagina
Onderstaande tekst zou een basis kunnen vormen voor een inleidende pagina op http://gemmaonline.nl/ over de API standaarden voor de Common ground.


Met de <a href="https://vng.nl/samen-organiseren/common-ground">Common Ground</a> en de bijbehorende, andere manier waarop de gemeentelijke ICT-systemen opnieuw georganiseerd worden zijn ook nieuwe uitwisselingsstandaarden nodig. Gegevens worden niet meer en masse gesynchroniseerd maar opgehaald bij de bron op het moment dat ze nodig zijn. De technieken die hiervoor nodig zijn vereisen een andere soort uitwisselingsstandaarden.

Deze nieuwe uitwisselingsstandaarden zijn niet alleen technisch anders van opzet, ze worden ook volgens het Common Ground principe door gemeenten zelf stapsgewijs opgezet en ingevuld naar behoefte. Op basis van zgn. user stories wordt beschreven welke functionele wensen gemeenten hebben die door een standaard ondersteund moet worden.

Een user story is een korte beschrijving (story) van wat een gebruiker (user) wil. User stories worden gebruikt bij het ontwikkelen van software of producten. Een user story bestaat uit enkele zinnen gewone spreektaal van de (computer)gebruiker waarin staat wat de gebruiker doet of moet doen, als onderdeel van z'n werk. (bron: https://nl.wikipedia.org/wiki/User_story) 

Door in korte, heldere taal een wens te beschrijven en deze in te vullen sluit de standaard naadloos aan op de behoeften van gemeenten zonder dat er overbodige functionaliteit en techniek opgenomen wordt. Voor leveranciers is het daarom ook helder waar de standaard voor dient en hoe deze toegepast dient te worden.

Naast gebruik van user stories worden standaarden ook agile ontwikkeld. In plaats van een langdurig ontwikkelproces wordt een onderdeel van een standaard in een korte cyclus uitgewerkt en afgestemd met de gebruikers. 

### Transparantie
De API standaarden worden volledig transparant en openbaar ontwikkeld. Alle user stories, documentatie, broncode, ontwerpen en andere zaken worden in een openbare Github repository vastgelegd. Daar kunnen belanghebbenden ook zelf userstories en bevindingen doorgeven die door het ontwikkelteam besproken, beoordeeld en opgepakt kunnen worden. 


### Zaakgericht Werken
De eerste standaard die op deze manier wordt ontwikkeld is een groep standaarden ter ondersteuning van het <a href="https://www.gemmaonline.nl/index.php/Thema_Zaakgericht_werken">Zaakgericht Werken</a>. De opvolger van de <a href="https://www.gemmaonline.nl/index.php/Zaak-_en_Documentservices">Zaak- Documentservices</a>, een op <a href="https://www.gemmaonline.nl/index.php/Sectormodel_Zaken:_StUF-ZKN">StUF ZKN</a> gebaseerde koppelvlakstandaard, is opgezet volgens de <a href" https://www.gemmaonline.nl/index.php/GEMMA_Architectuur">GEMMA 2</a> referentie architectuur. 

De Github repository waar deze standaard in ontwikkeld wordt staat hier: <a href="https://github.com/vng-realisatie/gemma-zaken">https://github.com/vng-realisatie/gemma-zaken</a>. De Github repository is dus een ontwikkelomgeving. De versie van de standaard in ontwikkeling zoals die getoond wordt tijdens een sprint demo staat op een aparte omgeving welke te vinden is op <a href="https://ref.tst.vng.cloud/">https://ref.tst.vng.cloud/</a>.

De volgende referentie componenten zijn (vooralsnog) onderdeel van de Zaakgericht Werken standaard:
<ul>
<li><a href="https://ref.tst.vng.cloud/standaard/apis/zrc">Zaakregistratie component</a></li>
<li><a href="https://ref.tst.vng.cloud/standaard/apis/drc">Documentregistratie component</a></li>
<li><a href="https://ref.tst.vng.cloud/standaard/apis/ztc">Zaaktypecatalogus</a></li>
<li><a href="https://ref.tst.vng.cloud/standaard/apis/brc">Besluitregistratie component</a> (nieuw geidentificeerd en toegevoegd op basis van de user stories)</li>
</ul>

Daarnaast is als <a href="https://nl.wikipedia.org/wiki/Mock-up">mockup</a> het <a href="https://ref.tst.vng.cloud/standaard/apis/overige">Overigeregistratiecomponent (ORC)</a> gemaakt, bedoeld voor die gegevens die wel in de user story thuis horen maar niet in het RGBZ opgenomen zijn. Hiermee is het mogelijk om de andere registratiecomponenten met bijbehorende API's die nog niet gerealiseerd zijn te simuleren en zo een user story te kunnen realiseren.


