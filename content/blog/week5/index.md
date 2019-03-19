---
title: Week 5
date: '2019-03-17'
---

## Dag 1-2:

Het begin van deze week stond nog steeds in thema van het verder implementeren van de GraphQL API in de frontend. Wanneer deze automatisch gegenereerde queries en mutations geïmplementeerd waren, kon er doorgegaan worden naar de volgende stap.

## Dag 3:

Dankzij Postgraphile konden we een hele hoop queries en mutations genereren zonder ooit zelf een resolver te schrijven. Maar natuurlijk kan Postgraphile niet alles voor ons doen. Sommige requests vragen dat bepaalde operaties in bulk gebeuren, zoals wanneer 1 mutation meerdere gegevens zal aanmaken. Of wanneer er velden verwacht worden die niet in Postgraphile ondersteund worden, zoals het gebruiken van een UUID als primary key. Hiervoor moeten we dus kijken om eigen resolvers toe te voegen aan onze reeds bestaande GraphQL API.

Dag 3 bestond uit het opzoeken van verschillende mogelijkheden hoe we dit het beste konden aanpakken. Een paar mogelijkheden waren:

-   Een Apollo Server opzetten, waar we zelf resolvers konden aanmaken. Vervolgens zou deze met behulp van Schema Stitching gecombineerd kunnen worden aan onze Postgraphile GraphQL API.
-   Postgres functies schrijven in SQL, zodat Postgraphile deze kan interpreteren en vervolgens queries en mutations kan aanmaken.
-   Gebruik maken van Postgraphile zijn makeExtendSchemaPlugin, een module waarmee we queries of mutations kunnen extenden, of gewoon nieuwe toevoegen.

De eerste methode zou met de Apollo Server nog een extra abstractie bovenop onze code geven, die we zouden moeten onderhouden en leren, wat niet ideaal was. De tweede methode waarin we pure Postgres functies zouden moeten schrijven, is weinig intuïtief en zou te veel logica in onze databank stoppen.
De derde methode laat ons toe om Postgraphile op een eenvoudige manier aan te vullen met onze eigen resolvers, door gewoon plugins toe te voegen die we zelf schrijven.

## Dag 4:

Op deze dag werd voor de eerste keer gekeken naar het aan de praat krijgen van een makeExtendSchemaPlugin. Hiervoor moest er een typedef geschreven worden, die zegt welke query of mutation er extend moet worden, en ook een resolver, waarin onze eigenlijke logica zit waar eer data opgehaald of weggeschreven wordt. Hier kon er op de reeds bestaande controllers gemakkelijk ingespeeld worden.

Postgraphile werkt intern met een zeer extensieve en ingewikkelde manier, om relaties tussen data te weten te komen en op deze manier snel te achterhalen welke data juist gerequest kan worden. Wanneer we zelf resolvers schrijven, en via onze controllers passeren, kunnen we deze relaties soms niet weten en dus minder geneste data teruggeven. Hierdoor was het soms zoeken om de juiste data terug te geven. Ook waren er een aantal problemen met het verschil in hoe data terug werd gegeven uit de controllers en hoe het plugin-systeem data verwachtte. Hiervoor moesten er nog een aantal functies bijgeschreven worden om de data consistent te houden, bv. veranderen van snake_case naar camelCase.
