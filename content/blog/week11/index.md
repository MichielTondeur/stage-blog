---
title: Week 11
date: '2019-05-03'
---

## Dag 1:

De vorige week werd er gestart met de Raspberry Pi's data te laten doorsturen met een druk op een knop. Hier kwamen we al meteen voor wat problemen te staan. De knop die gebruikt werd was een GrovePI Digital Button, maar deze vertoonde geen consistent gedrag. Het event dat de knop was ingedrukt gebeurde maar de helft van de tijd of liet enkele seconden op zich wachten. Er werd gekeken naar mogelijke oplossingen, zoals mogelijks een slecht ingestelde Baude Rate, maar na veel proberen was er weinig vooruitgang. Er werd er dus voor gekozen dit zo te laten en toch met de intervallen te werken, totdat er een nieuwe button sensor werd aangekocht.

## Dag 2:

Nadat de Raspberry PI voorbeelden allemaal werkten, werd er gekeken naar de volgende manier om data door te sturen. Tijdens het maken van de connectors had ik al een klein programma gemaakt om test data te kunnen door sturen over de MQTT connector. Deze data simulaties mocht ik voor elke connectors maken en consistent maken in de payload die verstuurd werd. Dit waren simpele NodeJS applicaties die een reeks berichten doorstuurden naar de gewenste connectors. Deze simulaties konden interessant zijn wanneer er geen RaspBerry PI aanwezig was om de demo toch te kunnen laten werken.

## Dag 3:

Voordat er verder gekeken werd naar andere manieren om data te versturen, was de code van de connectors door een code review gegaan. De rest van deze dag zat ik neer samen met een collega vanop Waylay om te kijken hoe we nog andere stukken code konden inovatiever maken. Zo werden er dus terug stukken code in de connectors en in de parser gerefactord. Dit was vooral functionaliteiten in hun eigen methodes plaatsen, namen veranderen van variabelen, bepaalde stukken code reduceren tot enkele lijnen aan code, een zeer leerrijk process voor mij om te kunnen zien waar er nog kan gesnoeid worden in mijn manier van code schrijven.

## Dag 4:

Dag 4 zat ik opnieuw samen met de collega om te kijken naar het plaatsen van de connectoren op de staging environment. Dit hield in het schrijven van verschillende manifesten in YAML om de deployment met Docker en Kubernetes te laten gebeuren. Iedereen binnen Waylay is verplicht om soort van de Devops te spelen voor hun eigen applicaties, en het opvolgen van een goeie deployment is dus ook van groot belang. Dit was iets waar ik nog weinig tot geen ervaring mee had, dus opnieuw een zeer leerrijke ervaring en iets waar ik mij zeker mee zal bezig houden naar de toekomst toe.
