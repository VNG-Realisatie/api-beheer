# Versie beheer en release management

## API versies

Versiebeheer is gebaseerd op [Semantic Versioning](https://semver.org) en de
[API strategie](https://aandeslagmetdeomgevingswet.nl/digitaal-stelsel/technisch-aansluiten/standaarden/api-uri-strategie/).
Elke  API heeft een eigen versienummer, opgebouwd uit `MAJOR.MINOR.PATCH` 
element. Bijvoorbeeld versie `2.1.8`:

Gegeven dit versienummer, elke ophoging van de:

* `MAJOR` versie betreft een *backwards-incompatible* API wijziging,
* `MINOR` versie betreft het toevoegen van een *backwards-compatible* API 
  wijziging,
* `PATCH` versie betreft het oplossen van *backwards-compatible* issues.

Verder wordt een aantal labels gebruikt, achter het versienummer:

* Als er geen aanduiding bij het versienummer staat, gaat het altijd om de
  meest actuele productie versie van de API.
* `supported` versies zijn oudere maar ondersteunde versies van de API,
* `archived` versies zijn oudere, niet meer ondersteunde versies van de API.

Voor meer interne doeleinden kennen we tenslotte nog de volgende labels achter
het versienummer:

* `RC` (Release Candidate) als de API versie feature-complete is. Alleen
  kritieke issues worden in deze versie nog verwerkt,
* `beta` als de versie gereed is voor testers en er geen grote wijzigingen meer
  verwacht worden. Alleen essentiele zaken worden in dit stadium nog 
  toegevoegd,
* `alpha` als de versie nog in ontwikkeling is en er geen enkele garantie is
  over de werking, stabiliteit e.d.

### Voorbeelden van backwards-incompatible wijzigingen

* Wijzigingen in de URL of fundamentale wijzigingen in de request/response
  schema's die bij een resource horen,
* Er is een data migratie nodig om van de vorige naar de nieuwe versie te komen.
  Bijvoorbeeld omdat een attribuut wordt opgesplitst in meerdere attributen, of
  juist worden samengevoegd,
* Verwijderen, hernoemen of type-wijziging van een attribuut, query parameter
  of header,
* Verwijderen of hernoemen van een resource of API als geheel,
* Toevoegen van een verplicht attribuut of header.

**LET OP: We spreken altijd over backwards-incompatible wijzigingen vanuit het 
provider perspectief! Een provider met API op versie `2.1.8` kan altijd goed
communiceren met een consumer die `2.0.0` t/m `2.1.8` praat (kortgezegd,
`2.x`) maar het is niet persé waar dat een consumer op versie `2.2.0` goed kan 
communiceren met een API op versie `2.1.8`.**

### Voorbeelden van backwards-compatible wijzigingen:

* Toevoegen van attributen die optioneel zijn, `null` mogen zijn of een andere
  standaard waarde hebben.
* Toevoegen van een element aan een enumeratie, 
_(we twijfelen er nog aan of dit wel een voorbeeld is  van een backwards-compatible wijziging. Daar moeten we dus nog naar kijken)_
* Een niet functionele wijziging in de documentatie,
* Wijzigingen in de volgorde van attributen.

### Implementaties door leveranciers

We onderscheiden een `consumer` en een `provider`. Een `consumer`, zoals een
taakapplicatie, maakt gebruik van de API's van een `provider`, zoals de Zaken
API en/of Documenten API.

Een leverancier implementeert bij voorkeur altijd de meest recente versie van
een API en zorgt dat haar provider software mee blijft lopen met de actuele 
versies die VNG aanbiedt, terwijl ook de door VNG ondersteunde versies blijven 
werken.

Volgens DSO API-24 hebben alle API's de `MAJOR` versie in de URL staan. Om de
exacte versie te weten wordt de volledige versie als header `API-version`
meegegeven in de response:

```
GET /api/v2/zaken/

HTTP 200
API-version 2.1.8
...
```

Als consumers geen versie meegeven in de header wordt de laatste versie 
gebruikt binnen de `MAJOR` versie die is opgegeven in de URL, zoals deze 
beschikbaar is bij de provider. Consumers kunnen wel een oudere versie afdwingen 
door deze versie mee te geven als header in het request.

*Voorbeeld*

Provider versie `2.1.8` die geen `1.x` ondersteund.

Consumer versie | Provider antwoord
--- | --- 
1.0.0 | Verzoek geweigerd, versie `1.x` wordt niet ondersteund
2.0.0 | Verzoek geaccepteerd, waarschuwing oude versie via header
2.1.0 | Verzoek geaccepteerd
2.1.8 | Verzoek geaccepteerd
2.2.0 | Verzoek geweigerd, versies hoger dan `2.1.x` worden niet ondersteund

### [WIP] Versie van de referentie implementatie vs versie van de API

De versie van de API loopt niet persé gelijk aan de versie van de referentie 
implementatie. Het is noodzakelijk dat de referentie implementatie aangeeft welke versie(s)
van de API (OAS) is geïmplementeerd.

*Voorbeeld*

* Zaken API referentie implementatie 1.0.0 (Zaken API 1.0.0)
* Zaken API referentie implementatie 1.0.1 (Zaken API 1.0.0)
  _Bugfix in de implementatie, geen effect op OAS, **de versies verschillen dus!**_
* Zaken API referentie implementatie 1.1.0 (Zaken API 1.1.0)
  _OAS minor update verwerkt in implementatie_
* Zaken API referentie implementatie 1.1.1 (Zaken API 1.1.1)
  _Patch in de OAS die ook in de referentie implementatie is verwerkt._

Het kan prima een patroon worden dat alleen de minor versie gaat verschillen 
tussen API en referentie implementatie.

TODO: Wellicht krijgen de referentie implementaties alleen het API-versienummer 
plus een buildnummer of commit hash. Zoiets als: 1.0.1-a6c319

### Voorbeeld van wijzigingen overzicht

Bij elke versie kunnen de wijzigingen worden opgenomen, als volgt:

1. Je kan de semantische wijzigingen bekijken in de [Changelog](https://github.com/maykinmedia/demo-api/blob/master/CHANGELOG.rst)
2. Je kan van elke versie apart de specificaties bekijken, zoals van [versie 1.0.0](https://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/maykinmedia/demo-api/1.0.0/openapi.yaml) en [versie 1.0.1](https://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/maykinmedia/demo-api/1.0.1/openapi.yaml)
3. Je kan versies van de specificatie echt met elkaar vergelijken ([bijvoorbeeld 1.0.0 vs 1.0.1](https://github.com/maykinmedia/demo-api/compare/1.0.0..1.0.1#diff-fe030a7c1568b3decf599edf399be7f4)): 

## Release management 

Een API zal nooit helemaal stabiel zijn. Verandering is onvermijdelijk. Het is 
belangrijk hoe met deze verandering wordt omgegaan. Goed gedocumenteerde en 
tijdig gecommuniceerde uitfaseringsplanningen zijn in het algemeen voor veel 
API gebruikers werkbaar.

TODO

### Standaard release schema

TODO

### Uitfaseren van een major API versie

TODO

### Ondersteuningsperiode

TODO: Zie API strategie 2.6.4

## API versies

Een overzicht van de huidige API versies binnen VNG.

### ZGW API's

Naam | Huidige versie | Ondersteunde versies
--- | --- | ---
Besluiten API | 1.0.0-alpha | [1.x][Besluiten-1.x]
Documenten API | 1.0.0-alpha | [1.x][Documenten-1.x]
Zaaktypen API | 1.0.0-alpha | [1.x][Zaaktypen-1.x]
Zaken API | 1.0.0-alpha | [1.x][Zaken-1.x]

[Besluiten-1.x]: https://ref.tst.vng.cloud/brc/api/v1/schema/
[Documenten-1.x]: https://ref.tst.vng.cloud/drc/api/v1/schema/
[Zaaktypen-1.x]: https://ref.tst.vng.cloud/ztc/api/v1/schema/
[Zaken-1.x]: https://ref.tst.vng.cloud/zrc/api/v1/schema/

### Bevragingen

Naam | Huidige versie | Ondersteunde versies
--- | --- | ---
Ingeschreven Personen API | 1.0.0-beta | [1.x][Ingeschreven Personen-1.x]

[Ingeschreven Personen-1.x]: https://rebilly.github.io/ReDoc/?url=https://raw.githubusercontent.com/VNG-Realisatie/Bevragingen-ingeschreven-personen/master/api-specificatie/Bevraging-Ingeschreven-Persoon/openapi.yaml

### Overige API's

Naam | Huidige versie | Ondersteunde versies
--- | --- | ---
Referentielijsten API | 1.0.0-alpha | [1.x][Referentielijsten-1.x]
Overige Registraties API | [1.0.0-alpha][Overige Registraties-1.x] | n.v.t.

[Referentielijsten-1.x]: https://ref.tst.vng.cloud/referentielijsten/api/v1/schema/
[Overige Registraties-1.x]: https://ref.tst.vng.cloud/orc/api/v1/schema/
