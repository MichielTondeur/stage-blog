---
title: Week 3
date: '2019-03-03'
---

## Dag 1:

Nu de Postgraphile library op punt stond en de automatisch gegenereerde GraphQL API volledig aangemaakt was, kon er gekeken worden voor een initiële implementatie in de frontend. Hiervoor wordt er gebruik gemaakt van een framework genaamd Apollo. Apollo beschikt over zowel een manier om een GraphQl server mee op te zetten in de backend, als het verwerken van queries en mutations in de frontend. Aangezien de API door Postgraphile aangemaakt is, is enkel de frontend, nl. Apollo Client, interessant voor ons. Deze dag bestond uit het lezen van de documentatie van Apollo Client en het maken van enkele test voorbeelden.

## Dag 2-3-4:

De rest van de week hield de implementatie van de GraphQL API in de frontend UI in. Na het onderzoeken van de Apollo Client, kwamen we tot de conclusie dat de Client op 2 verschillende manieren in React kon gebruikt worden. Ten eerste namelijk met behulp van hun eigen Apollo componenten, nl. de <Query> en <Mutation> componenten. Of ten tweede, door gebruik te maken van React Higher Order Components. Waar de eerste manier ons toelaat om logischer na te denken over de structuur met behulp van componenten, laat de tweede manier ons toe om alle functionaliteit gescheiden te houden van de componenten, en zo dus aan separation of concerns te doen. Omdat we de frontend zo makkelijk mogelijk en leesbaar willen houden, is de tweede optie de logische keuze.

Om de GraphQL API te implementeren, moest er een Apollo Client opgezet worden, moest er een ‘GraphQL’ endpoint aangemaakt worden op de server en worden verschillende REST API calls vervangen door queries en mutations.

Ook werd er gekeken om te werken met de Apollo Cache. Apollo herkent reeds opgevraagde data en houdt hiervoor zijn eigen lokale, genormaliseerde store bij. Deze cache laat ons toe om geen onnodige API-calls te maken wanneer de data reeds opgevraagd was in het verleden. Deze cache herkent ook edits of updates in de reeds aanwezige data en kan deze dus automatisch aanpassen, zonder dat wij hiervoor moeten inspringen. Waar er wel code geschreven werd, is wanneer er data wordt bijgevoegd of verwijderd. Omdat de cache niet synchroon is met de databank, moest er bij een toevoeging of verwijdering, handmatig data uit de cache weggeschreven of verwijderd worden.

Deze initiële implementatie gaf een veel duidelijker beeld over wat juist te verwachten van de GraphQL API en toonde ook sommige minpunten van Postgraphile. Zo is er de nood om zelf custom resolvers te schrijven voor bepaalde functionaliteiten wat niet simpel opgelost kan worden met Postgraphile. In de verdere dagen zal er gekeken worden hoe dat we dit kunnen opvangen en verbeteren.
