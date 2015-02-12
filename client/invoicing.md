---
layout: default
title: Factureren
group: "client"
weight: 3
---

#### Handmatige factuur aanmaken
Facturen kunnen automatisch worden aangemaakt naar aanleiding van deelnames aan groepen (lidmaatschappen) of evenementen.
Daarnaast kan er ook handmatig een losse factuur worden aangemaakt. Dit gebeurt op de standaard manier waarmee nieuwe
documenten kunnen worden toegevoegd, namelijk door naar het tabblad "Factuur" te gaan en vervolgens op "Toevoegen" te klikken.

![Screenshot Factuur Form](/assets/img/handmatigFactuur.png)

Vervolgens komt de gebruiker in een formulier terecht waar de gegevens van de factuur kunnen worden ingevoerd. Dit
werkt hetzelfde als bijvoorbeeld een formulier om een nieuw persoon toe te voegen. Voor uitleg hierover, zie
[Werken met documenten](/client/workingWithEntities/).

Als een factuur is aangemaakt, zijn er een aantal specifieke acties mogelijk welke alleen bij facturen van toepassing zijn.
Deze aanvullende acties zijn [Definitief maken](#definitief) en [Crediteren](#crediteren) en zijn te vinden in het menu van de standaard acties.

![Screenshot Actions Factuur](/assets/img/factuurActies.png)

##### <a class="anchor" id="definitief"></a>Definitief maken
Een factuur zonder factuurnummer kan definitief worden gemaakt. Dit houdt in dat de factuur wordt voorzien van factuurnummer en
daardoor niet meer veranderd of verwijderd kan worden. Zolang een factuur niet definitief is, kan deze als "proforma" worden
beschouwd en is de factuur nog vrij aan te passen. Zodra een factuur definitief is, kan deze alleen ongedaan worden gemaakt
middels een creditfactuur.

##### <a class="anchor" id="crediteren"></a>Crediteren
Een definitieve factuur kan worden gecrediteerd en dit houdt in dat er een nieuwe factuur wordt opgesteld met daarin
het factuurbedrag, maar dan negatief. Boekhoudkundig wordt het factuurbedrag daarmee 0 euro. De PDF van deze creditfactuur
kan een gebruiker opsturen per e-mail naar de debiteur om aan te geven dat de originele factuur niet hoeft te worden voldaan.
Ook kan er handmatig een e-mail gestuurd worden naar de debiteur door het factuur naar "Contact" te slepen in het Communilinks
menu en de wizard te volgen.

#### Facturatie wizard
Zodra je meerdere facturen tegelijk wilt maken, is het veel werk om iedere keer een nieuwe factuur aan te maken.
In dat geval kan er gebruik gemaakt worden van de [Drag and Drop techniek](/client/#dragAndDrop).
De gebruiker kan de een groepslidmaatschap of evenement naar het veld "Factuur" slepen. Dit is echter mogelijk
voor groepslidmaatschappen en evenementen. Voor beide entiteiten zal er een facturatie wizard verschijnen.

##### Groepslidmaatschappen
Het is mogelijk om alle relevante lidmaatschappen óf een selectie aan lidmaatschappen te factureren. In het eerste geval
kunt u gebruik maken van de knop "Alle groepsdeelnames factureren" onder het menu "Standaard actie". In het andere geval
kunt u eerst de gewenste lidmaatschappen zoeken en selecteren en deze daarna slepen naar het Communilinks-paneel "Factuur".

Om facturen te kunnen maken voor groepslidmaatschappen, moet de gerelateerde groep minstens één tarief bevatten. Als
dit niet het geval is, zal er een foutmelding verschijnen die eruit ziet zoals de foutmelding hieronder.

![Screenshot Error Group](/assets/img/facturatieGroepFoutmelding.png)

Als deze foutmelding voorkomt, mist de betreffende groep een tarief en kan er dus logischerwijs geen factuur worden
opgesteld. Het zou ook kunnen dat het te gebruiken tarief "niet meer geldig" is: tarieven hebben een geldigheidsduur.

Als de groep een tarief bevat, zal de gebruiker terecht komen in een wizard die zal vragen tot welke periode het
lidmaatschap kan worden gefactureerd. Zo kan bijvoorbeeld gekozen worden om voor het komende jaar of voor de komende
drie jaar een factuur op te stellen. De data die beschikbaar zijn in dit menu, zijn de data die zijn opgegeven bij
de tarieven in de betreffende groep. Zodra de gebruiker een keuze gemaakt heeft, kan er gedrukt worden op
"Start factureren wizard".

Vervolgens verschijnt er een overzicht van alle facturen die door de wizard worden opgesteld. Hier kan de gebruiker
nog gegevens wijzigen of verwijderen en zodra alles correct is, kan er worden gedrukt op "Volgende stap". In het
scherm dat dan verschijnt is een voorbeeld van een factuur te zien. Alle facturen kunnen hier getoond worden door op
het pijltje omlaag te klikken rechtsboven de factuur.

![Screenshot Example Invoice](/assets/img/voorbeeldFactuur.png)

Als er nog gegevens onjuist zijn, kunnen deze worden aangepast door op "Terug" te klikken en de gegevens aan te passen.
Als alles correct is, kan er worden geklikt op "Opstellen". Dit houdt in dat de factuur wordt aangemaakt en de
administratie zal vragen of de factuur definitief is en of de debiteur een e-mail moet ontvangen. Als dit gedaan
is, ben je klaar met het factureren van de groepslidmaatschappen.

##### Evenement
Om deelnemers van evenementen op dezelfde manier te kunnen factureren, moet een evenement ook minstens één tarief en
een deelnemer bevatten. Als dit niet het geval is, verschijnt er voor de gebruiker deze melding:

![Screenshot Error Event Invoice](/assets/img/facturatieEvenementFoutmelding.png)

Dit kan worden opgelost door een tarief toe te voegen aan het evenement of aan de sessie van het evenement. Bovendien
moet er dan een deelnemer aanwezig zijn bij het evenement of bij de sessie. Als dit het geval is, zal de gebruiker
in een facturatie wizard terecht komen met een overzicht van alle facturaties die gaan worden opgesteld. De volgende
stappen zijn dezelfde stappen als bij het factureren van groepslidmaatschappen hierboven.
