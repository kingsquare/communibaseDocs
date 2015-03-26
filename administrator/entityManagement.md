---
layout: default
title: Entiteiten beheren
group: "administrator"
weight: 3
---

#### Wat is een entiteit?
In de administratie zijn kenmerken opgeslagen van verschillende entiteiten. Aan de hand van deze eigenschappen kunnen
nieuwe documenten worden aangemaakt of oude documenten worden aangepast. Zo is er bijvoorbeeld opgeslagen dat de
entiteit "Persoon" een aantal eigenschappen bevat, zoals een voornaam, een achternaam en een geboortedatum. Ook zijn
er andere eigenschappen opgeslagen, bijvoorbeeld dat een e-mailadres een '@' teken moet bevatten of dat een telefoonnummer
niet uit letters kan bestaan. De belangrijkste entiteiten zijn zichtbaar als tabblad in het centrale menu (Persoon,
Organisatie, etc.).

Je kunt entiteiten aanpassen door op het menu "Beheertaken" linksboven in het scherm te klikken en vervolgens te kiezen
voor "Beheer document definities". Hier staan alle bestaande entiteiten en er zijn verschillende opties. Je kunt een
entiteit toevoegen, wijzigen, verwijderen, kopieren en bulkwijzigen.

__LET OP__: Zodra een entiteit is veranderd of verwijderd, heeft dit eventueel invloed op ALLE documenten. Denk hier over na
voordat je hier wijzigingen in aanbrengt.

####<a class="anchor" name="uitleg"></a> Wat betekenen de diverse onderdelen van het formulier?
Als je een nieuwe entiteit aanmaakt of een oude wijzigt, komt je in een formulier met verschillende onderdelen.
Ten eerste zijn er vier kenmerken om in te vullen: 'Titel', 'Beschrijving', 'Systeemonderdeel' en 'Directe informatiebron'.
De tabel hieronder heeft een beschrijving van deze kenmerken:

|Naam onderdeel|Uitleg|
|---|---|
|Titel|De naam van de entiteit. Deze kan niet meer worden gewijzigd als het eenmaal is opgeslagen.|
|Beschrijving|Een korte beschrijving van wat de entiteit inhoudt en deze wordt alleen gelezen door een gebruiker.|
|Systeemonderdeel|Als een entiteit een systeemonderdeel is, is deze entiteit niet te verwijderen door een gebruiker. Dit houdt in dat het in principe helemaal niet verwijderd kan worden! Als een entiteit echter geen systeemonderdeel is, dan kan het door iedereen op elk moment worden verwijderd!|
|Directe informatiebron|Als een entiteit een directe informatiebron is, dan heeft het zijn eigen plaats in de administratie (zoals Persoon, Bedrijf, etc.). Zo niet, dan kan hij alleen als onderdeel van een directe informatiebron gebruikt worden (zoals Positie als onderdeel van Persoon).|

Vervolgens zijn er ook kenmerken aan een entiteit. Dit zijn de waardes die de entiteit heeft of kan hebben. Als je een
kenmerk toevoegt, kom je in een nieuw menu met verschillende onderdelen. Hieronder is een tabel met de uitleg per onderdeel:

|Naam onderdeel|Uitleg|
|---|---|
|Titel|De naam van de eigenschap. Dit is ook de naam die bijvoorbeeld gebruikt wordt met exporteren / importeren. De titel is in het Engels, begint altijd met een kleine letter en bevat geen spaties. Als het twee woorden zijn, wordt het samen geschreven op de volgende manier: firstName.|
|Systeemonderdeel|Als een eigenschap een systeemonderdeel is, dan kan het niet worden verwijderd door een gebruiker. Zie de tabel hierboven bij "Systeemonderdeel"|
|Verplicht|Mag dit veld leeggelaten worden in een formulier of moet het verplicht worden ingevuld?|
|Type|Wat voor soort informatie bevat deze eigenschap? Dit kan bijvoorbeeld een getal, datum of objectverwijzing zijn. Meer informatie over de inhoud en werking van deze datasoorten vindt u op [deze](https://github.com/wordnik/swagger-core/wiki/Datatypes) externe site.|
|Presentatie|Bepaalde dingen kunnen anders weergegeven worden in formulieren. In dat geval kan er bij deze optie gekozen worden voor een andere presentatie. Opties zijn bijvoorbeeld: 'Opgemaakte tekst (HTML)' voor HTML input, 'Groot tekstveld' voor als er veel ruimte nodig is om te typen en 'Wachtwoord' voor als de input niet leesbaar mag zijn.|
|Beschrijving|De volledige beschrijving van de eigenschap. Wat kan er ingevuld worden, op wat voor manier moet het ingevuld worden en waar zou het eventueel voor gebruikt kunnen worden?|
|Standaard waarde|Wat zou er standaard in dit veld ingevuld moeten zijn als je nog niks hebt ingevuld? Welke voorkeurswaarde moet er staan in dit veld? Als er niks in dit veld moet staat is de Standaard waarde "" (leeg).|
|Items|Als het type van de eigenschap 'Lijst' is, wordt hier beschreven welke objecten er in de lijst zouden kunnen. Dit kunnen bijvoorbeeld adressen of posities kunnen zijn (entiteiten die geen directe informatiebron zijn).|
|Referentie naar|Als het type van de eigenschap 'ID (objectverwijzing)' is, wordt hier beschreven naar wat voor object er verwezen worden met het ID. Dit kan bijvoorbeeld persoon of debiteur zijn.|
|Soort|Sommige eigenschappen mogen slechts een beperkt aantal waarden bevatten. Hier kan worden geselecteerd of er een bepaald aantal waarden bevat mogen worden. Zo ja, dan is de keuze 'Keuzelijst', 'Reeks' en 'Reguliere expressie'. Meer informatie over deze types, is [hier](https://github.com/wordnik/swagger-core/wiki/Datatypes) (externe site) te vinden.|
|Minimum|Als er bij "Soort" is gekozen voor "Reeks", dan moet er een minimum en een maximum van het getal ingesteld worden. Hier kan het minimum worden ingevuld.|
|Maximum|Zie minimum.|
|Waardes|Als bij "Soort" is gekozen voor "Keuzelijst", moeten hier de mogelijke waardes worden ingevuld. Dit moet genoteerd op de volgende manier (voorbeeld): ["Ja","Nee","Misschien"]. LET OP: Als het ook mogelijk is om een lege waarde in te voeren, moet die ook worden toegevoegd aan de waardes. Dan wordt het dus: ["Ja","Nee","Misschien",""] (de dubbele quotes staan voor een lege waarde.|
|Overeenkomst|Als bij "Soort" is gekozen voor "Reguliere Expressie", dan moet hier de Reguliere Expressie waaraan moet worden voldaan worden ingevuld. Een voorbeeld is "/abc\d+/i." (zonder quotes).|