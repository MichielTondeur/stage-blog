---
title: Week 8
date: '2019-04-06'
---

## Dag 1:

Een extra controle die nog geschreven moest worden, was het valideren van de vele forms. We willen natuurlijk dat de gebruikers nuttige informatie ingeven en moeten er dus bepaalde regels toegepast worden op onze velden om te controleren op hun inhoud. Voornamelijk houdt dit in het controleren of de ingegeven data een string is, minimale lengte, dat het voldoet aan het soort veld, bijvoorbeeld een email-veld, etc... . Een handige library die hiervoor bestaat is JOI.js, een object schema validator. Wij gebruiken hiervoor specifiek Celebrate.js, die ons toelaat om de JOI validatie in onze middleware toe te passen.

## Dag 2:

Omdat aanvragen naar de GraphQL server samen met de JWT middleware soms nog voor errors en problemen zorgden, werd er gekozen om een aantal testen bij te schrijven. Zo werd er in deze testen bij een aanvraag gekeken of een token aanwezig was, of deze wel de juiste structuur van een JWT token had en vervolgens of de JWT token wel geautoriseerd was. Door deze testen werd nog een klein probleem gevonden waar er naar een foute route nog verwezen werd. Na dit op te lossen werkte de Postgraphile implementatie met de JWT middleware volledig.

## Dag 3:

Dag 3 werd de GraphQL implementatie op de staging environment geplaatst, zodat de collega's er mee konden werken en eventuele problemen nog konden tegenkomen, voordat het in productie geplaatst wordt. Een aantal problemen die hier nog boven water kwamen waren een aantal variabelen die nog steeds op localhost stonden ingesteld, alsook een paar snapshots in Jest die niet meer overeenkwamen met de nieuw opgestelde databank. De rest van de dag bestond vooral uit het oplossen van deze minieme problemen.

## Dag 4:

Omdat de GraphQL implementatie enkel verder gecontroleerd moest worden, kon er al aan een nieuwe opdracht gewerkt worden. Wanneer bedrijven hun data willen doorsturen naar de Waylay, maakten ze vaak gebruik van bepaalde pub/sub systemen. Een aantal voorbeelden hiervan zijn Azure Iot Hub, AWS Iot Core of Google Pub/Sub. Waylay voorzag hiervoor een aantal zelfgeschreven connectoren, die konden subscriben op deze systemen om dan vervolgens de data door te geven. Deze connectoren kunnen door bedrijven gemakkelijk als Docker Images opgezet worden.
Vb: Data van Iot devices --> PubSub systeem --> connector --> Waylay broker --> Waylay environment.

Sommige bedrijven maken geen gebruik van third party systemen, maar hebben hun eigen PubSub broker, die gebruik maakt van MQTT, een protocol bedoelt IoT messages te verwerken.

De nieuwe opdracht bestond uit het schrijven van een nieuwe connector, die kan subscriben op MQTT brokers en deze data kon verder versturen naar de Waylay broker.

Deze laatste dag werd de eerste connectie met de MQTT broker al gemaakt en kon er al op data gesubscribed worden.
