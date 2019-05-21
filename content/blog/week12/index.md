---
title: Week 12
date: '2019-05-11'
---

## Dag 1:

Aangezien er opnieuw grote refactors waren gebeurd met de code en mogelijke variabelen, moest de documentatie terug aangepast worden. Ook werden er vermeldingen gemaakt naar het gebruik van de Raspberry PI en de simulators.

## Dag 2:

Een andere manier van data door te sturen is met behulp van een gateway. De CLoudgate Option Gateway is een machine die kan verbinden met verschillende industriele sensoren. Deze sensoren hebben vaak zelf geen manier om data door te sturen over het internet, maar connecteren dus met de gateway met behulp van manieren zoals LoRa, Sigfox, ... In de gateway zelf wordt er gebruik gemaakt van Luvit-RED, een Lua variant van Node-RED. Dit programma liet ons toe om doormiddel van drag en drop met verschillende bouwstenen, de code uit te lezen uit de sensors en deze door te sturen. De gemakkelijkste implementatie was het publishen naar een bepaalde MQTT topic.

## Dag 3:

Nu de connectoren op staging stonden en er een aantal voorbeelden waren van manier door te sturen, kon er gekeken worden naar een ander onderdeel in het verhaal, namelijk payload transformaties. Niet elke payload dat binnenkomt in de Waylay environment is hetzelfde. Soms komt er zelfs teveel data binnen of moet deze data nog veranderd worden naar een ander formaat. Er werd een meeting gehouden met een paar van de senior developers om te overlopen welke verschillende transformaties een meerwaarde kunnen betekenen. Ook werd er vooral gekeken waar dat deze transformations plaats zouden vinden. Was dit iets dat door de klanten zelf verwacht wordt te gebeuren of moet Waylay deze functionaliteit aanbieden. Dit onderwerp zal zeker nog meerdere malen besproken worden, maar ik kreeg alvast de opdracht om wat dieper in te gaan op de transformaties. Whitelisting, blacklisting, eenvoudige wiskundige veranderingen, key value van naam veranderen, flatten van de data, values van type veranderen, meerdere payloads samenvoegen tot 1 JSON object of tot een array van JSON objecten. Deze transformaties kunnen zeer complex worden, dus was het mijn opdracht om te kijken welke libraries er bestaan om dit mogelijks op te lossen.

## Dag 4:

De zoektocht begint naar een library waarmee we een JSON payload kunnen transformeren. Hiervoor kunnen we kijken naar hoe XML dit probleem oploste met iets zoals XSLT en XPath. Nadat verschillende libraries bekeken werden, was er eentje die uit het oog sprong om ons probleem op te lossen, namelijk JSONata. JSONata is een transformatie taal die met behulp van templates, verschillende functionaliteiten en operatoren, de gebruiker toelaat om JSON data te veranderen in de gewenste structuur. De kracht lag er ook in dat we veel transformaties konden combineren door de template op te stellen hoe wij deze wouden. Het enigste mogelijke nadeel zou zijn dat wanneer onze binnenkomende data zeer groot was, onze template ook groot zou moeten zijn. Hiervoor biedt JSONata wel bepaalde methodes aan om de data te overlopen, maar dit kan vlug zeer complex worden. Volgende week zullen we een klein aantal voorbeelden uitwerken om de functionaliteiten van JSONata toe te lichten.
