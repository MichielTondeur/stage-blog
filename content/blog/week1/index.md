---
title: Week 1
date: '2019-02-17'
---

## Dag 1:

Deze dag bestond vooral uit een korte rondleiding door het bedrijf, een kennismaking met de collega's en vervolgens het opzetten van verschillende accounts. Dat hield in: toegang krijgen tot de nodige repos op github, toegang tot het staging gedeelte van alle websites, toegang tot de continious integration website, nl. Drone, alsook het opzetten van een persoonlijk Google account. Ook werd ik toegevoegd aan een Slack en een Trello om alle verdere communicatie langs deze kanalen te doen. Na dit alles kreeg ik toegang tot repos waar ik de komende dagen een GraphQL API zal moeten implementeren.

## Dag 2:

Ik kreeg toegang tot frontend en backend repos van een dashboard applicatie, waarin ik mij vervolgens wegwijs in moest maken. Kijken hoe deze met elkaar gelinkt waren, welke technologieën er gebruikt werden, welke API calls er gemaakt werden en uitzoeken waar er een duidelijk verschil zou zijn moest er gebruik gemaakt worden van een GraphQL API.

## Dag 3:

Dag 3 bestond vooral uit het leren van de GraphQL technologie en opzoekwerk wat de beste manier zou zijn om een GraphQL API te implementeren. Hierbij werd vooral de officiele documentatie en codevoorbeelden gebruikt. Aangezien de applicatie gebruik maakt van een Postgres databank, kan er gebruik gemaakt worden van een tool genaamd Postgraphile. Deze tool kan aan de hand van Postgres schemas, comments en functies een GraphQL API genereren. De rest van de dag werd gespendeerd aan de documentatie hiervan te lezen, te begrijpen en de nuttige functionaliteiten voor onze applicatie op te schrijven.

## Dag 4:

De allerlaatste dag werd geprobeerd Postgraphile te implementeren in de applicatie, dit als middleware in een node server. Deze is vervolgens gekoppeld met de reeds bestaande authenticatie middleware en werden er verscheidene nuttige plugins toegevoegd om meer functionaliteiten te krijgen in de API.

Vervolgens werd er gekeken om de API verder te verfijnen en nuttiger te maken, door bv. Postgres functies toe te voegen om extra Graphql resolvers te bekomen. Ook werd er gekeken om Postgres comments toe te voegen, zodat Postgraphile met deze comments bepaalde velden of tabellen kan negeren, of bepaalde graphql queries niet aanmaakt omdat deze geen permissies hebben.
