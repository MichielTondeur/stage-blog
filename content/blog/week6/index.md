---
title: Week 6
date: '2019-03-21'
---

## Dag 1-2-3:

Het begin van de week was vooral het aanmaken van de custom resolvers die de GraphQL API zal gebruiken. Deze custom resolvers zijn nodig om bepaalde zaken te laten gebeuren die Postgraphile natuurlijk niet automatisch kan. Dit houdt dus vooral in het aanmaken van een unieke UUID, het bulk aanmaken van bepaalde data en eventuele andere acties die op een call volgen, zoals het versturen van een email.  
De volgende stappen werden telkens gevolgd: aanmaken van een custom resolver, deze laten verwijzen naar een reeds bestaande controller of eventueel zelf nog functionaliteit schrijven en deze vervolgens implementeren in de frontend. Hier kwamen vaak nog sommige problemen bij kijken, zoals het aanpassen van het databank model of problemen met de cache die automatisch gesynct werd.

## Dag 4:

Op dag 4 werden de laatste van de custom resolvers geïmplementeerd. Hierdoor komt de opdracht op de laatste rechte lijn richting de finish te geraken.
Een probleem dat nog werd opgelost vandaag, was een probleem met de routing tussen 2 pagina's. Vroeger maakten predefined roles en custom roles gebruik van dezelfde pagina om rollen te tonen, maar ze moesten elk een aparte pagina krijgen, omdat hun Apollo Client queries anders moesten zijn in de Higher Order Components. Hierdoor waren er wel een aantal problemen met breadcrumbs en URL's die kapot waren. Er werden een paar url's aangepast, als ook het meegeven van een 'predefined' property aan bepaalde componenten, om de juiste lay-out te kunnen tonen aan de hand van welke rollen we te zien krijgen.
