---
title: Week 7
date: '2019-03-31'
---

## Dag 1:

Aangezien veel van de grote gedeeltes van de GraphQL transformatie compleet waren, kon er al een gekeken worden om de applicatie op de staging-omgeving te plaatsen. Hiervoor moesten natuurlijk wel alle testen lukken, en er waren nog enkele die bij die onopgeloste errors gaven.

Zo gaf Jest errors over het inladen van de Postgraphile plugins nadat de testomgeving afgebroken was. Hierover was weinig documentatie over te vinden op het internet, dus moest er stap voor stap getroubleshoot worden op welke testen de code juist faalde. Uiteindelijk kwam de oplossing bij het hoofd testbestand. In deze index.js werd na de testen de databank migrations volledig gewist zonder te wachten op eventuele verandering van buitenaf. Aangezien de Postgraphile plugins met webhooks werkten werden deze pas ingeladen nadat de testomgeving afgesloten was. Omdat zij de databank nodig hadden om de GraphQl API op te starten, moest er hier simpel weg nog een beforeAll en afterAll toegevoegd worden om het wissen tegen te gaan.

## Dag 2:

Een ander probleem dat nog moest opgelost worden, was een best-practice die beschreven stond in de Postgraphile documentatie. Postgraphile doet automatisch al checks om te kijken of alle foreign key indexes aanwezig zijn en geeft warnings wanneer dit niet zo is. Deze foreign keys worden niet automatisch door Postgres aangemaakt, dus deze moeten manueel nog met migrations toegevoegd worden. Deze indexes hebben als impact dat Postgres veel sneller data kan opzoeken doordat hij de verschillende relaties kent. Naast het schrijven van een extra migration, werd er ook een extra test geschreven, die ook checkt of alle foreign indexes aanwezig zijn.

## Dag 3:

Dag 3 was ik afwezig op de stage vanwege ziekte.

## Dag 4:

Voordat de applicatie op staging geplaatst zou worden, moest de GraphQl route ook nog toegevoegd worden aan de custom JWT-middleware. Hiervoor was dit niet het geval, omdat anders grafische interfaces zoals Graphiql of een programma zoals Postman zeer moeilijk te gebruiken werden. Er zou immers elke keer een Authentication Bearer token moeten toegevoegd worden. Nu dat de implementatie zo ver als gedaan was, kon er gekeken worden om de JWT-middleware toe te voegen. Het was even opzoeken hoe Postgraphile dit precies kon verwerken, maar na het implementeren kon vanaf nu enkel mensen die ingelogd zijn, en dus een JWT token hebben, effectief de GraphQL API aanspreken.
