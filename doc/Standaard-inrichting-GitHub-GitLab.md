# Standaard inrichting GitHub/GitLab

GitHub en GitLab repositories zijn langzamerhand de ruggegraat van ons werkproces. Voor bijna elk project is een GitHub en/of GitLab repository noodzakelijk.
Het aantal VNG Realisatie repositories kent inmiddels een behoorlijke omvang en is nog steeds groeiende. Met regelmaat wordt ons gevraagd een nieuwe 
VNG Realisatie GitHub of GitLab repository te creëren. Er is daarom behoefte aan een beschrijving van de wijze waarop zo'n 
VNG Realisatie repository moet worden aangemaakt of voorzien van extra functionaliteit. Dat zorgt er immers voor dat niets in de initiële configuratie vergeten wordt en dat de VNG Realisatie repositories gelijkvormig zijn wat het  werken met deze repositories weer handiger maakt. Iemand die de ene VNG Realisatie repositorie kent kan zich in een andere repository immers ook al snel redden.

In dit document beschrijven we de wijze waarop GitHub en GitLab repositories moeten worden aangemaakt, geconfigureerd en van extra functionaliteit kunnen worden voorzien.

Alle VNG Realisatie GitHub repositories kunnen gevonden worden onder deze url: https://github.com/VNG-Realisatie.
Alle VNG Realisatie GitLab repositories kunnen gevonden worden onder deze url: https://gitlab.com/vng-realisatie.

## GitHub

Een aanvraag voor een nieuwe VNG Realisatie GitHub repository wordt altijd per mail ingediend en dient de volgende informatie te bevatten:
* Dat het om een GitHub repository gaat;
* De naam van de repository.
Denk hierbij niet alleen aan de semantische naam maar ook aan de technische naam (de naam zonder spaties) aangezien die in de url terug komt;
* Of het een private of een public repository moet zijn;
* Welke gebruikers toegang dienen te krijgen tot de repository.
Met per gebruiker diens GitHub gebruikersnaam;
* Welke rol deze gebruikers toegekend moeten krijgen:
  * **Read**<br/>aanbevolen voor gebruikers die de code slechts willen bekijken en willen deelnemen aan de discussies.
  * **Triage**<br/>aanbevolen voor gebruikers die issues, discussies en pull request willen beheren zonder schrijfrechten.
  * **Write**<br/>aanbevolen voor gebruikers die actief willen bijdragen aan een project.
  * **Maintain**<br/>aanbevolen voor project managers die het beheer over een repository willen uitvoeren zonder daarbijtoegang te hebben tot gevoelige of zelfs destructieve acties.
  * **Admin**<br/>aanbevolen voor gebruikers die volledige toegang moeten hebben tot een project inclusief gevoelige of zelfs destructieve acties zoals het beheren van de beveiliging en het verwijderen van een repository.
* Of er op basis van de repository (later) ook een GitHub Pages site moet worden gegenereerd.
* Of het gebruik van GitFlow gewenst is.
* Of er voorzien moet worden in standaard issue templates en zo ja welke.
* Of er voorzien moet worden in een standaard PR template.

### Initiële configuratie

1. Open het [VNG Realisatie GitHub domein](https://github.com/VNG-Realisatie);
2. Klik op de groene 'New' button;
3. Geef in het veld 'Repository name' de gewenste repository naam in;
4. Stel de repository als 'Public' in;
5. selecteer de optie 'Add a README file'. Er wordt dan een standaard README.md bestand aangemaakt waarvan de content later kan worden aangebracht;
Bij VNG Realisatie nemen wij altijd zo'n bestand op;
6. We creëren niet standaard een licentie bestand en ook geen .gitignore;
7. Klik op 'Create repository'.

### Gebruikers (autorisaties)

Doordat de repository 'Public' is, staat deze voor de gehele wereld open. Dat betekent dat de inhoud door de gehele wereld bekeken kan worden. Dat is ook
precies zoals wij dat bij VNG Realisatie willen. 

1. Ga naar het tabblad 'Settings' en klik op 'Manage access';
2. Voeg nu m.b.v. de bullet 'Invite teams or people' gebruikers toe. Je kunt hier dus kiezen voor individuele gebruikers of voor reeds aangemaakte teams. 
Indien je dat wil kan je er ook voor kiezen om eerst een nieuw team aan te maken;
3. Indien je op 'Invite teams or people' hebt geklikt kom je nu in een interface waarin je een gebruikersnaam of teamnaam in kunt geven;
4. Definiëer vervolgens de rol die de gebruiker of het team dient te krijgen (Read, Triage, Write of Maintain);
5. Klik vervolgens op de groene button 'Add xxxxx to the repository' waarna de gebruiker of team gebruik kan maken van de hem/hun toegekende rechten op de
repository.

### Initiële content

De repository is nu aangemaakt en kan nu (door de gebruikers) voorzien worden van content. 

De licentie tekst is voor elke VNG Realisatie GitHub repository gelijk en wordt daarom al door de administrators aangemaakt.
1. Maak naast het README.md bestand een document aan met de naam 'LICENCE.md'.
2. Kopiëer de inhoud van een LICENCE.md bestand uit een andere VNG-Realisatie repository, plaats deze in het nieuwe bestand en commit het bestand direct
naar de 'main' branch.


### Initiële structuur

We streven er binnen de VNG-Realisatie GitHub repositories naar overal een gelijke structuur te hanteren. Het gaat daarbij niet alleen over de folder structuur maar ook over de branch structuur. E.e.a. is nog wel afhankelijk van de functie van de repository. Zo wordt niet elke repository gebruikt t.b.v. een API specificatie en in dat geval is de folder 'specificatie' natuurlijk niet nodig. Wordt de repository echter wel gebruikt met als doel om een API specificatie op te leveren dan staat die specificatie wel in de folder 'specificatie'. 

#### Folder structuur

Hieronder een tabel met daarin de standaard folder en daarachter de conditie.

| Foldernaam | Conditie |
| --- | --- |
| specificatie | Alleen opnemen als  het doel of een van de doelen van de repository is het opleveren van een API- of anderssoortige specificatie.|
| docs | Deze folder is alleen noodzakelijk als het de bedoeling is om op basis van de respository ook een GitHub Pages site te genereren. Meestal is dit een repository die pas op een later moment aangemaakt zal hoeven te worden aangezien de content voor een GitHub Pages site eerst zal moeten worden vervaardigd. |
| .github/ISSUE_TEMPLATE | Wordt alleen aangemaakt als er behoefte is aan 1 of meer templates voor het aanmaken van GitHub issues. |
| .github/PULL_REQUEST_TEMPLATE | Wordt alleen aangemaakt als er behoefte is aan 1 of meer templates voor het aanmaken van GitHub Pull Requests. |
| .github/workflows | Wordt alleen aangemaakt indien de repository moet worden voorzien van action scripts. |

In deze tabel zijn de folders die door Action scripts worden gegenereerd niet opgenomen juist omdat ze gegenereerd worden en niet door de administrators aangemaakt hoeven te worden.

1. Maak de folders aan die voor de repository wenselijk zijn.

#### Branch structuur

Bij de branch structuur gaat het vooral om de voor de branches gehanteerde naamgeving aangezien er geen branches binnen branches kunnen voorkomen. In principe staat het iedereen vrij om die branch structuur te hanteren die men wenselijk acht. Als er men echter gebruik wil maken van de GitFlow workflow zijn er wel enkele regels die in acht genomen moeten worden. Voor meer informatie over de toepassing verwijs ik naar [de beschrijving van GitFlow in onze API Kennisbank](https://github.com/VNG-Realisatie/API-Kennisbank/blob/master/GitFlow/Gitflow_implementatie.md).

In de 'master' (of 'main') branch wordt standaard bij het aanmaken van de repository al voorzien. Het aanmaken van 'Feature' branches wordt door de developers in de repository zelf geregeld. Daarmee blijft de volgende door de administrator uit te voeren actie over:

1. Maak, idien het werken volgens Gitflow gewenst is, de branch 'develop' aan.

### Issue templates

De inhoud van een repository is over het algemeen het resultaat van een samenwerking van meerdere personen. Sommige personen bouwen daadwerkelijk aan de content anderen reviewen of dragen bij door wensen kenbaar te maken. Opmerkingen en wensen m.b.t. de content worden meestal kenbaar gemaakt middels zogenaamde issues. Issues kunnen veel vormen aannemen, bijv. als 'Improvement story', 'Bug report' of als een eenvoudige 'taak'. Elk van deze issuesoorten heeft zijn eigen karakter wat zich vertaald in de informatie die moet worden verstrekt. Om er voor te zorgen dat bij elk type issue de gewenste informatie ook wordt verstrekt kunnen issue templates worden aangemaakt. De naam van zo'n template verschijnt dan als keuzemogelijkheid op het moment dat een nieuw issue wordt aangemaakt.

Hiertoe dient in de folder '.github' de folder 'ISSUE_TEMPLATE' aangemaakt te worden. De markdown bestanden die in deze folder worden geplaatst zullen de issue templates vormen. In de onderstaande tabel benoemen we de meest gebruikelijke templates en hun functies. De betreffende bestanden kun je [hier](https://github.com/VNG-Realisatie/api-beheer/tree/master/doc/issue-templates) vinden.

| Template | Functie |
| --- | --- |
| Bug-report.md | Template om een bug in het bestaande product te kunnen melden. |
| Enhancement.md | Template om een voorstel tot verbetering van het materiaal in de repository te kunnen doen. |
| Impediment.md | Template waarmee een belemmering onder de aancht kan worden gebracht. |
| Improvement-story.md | Template waarmee alles wat in een sprint niet goed ging kan worden gemeld, dit kan dan worden aangepakt zodat het team leert hoe zichzelf te verbeteren en er in volgende Sprints niet dezelfde fouten worden gemaakt. |
| Scrumtaak.md | Template waarmee een taak (zijnde geen user- en improvement story) kan worden opgevoerd die door het team moet worden opgepakt, bijv. het voorbereiden van een demo. |
| User-story--als-----wil-ik----.md | Template waarmee een feature/user story dat men graag in het product opgenomen zou zien kan worden beschreven. |
| Vraag.md | Template voor het stellen van vragen over onderwerpen die verband houden met het materiaal in de onderliggende repository. |

1. Maak, indien gewenst en als deze nog niet aanwezig is, de folder '.github/ISSUE_TEMPLATE' aan;
2. Plaats alle templates die gewenst zijn in deze folder;
3. Templates zijn direct bruikbaar.

### Pull Request templates

Indien gewenst kunnen er, net als voor de verschillende soorten issues, templates voor Pull Requests worden aangemaakt. Op dit moment kent alleen de gemma-zaken repository zo'n template (spec-wijziging.md), zie daarvoor de [gemma-zaken repository](https://github.com/VNG-Realisatie/gemma-zaken/tree/master/.github/PULL_REQUEST_TEMPLATE). Daar is het handig omdat in die context voor een PR standaard informatie verstrekt moet kunnen worden, bijv. over de relatie van het PR met andere ZGW API standaarden.

1. Maak, indien gewenst en als deze nog niet aanwezig is, de folder '.github/PULL_REQUEST_TEMPLATE' aan;
2. Plaats het template in die folder (de gebruikers kunnen deze zelf aanpassen aan hun wensen);
3. Templates is direct bruikbaar.

### Standaard labels

Een eenduidige werkwijze vertaalt zich ook naar de op de issues en PR's toe te passen labels.
Natuurlijk vult elke repository de behoefte van zijn gebruikers zo goed mogelijk in wat kan betekenen dat er een aantal specifiek in de betreffende repository worden aangemaakt. Over het algemeen kennen de repositories echter wel een aantal labels die het gemeen heeft met andere repositories en idealiter hebben deze over de verschillende repositories eenzelfde kleur. In de onderstaande tabel zijn een aantal van deze labels opgenomen met de daarbij horende hexadecimale waarde van de kleur.

| Labelnaam | Beschrijving | Kleur |
| --- | --- | --- |
| bug | Fout in de code.  | #d73a4a |
| user story | Business vraag van een gemeentelijke afnemer. | #82f2cb |
| vraag |  | #d876e3 |
| v1.0 |  | #b030db |
| v1.1 |  | #704bea |
| v1.2 |  | #e5ca60 |
| v1.3 |  | #bfd4f2 |
| v1.4 |  | #3A7D4B |
| v2.0 |  | #3e83c4 |
| documentation | Verbeteringen of toevoegingen aan de documentatie. | #0075ca |
| wontfix | Dit wordt niet opgelost. | #ffffff |

### Initiële opzet project structuur

Als administrator voorzien we niet in een standaard project structuur. Zo'n structuur zal door (een van) de administrators van de repository moeten worden opgebouwd.
Voor voorbeelden van zo'n structuur verwijzen we naar de andere repositories in de GitHub organisatie [VNG-Realisatie](https://github.com/VNG-Realisatie).

Over het algemeen wordt echter altijd wel voorzien in de volgende kolommen:
* Backlog
* In progress
* Done

### Geautomatiseerde functies

M.b.v. geautomatiseerde functies kunnen we acties automatisch laten uitvoeren op basis van het voorkomen van een event, bijv. het wijzigen van een status.
Bij '[Configuring automation for project boards](https://docs.github.com/en/github/managing-your-work-on-github/configuring-automation-for-project-boards)' vind je meer informatie.

#### Plaats issues in kolom project board

Zodra een issue de status 'closed' krijgt dient deze over het algemeen ook verplaatst te worden naar de kolom 'Done' van het project board. Dit kan je op de volgende wijze regelen:

1. Op het betreffende projectboard;
2. Klik in de kolom waarvoor je een functie wil automatiseren op '...';
3. Klik op 'Manage automation';
4. Selecteer een 'Preset' die je de geautomatiseerde functie geeft die je wil gebruiken;
5. Vink de actie aan die je wil automatiseren.

### Standaard Actions

Binnen Haal Centraal zijn een aantal Action scripts ontwikkeld die ook bruikbaar kunnen zijn in andere repositories. Over het algemeen zal de behoefte aan deze script pas naar voren komen zodra de repository voldoende content heeft. Hier hoeft dus niet al meteen bij het initiëel aanmaken in te worden voorzien. Hieronder kort een overzicht van de beschikbare actions en een korte beschrijving van de functionaliteit.

| Actionnaam | Beschrijving |
| --- | --- |
| lint-oas | Valideert de OAS specificatie en genereert indicatoren die gebruikt kunnen worden om het resultaat van de analyse visueel te maken. |
| generate-sdks | Genereert op basis van OAS specificatie SDK packages en genereert indicatoren die gebruikt kunnen worden om het resultaat van de generatie visueel te maken. |
| generate-postman-collection | Genereert op basis van OAS specificatie postman scripts en genereert indicatoren die gebruikt kunnen worden om het resultaat van de generatie visueel te maken. |
| generate-user-stories-md | Genereert t.b.v. de GitHub Pages site markdown bestanden met daarin de user stories die al ingevuld zijn met een in productie versie en user stories die ingevuld worden in de in ontwikkeling versie. Om de juiste issues te kunnen tonen zal het script steeds aangepast moeten worden na het uitkomen van een nieuwe in productie versie en/of in ontwikkeling versie. |

Voor de ins & outs m.b.t. de voor VNG-R beschikbare actions en de wijze waarop deze geactiveerd kunnen worden in de respositories verwijzen we naar [de uitleg daarover in de API-Kennisbank](https://github.com/VNG-Realisatie/API-Kennisbank/tree/master/GitHub%20Actions).

#### Spectral rules

Zoals je in [lint-oas](https://github.com/VNG-Realisatie/API-Kennisbank/blob/master/GitHub%20Actions/haal-centraal.md#lint-oas) sectie kunt lezen wordt er bij het valideren de openapi specificatie gebruik gemaakt van Spectral. De gebruikte OAS rules staan dan ook gedefinieerd in het .spectral.yml bestand. Meer daarover kun je vinden in ['Valideren van de openapi.yaml en de genereervariant van de openapi.yaml bestand' in Haal Centraal npm beheer](https://github.com/VNG-Realisatie/API-Kennisbank/blob/master/GitHub%20Actions/haal-centraal-npm-beheer.md#valideren-van-de-openapiyaml-en-de-genereervariant-van-de-openapiyaml-bestand).

### GitHub Pages

Zodra het product waarvoor de repository in het leven is geroepen een bepaalde status heeft kan de behoefte ontstaan om het met GitHub Pages te publiceren.
Meer informatie over het activeren van GitHub Pages specifiek voor VNG Realisatie vind je in [de GitHub Pages sectie van de API Kennisbank](https://github.com/VNG-Realisatie/API-Kennisbank/blob/master/GitHub%20Pages/GitHub-Pages-implementatie-VNG-R.md).

## GitLab

### Initiële configuratie

### Gebruikers (autorisaties)

### Initiële content

### Initiële structuur???

### Spectral rules???

### GitHub Pages???

