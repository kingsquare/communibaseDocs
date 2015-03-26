---
layout: default
title: Externe bestanden gebruiken
group: "client"
weight: 4
---

#### Exporteren
Als een gebruiker bepaalde gegevens uit een overzicht wil exporteren naar een csv-bestand, dan is dit mogelijk door
middel van een van de exporteer-functies. Ze zijn te vinden boven het juiste overzicht, onder het kopje "Extern".
Zodra er documenten zijn geselecteerd, kan er geexporteerd worden door op "Exporteer zichtbare kolommen", "Exporteer
alle kolommen" of "Technische export" te klikken.

![Screenshot export](/assets/img/exporteren.png)

Bij de eerste optie, zullen alleen de kolommen die op dit moment in het overzicht zichtbaar zijn geexporteerd worden.
De niet-zichtbare kolommen zullen dan niet voorkomen in het csv-bestand. Dit is niet zo als de optie "Exporteer alle kolommen"
gekozen wordt, dan zullen alle mogelijke kolommen in het csv bestand zichtbaar zijn.

Als er gekozen wordt voor "Technische export" zullen ook alle mogelijke kolommen geexporteerd worden, én er zal bepaalde
technische informatie meegestuurd worden die het makkelijker maakt om het bestand later weer te importeren. Ook zijn de kolom-koppen
niet naar het Nederlands vertaald, maar bevatten de (Engelse) namen zoals het systeem deze intern hanteert. Ook staan er
ID-nummer naar gekoppelde documenten, welk zonder (technische) context niet direct bruikbaar zijn. De bestanden die op
deze manier geexporteerd worden zullen van het goede formaat zijn om het weer te importeren, dus er hoeven niet per se veranderingen
aan gemaakt te worden. Het is dus raadzaam hier gebruik van te maken als je de informatie wilt wijzigen om deze daarna
terug in het systeem in te lezen.

####<a class="anchor" name="import"></a> Importeren
Als je beschikt over een (technisch) .csv-bestand met gegevens voor de administratie, dan kun je gebruik maken
van de importeer functie van de applicatie. Dit is te vinden bij het menu "Extern" boven het juiste overzicht.
Vervolgens kan men klikken op "Importeer bestand" en kan het csv-bestand worden geselecteerd.

![Screenshot import](/assets/img/importeren.png)

Het bestand moet gescheiden zijn met een ';' teken en de eerste regel moet zijn voorzien van de namen van de eigenschappen.
Hieronder is een klein voorbeeld van hoe een goed persoon bestand er in excel uit zou moeten zien.

|FirstName|LastName|BirthDate|
|---|---|---|
|Willem|de Vries|01-01-1950|
|Peter|Beentjes|12-12-1930|

Dit bestand zou dan kunnen worden geimporteerd (zolang het gescheiden is met een ';' teken) en het zou dan worden
opgenomen in de administratie als nieuwe personen. Zodra er objecten met een "_id" worden geimporteerd, zullen er
geen nieuwe documenten worden aangemaakt, maar zullen de bestaande documenten (met het desbetreffende "_id") worden
aangepast.

####<a class="anchor" name="speciaal"></a> Speciale exports
Sommige document-overzichten hebben speciale export- en importfuncties. Zo kan er bij een evenementoverzicht een export
worden gemaakt van deelnemers-informatie. Bij facturen is het mogelijk om speciaal voor bepaalde boekhoudpakketten een
export op te stellen. Mocht de door u gewenste export- of import vorm er niet bij staan, neem dan contact op met
Kingsquare.