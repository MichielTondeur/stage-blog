---
title: Week 4
date: '2019-03-10'
---

## Dag 1-4:

Deze week werd de GraphQL API verder geïmplementeerd in de frontend UI. Dit ging te werk door te kijken welke REST API calls er gemaakt werden, welke GraphQL queries deze konden vervangen en het vervolgens samenvoegen van alle calls in 1 grote query, zodat er maar 1 bezoek naar de API moet gebeuren.

Dit alles ging hand in hand met het gebruiken van de Apollo Cache. Deze cache laat Apollo toe om eerst te kijken of de data reeds lokaal bestaat, zodat er geen onnodige calls naar de API moeten gemaakt worden.
De data wordt opgeslagen in de cache aan de hand van zijn typename en zijn unieke id, bv. 'User:2f5921ce-f35f-4083-9594-2576dc77de23'.
Door deze verwijzing naar de data kan Apollo veranderingen aan deze data gemakkelijk zelf updaten, zodat het editeren van data of meer informatie opvragen over de data in de achtergrond aangepast wordt. Deze laat ons toe om data consistent te houden door verschillende pagina's heen.

Waar de cache wel manueel moet gelezen en veranderd worden, is bij het toevoegen of verwijderen van data in een lijst, bv. Users toevoegen of verwijderen. De toegevoegde of verwijderde data moet manueel aangepast worden en is gelinkt aan een query waarin de data opgevraagd wordt. Het zelf aanpassen van de cache kan soms voor problemen zorgen, zoals wanneer een bepaalde stuk data meerdere keren voorkomt in de cache. Apollo heeft nog geen goede manier om hiermee om te gaan en is momenteel 1 van de grootste issues die Apollo heeft.

https://github.com/apollographql/apollo-feature-requests/issues/4

Omdat het manueel aanpassen van de cache op deze manier vaak niet mogelijk of te moeilijk is, kiezen we ervoor om bepaalde queries een extra property mee te geven. Door de 'fetchPolicy' aan te passen van bepaalde queries, zullen deze queries zowel in de cache als met de API kijken of de data veranderd is. Op deze manier houden we alle data consistent, met als nadeel soms een paar onnodige calls naar de API.

Door het implementeren van de GraphQL API in de frontend, zien we dat er veel code verwijderd mag worden en dat de code veel overzichtelijker wordt. Dankzij Apollo Cache kan bv. Redux volledig weggelaten worden in de code. Queries kunnen gemakkelijk aangepast of veranderd worden, om andere of meer data te verkrijgen. Alle functionaliteit is ook mooi gescheiden van de eigenlijke componenten. Door gebruik te maken van GraphQL krijgt de code een logischere structuur en kan er gemakkelijker gefocust worden op het schrijven van code.
