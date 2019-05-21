---
title: Week 13
date: '2019-05-17'
---

## Dag 1:

De bedoeling van deze opdracht is een document uitschrijven waarin er gekeken wordt welke library gebruikt kan worden voor de JSON transformaties. Ik heb ervoor gekozen om te beginnen met een reeks testen te schrijven waarin JSON data veranderd wordt, en vervolgens 2 programma's tegen deze testen te runnen. Eenmaal door gebruik te maken van gewone Javascript code en eenmaal door gebruik te maken van JSONata, in de hoop om een duidelijke meerwaarde aan te tonen in JSONata. De eerste dag bestond dus om testen te schrijven voor elke mogelijk transformatie die we willen toepassen op onze JSON data.

## Dag 2:

Dag 2 was het schrijven van het eerste programma, waarin er standaard Javascript gebruikt werd om de JSON data aan te passen. Al snel werd het duidelijk dat zelfs voor schijnbaar makkelijke transformaties zoals het veranderen van een naam, we al snel zeer complexe stukken code moesten schrijven. Iterenen over een object zijn keys en values, gebruik maken van methodes zoals omit, filter, reduce, ... Meerdere transformaties zou ook betekenen meerdere methodes na elkaar aanroepen, wat mogelijk de data zeer snel kan vervormen. Alle testen sloegen voor het uitgewerkte programma in standaard Javascript, maar het was duidelijk dat dit zeer snel zeer complex werd.

## Dag 3:

Vervolgens maakte ik dezelfde transformaties, maar deze keer met behulp van JSONata. De meeste transformaties waren ongelofelijk simpel op te lossen mbv JSONata. Namen veranderen en transformeren van types kon gebeuren door simpel weg in de template die zaken aan te passen. Door te kiezen in de template welke data je wou tonen, werd het probleem van whitelisting en blacklisting opgelost. Maar niet alles was even gemakkelijk. Het flattenen van data was nog steeds beter oplosbaar door een aparte, flatten library te gebruiken. En het veranderen van meerdere payloads tot 1 enkele array van payloads werd al snel complex in JSONata door het moeten gebruiken van bepaalde operatoren. Maar voor het merendeel van de transformaties, alsook de kracht van al deze transformaties samen uit te voeren, maakten van JSONata een duidelijke winnaar.

## Dag 4:

De laatste dag van de week bestond uit het opstellen van het document waarin ik JSONata als een mogelijke kandidaat naar voren schoof voor de JSON transformaties. Na alle positieve en negatieven neer te pennen, was er een korte meeting met hetzelfde team als de eerste meeting. JSONata werd inderdaad als een mogelijke library om te gebruiken gevonden, maar de vraag was nog steeds of ze de bedrijven deze library kunnen laten gebruiken eer de data wordt doorgestuurd naar Waylay. Maar aangezien dit voorbij mijn stageperiode gaat, waren ze nu vooral al blij dat het gebruiken van gewone Javascript kon van tafel geveegd worden en dat een library de juiste optie was.
