# Standaard inrichting GitHub/GitLab

GitHub en GitLab repositories zijn langzamerhand de ruggegraat van ons werkproces. Voor bijna elk project is een GitHub en/of GitLab repository noodzakelijk.
Het aantal VNG Realisatie repositories kent inmiddels een behoorlijke omvang en is nog steeds groeiende. Met grote regelmaat wordt ons nl. gevraagd een nieuwe 
VNG Realisatie GitHub of GitLab repository te creëren. Het is dan ook niet verbazingwekkend dat er behoefte is aan een beschrijving van de wijze waarop zo'n 
VNG Realisatie repository moet worden aangemaakt. Dat zorgt er immers voor dat niets in de configuratie vergeten wordt maar kan er ook voor zorgen dat de 
VNG Realisatie repositories gelijkvormig zijn wat het  werken met deze repositories weer handiger maakt. Iemand die de ene VNG Realisatie repositorie kent kan 
zich in een andere repository immers ook al snel redden.

In dit document beschrijven we de wijze waarop GitHub en GitLab repositories moeten worden aangemaakt en geconfigureerd.

Alle VNG Realisatie GitHub repositories kunnen gevonden worden onder deze url: https://github.com/VNG-Realisatie.
Alle VNG Realisatie GitLab repositories kunnen gevonden worden onder deze url: https://gitlab.com/vng-realisatie.

## GitHub

Een aanvraag voor een nieuwe VNG Realisatie GitHub repository wordt altijd per mail ingediend en dient de volgende informatie te bevatten:
* Dat het om een GitHub repository gaat;
* De naam van de repository.
Denk hierbij niet alleen aan de semantische naam maar ook aan de technische naam (de naam zonder spaties) aangezien die in de url terug komt;
* Welke gebruikers 'toegang dienen te krijgen tot de repository.
Met per gebruiker diens GitHub gebruikersnaam;
* Welke rol deze gebruikers toegekend moeten krijgen (Read, Triage, Write of Maintain).

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

Doordat de repository 'Public' is, staat deze voor de gehele wereld op. Dat betekent dat de inhoud door de gehele wereld bekeken kan worden. Dat is 
precies zoals wij dat bij VNG Realisatie willen. Dat 

1. Ga naar het tabblad 'Settings' en klik op 'Manage access';
2. Voeg nu m.b.v. de bullet 'Invite teams or people' gebruikers toe. Je kunt hier dus kiezen voor individuele gebruikers of voor reeds aangemaakte teams. 
Indien je dat wil kan je er ook voorkiezen om eerst een nieuw team aan te maken;
3. Indien je op 'Invite teams or people' hebt geklikt kom je nu in een interface waarin je een gebruikersnaam of teamnaam in kunt geven;
4. Definiëer vervolgens de rol die de gebruiker of het team dient te krijgen (Read, Triage, Write of Maintain);
5. Klik vervolegns op de groene button 'Add xxxxx to the repository' waarna de gebruiker of team gebruik kan maken van de hem/hun toegekende rechten op de
repository.

### Initiële content

De repository is nu aangemaakt en kan nu (door de gebruikers) voorzien worden van content. 

De licentie tekst is voor elke VNG Realisatie GitHub repository gelijk en wordt daarom door de administrators aangemaakt.
1. Maak naast het README.md bestand een document aan met de naam 'LICENCE.md'.
2. Kopiëer de inhoud van een LICENCE.md bestand uit een andere VNG-Realisatie repository, plaats deze in het nieuwe bestand en commit het bestand direct
naar de 'main' branch.


### Initiële structuur

(bijv. t.b.v. GitFlow en GitHub Pages)

### Spectral rules

### GitHub Pages

## GitLab

### Initiële configuratie

### Gebruikers (autorisaties)

### Initiële content

### Initiële structuur???

### Spectral rules???

### GitHub Pages???

