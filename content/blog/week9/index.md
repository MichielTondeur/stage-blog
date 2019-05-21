---
title: Week 9
date: '2019-04-19'
---

## Dag 1:

De structuur van de data die de MQTT connector kan ontvangen, is onbekend voor de connector. Het was dus nodig om deze op te vangen, te kijken of het XML of JSON is en vervolgens deze data te flatten. Zo krijgt men steeds voorspelbare data in het Waylay platform.

Uiteindelijk was het dus mogelijk om op bepaalde topics te kunnen subscriben, deze data te parsen en door te sturen naar de Waylay environment. Verder werd er ook al op bepaalde plaatsen logs doorgestuurd en checks gedaan om te zien of alle mogelijke variabelen correct aanwezig waren.

## Dag 2:

De connector moest natuurlijk ook kunnen werken met de reeds bestaande connectoren. Hiervoor kon met een simpele variabele gezegd worden of een connector gebruikt werd en deze werd dan in een sink geplaatst waar alle open connectoren inzaten.

Na een code review moesten er nog een aantal andere zaken aangepast worden. Naast wat refactoren moest er ook gebruik gemaakt worden van fast-safe-stringify, dit om circular structures in JSON objecten te voorkomen.

Wanneer dit alles gedaan was, kon een docker image gemaakt worden en op de google cloud van Waylay geplaatst worden om eens te testen. Berichten werden vestuurd met behulp van MQTT.FX over een bestaande Waylay MQTT broker, deze werden opgevangen door de connector die als container in de google cloud kubernetes draaide om vervolgens toe te komen in de Waylay environment.

## Dag 3:

Dag 3 bestond uit het schrijven van documentatie over het opstellen van de docker container van de nieuwe connector.

Wanneer dit alles gebeurd was, kreeg ik de opdracht om eens echte informatie van een IoT device door te sturen naar de MQTT broker, om vervolgens via de connector door te sturen. Hiervoor mocht ik aan de slag gaan met een Raspberry Pi 3 met een GrovePi Shield met enkele sensoren.
Hierin maakte ik eerst gebruik van Node-Red, een programmeer tool om bepaalde acties aan elkaar te verbinden en zo mijn data van de sensoren door te kunnen sturen naar de MQTT broker. Waar dit wel gemakkelijk werkte, was het wel een extra abstractie en kon er beter gekeken worden om alles in gewone NodeJs te schrijven.

## Dag 4:

Er werd gestart aan het schrijven van een NodeJS programma om data te publishen naar de MQTT broker. Hiervoor werd er met een mqtt library gewerkt, waar we gemakkelijk konden acties uitvoeren op connect, disconnect, subscribe, publish, ...
Door naar een bepaalde topic te publishen waar de connector ook op gesubscribed was, kon er gemakkelijk data naar de Waylay broker verstuurd worden. De data zelf kwam van de GrovePi sensoren, een licht- en geluidssensor. Deze data werd in een payload geplaatst met als resource naam de Raspberry Pi zelf en vervolgens doorgestuurd.
Ook kon er gesubscribed worden op een bepaalde topic van de MQTT broker, om data te verkrijgen waarmee bv. een led-lampje kon mee aangestoken worden.
Waar deze eerste implementatie al goed was, moest er natuurlijk nog meer gekeken worden naar het opvangen van de verschillende connecties en aantal messages.
