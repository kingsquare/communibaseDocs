---
layout: default
title: Technische documentatie
group: "api"
---

Externe ontwikkelaars kunnen toegang krijgen tot één of meer onderdelen van een administratie. Op deze manier kan informatie
uit de administratie via een website worden aangeboden. Op deze manier is het bijvoorbeeld mogelijk om uw eigen ledenlijst,
zoekfunctie, profielpagina of evenementdeelname systeem in te richten, welke rechtstreeks is gekoppeld met de informatie
in de ledenadministratie.

Om gebruik te maken van de Communibase REST API heeft u een API sleutel nodig. Deze kunt u opvragen via het secretariaat van uw vereniging.

Wanneer u in het bezit bent een API sleutel kunt u de documentatie lezen welke voor u van toepassing is. U vindt deze documentatie hier:

[https://api.communibase.nl/docs/](https://api.communibase.nl/docs/)

Voorbeeldcode gebruik API
-------------------------

Voor PHP treft u dit hier: [https://github.com/kingsquare/communibase-connector-php](https://github.com/kingsquare/communibase-connector-php)

Voor node.js treft u dit hier: [https://github.com/kingsquare/communibase-connector-js](https://github.com/kingsquare/communibase-connector-js)


Veel gebruikte zoekopdrachten
-----------------------------

__Actieve lidmaatschappen__

U kunt met de volgende zoekopdracht de API gebruiken voor het opvragen van actieve lidmaatschappen. De volgende zoekopdracht geeft
alle lidmaatschappen welke lid waren van de groep met id-nummer 528cd99874c193fe070000fb op datum 11-03-2014

```
	{
		"$and": [
			{
				"groupId": "528cd99874c193fe070000fb"
			},
			{
				"$or": [
					{
						"startDate": null
					},
					{
						"startDate": {
							"$lt": "2014-03-11T00:00:00+01:00"
						}
					}
				]
			},
			{
				"$or": [
					{
						"endDate": null
					},
					{
						"endDate": {
							"$gt": "2014-03-11T00:00:00+01:00"
						}
					}
				]
			}
		]
	}
```

Ter verduidelijking: 528cd99874c193fe070000fb is in dit voorbeeld  ID nummber van de hoofd-lidmaatschapsgroep.
Dit ID nummer is op te vragen via een overzicht van groepen, of kan aan u worden verstrekt via een beheerder.
Datumnotatie volgt de ISO 8601 standaard.
