---
title: Week 10
date: '2019-04-26'
---

## Dag 1:

Paasmaandag.

## Dag 2:

De MQTT connector werd verder uitgebouwd om conform te zijn met de functionaliteiten in de reeds bestaande connectors. Zo werd het meegeven van argumenten aan de connector op een betere manier gedaan met een environment bestand en werd er een systeem toegevoegd voor inkomende messages beter op te vangen. Zo zou er bij een slecht bericht een polling tijd toegevoegd worden aan het interval waarover de berichten gestuurd worden, om wat meer speling te geven. Wanneer deze polling tijd een bepaalde limiet bereikte, werd het sturen van de berichten stopgezet. Ook werd er een optie toegevoegd om een limiet te plaatsen op het aantal berichten dat je wilt doorsturen, default staat deze op oneindig.

## Dag 3:

De connectoren die nu bestaan zijn een MQTT, Azure Iot Hub, AWS Iot Core en een Google Pub/Sub connector. Deze gebruiken maakten allemaal gebruik van hun eigen parser, om de inkomende berichten te veranderen naar een structuur die door de Waylay environment kan ingelezen worden. Deze parsers werden allemaal herschreven tot 1 gezamelijke parser, om zoveel mogelijk DRY te werken. Hiervoor werden ook terug een aantal testen geschreven in Jest.

## Dag 4:

Om de functionaliteiten te tonen van de connectors aan mogelijke klanten of op bv. beurzen en conferenties, moet er ook gekeken worden naar data die doorgestuurd wordt naar de verschillende pubsub systemen. Hiervoor werd reeds data verstuurd met behulp van Raspberry Pi's, maar er zijn talloze andere IOT devices die data kunnen doorsturen. De komende dagen zullen er een paar van deze manieren uitgewerkt worden. Het eerste was moest gebeuren was het refactoren van de Raspberry PI voorbeelden. Alle reeds bestaande voorbeelden werden eens getest om te kijken of ze nog steeds naar behoren werkten en werd er ook gekeken naar het aanpassen van de code. Zo zou het interessant zijn om ipv de Raspberry PI op een interval te laten data doorsturen, dit te laten gebeuren met een druk op een knop.
