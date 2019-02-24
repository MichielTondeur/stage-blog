---
title: Week 2
date: '2019-02-24'
---

## Dag 1:

De dag begon met het verder implementeren van Postgraphile. De GraphQL API kon succesvol worden aangemaakt, en met behulp van een geïntrigeerde grafisch interface genaamd GraphiQL kon er al getest worden of de queries en mutations werkten. Ook werd er eens geprobeerd de API aan te spreken met behulp van Postman, een programma waarmee HTTP requests gemaakt kunnen worden. Vervolgens werden de plugins die Postgraphile aanbiedt wat dieper op ingegaan. 2 plugins zouden het gebruik van de API sterk verbeteren, namelijk de pg-simplify-inflector en de pg-many-to-many plugins. Deze zorgen er respectievelijk voor dat de GraphQL API gebruik maakt van een simpelere en duidelijkere naamgeving, en dat de API een veld toevoegt om veel op veel relaties gemakkelijker te querien.

## Dag 2-3:

Deze dagen bestonden vooral uit het schrijven van migrations en het debuggen van een paar problemen. De migrations die geschreven werden, voegden aan de Postgres databank comments en functies toe, zodat deze door Postgraphile kon geïnterpreteerd worden voor de GraphQL API. Zo werden foreign key indexes toegevoegd voor alle relaties, omdat deze vereist waren voor GraphQL om te werken. Ook werd er commentaar toegevoegd aan sommige tabellen en velden. Postgraphile leest deze 'smart comments' en kan aan de hand hiervan op bepaalde velden of tabellen restricties toeleggen.

Een aantal bugfixes werden ook gedaan tijdens deze 2 dagen. De applicatie maakte al gebruik van Jest om bepaalde functionaliteiten te testen. Deze testen openden elke keer een nieuwe connectie naar de databank, en sloten deze niet proper af. De limiet stond ingesteld op 100 connecties, en vaak faalde het builden van de code dan. Met het toevoegen van een simpele methode om connecties mooi af te sluiten na elke test, was dit opgelost. Jest faalde soms ook, omdat bepaalde testen gebruik maakten van snapshots. Deze snapshots zijn de verwachte html die men krijgt wanneer de applicatie gebuild wordt. Deze snapshots wisselden soms van volgorde, en het opnieuw aanmaken van elke snapshot, loste dit probleem op. Ten laatste was er ook een probleem met de Postgraphile plugins. De plugins werken wel tijdens het builden, maar geven ook problemen met Jest. Nadat de Jest testen gedaan waren, kwam er een foutmelding dat er niet mag geïmporteerd worden nadat de testen gedaan zijn. We vermoeden dat de fout ligt in de code van de plugins zelf, en niet in mijn implementatie ervan. Mogelijks zal ik hiervoor nog een issue aanmaken op de Github-pagina van deze plugin.

## Dag 4:

De allerlaatste dag was het eerste ontmoetingsgesprek met de stagementor en stagebegeleider. We overliepen de stageopdracht, de bachelorproef en de het opgestelde actieplan. Deze waren allemaal goed opgesteld en voldeden aan de eisen.

In de namiddag werd er kort nog een extra migration geschreven om een functie toe te voegen die gebruik maakt van de 'firstname' en 'lastname' velden, om deze dan samen te voegen en er een 'fullname' veld van te maken. Deze functie wordt door Postgraphile herkend, en deze wordt dan ook toegevoegd aan de GraphQL API. Vervolgens werd er kort ook al eens geprobeerd om de GraphQL API te implementeren in de UI.
