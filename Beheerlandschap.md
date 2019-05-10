---
title: "Beheer"
date: '10-5-2019'
weight: 100
---

*Versie 0.1*

## API Beheerlandschap

Het beheren van de API standaarden van VNG Realisatie behelst meer dan alleen het beheer van alle componenten in de GitHub omgeving van VNG Realisatie. Het landschap bevat meerdere omgevingen waar API Beheer een rol te spelen heeft. Naast de GitHub omgeving onderkennen we nog de volgende omgevingen:

- ref.tst.vng.cloud
- hub.docker.com
- API testvoorziening
- test.developer.overheid.nl

De relatie tussen deze omgevingen is gevisualiseerd in de onderstaande image:

![API Beheerlandschap](https://github.com/VNG-Realisatie/api-beheer/blob/melsk-r-beheerlandschap/API%20Beheerlandschap.jpg)

In GitHub bestaat voor elk registratie component een repository maar ook voor enkele andere componenten. Zo hebben we nog een repository voor 'Zaken volgens GEMMA 2.0' dat dient als portaal naar alle gerelateerde GitHub repositories.
Daarnaast bestaan er ook nog repositories voor de API testvoorziening, voor een tutorial over het werken met GitHub en voor API Beheer (waar dit document deel van uitmaakt).

Het daadwerkelijk vervaardigen van de API standaarden en coderen van de Referentie Implementaties gebeurd in de GitHub repositories van de registratiecomponenten.
Voor het publiekelijk kenbaar maken van de API standaarden en bijbehorende tooling zijn enkele andere omgevingen in gebruik.

Zo is er voor de API's in elk registratie component in de GitHub omgeving ook een duidelijke beschrijving opgenomen in de ref.tst.vng.cloud omgeving. 
https://ref.tst.vng.cloud/zrc/api/v1/schema/ bevat bijvoorbeeld informatie over alle API's in de zaakregistratiecomponent en https://ref.tst.vng.cloud/drc/api/v1/schema/ over alle API's in de documentregistratiecomponent. 
_TODO: beschrijven hoe deze omgeving precies technisch samenhangt met de GitHub omgeving. Wordt deze automatisch gegenereerd (bijv. middels een nightly build) en/of behoeft de creatie handmatige slagen._

Voor elke Referentie Implementatie die in GitHub is vervaardigd bestaat in hub.docker.com een docker file. Aangezien er voor elke registratie component een Referentie component is, is er ook voor elk registratie component een docker file.
Er zijn echter ook docker files voor enkele andere componenten. Bijv. voor de vng-referentielijsten, demo-api en  gemma-zaken-docs.
Op korte termijn zal de hub.docker.com omgeving worden vervangen door de Haven omgeving. T.z.t. zal een uitleg daarvan en van de (technische) relatie met de andere omgeving hier worden geplaatst.
_TODO: beschrijven hoe deze omgeving precies technisch samenhangt met de GitHub omgeving. Wordt deze automatisch gegenereerd (bijv. middels een nightly build) en/of behoeft de creatie handmatige slagen._

API testvoorziening: TODO (hoewel de API testvoorziening op dit moment draait in de hub.docker.com omgeving en in de toekomst in de Haven omgeving hebben we deze hier toch als een aparte omgeving neergezet.
Het is voor ons immers een omgeving de we apart moeten gaan beheren en configureren.)
_TODO: beschrijven hoe deze omgeving precies technisch samenhangt met de GitHub omgeving. Wordt deze automatisch gegenereerd (bijv. middels een nightly build) en/of behoeft de creatie handmatige slagen._

test.developer.overheid.nl: TODO
_TODO: beschrijven hoe deze omgeving precies technisch samenhangt met de GitHub omgeving. Wordt deze automatisch gegenereerd (bijv. middels een nightly build) en/of behoeft de creatie handmatige slagen._

Aangezien GEMMA Online voor velen de ingang is naar meer informatie over de VNG Realisatie standaarden is er in die omgeving ook voorzien in informatie over de API standaarden.
Dit is echter tot een minimum beperkt, vanuit GEMMA Online wordt slechts globale informatie verstrekt over deze standaarden en voor meer informatie wordt daar verwezen naar de ref.tst.vng.cloud omgeving.








