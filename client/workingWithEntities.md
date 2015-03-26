---
layout: default
title: Werken met documenten
group: "client"
weight: 1
---

#### Overzichten en documenten
Alle documenten van een [entiteit](/client/#entities) zijn beschikbaar in het overzicht. Wanneer het werkscherm
document-overzichten bevat, kun je, door te wisselen van tabblad, een overzicht van de documenten van een andere entiteit krijgen.
In een overzicht zijn verschillende acties beschikbaar voor de documenten. Ten eerste zijn er functies beschikbaar via de
knoppen boven het overzicht: 'Toevoegen', 'Verwijderen' en 'Bulk' (meer over 'Bulk' onder de kop [Wat is bulk bewerken en hoe
gebruik ik het?](#bulk).

![Screenshot Base Functions](/assets/img/basisFuncties.png)

Ook zijn er acties mogelijk wanneer de gebruiker met de rechtermuisknop op een document klikt: 'Bewerken', 'Verwijderen'
en 'Kopieren'.

![Screenshot Right Click](/assets/img/rechterMuisknop.png)

Tot slot staan er ook nog twee opties achter ieder document, namelijk een potlood-icoon ('Bewerken') en een
prullenbak-icoon ('Verwijderen').

![Screenshot Icons](/assets/img/iconen.png)

Zodra een of meerdere objecten worden toegevoegd, bewerkt of gekopieerd, verschijnt er een nieuw scherm voor de gebruiker
waarin het document (opnieuw) kan worden ingevuld. Hierbij moet wel rekening worden gehouden met validatie (zie hieronder).

####<a class="anchor" name="validatie"></a> Validatie en gewijzigde velden
Validatie is een belangrijk aspect aan het opslaan van nieuwe of bewerkte documenten. Sommige zaken in een formulier moeten aan bepaalde eisen voldoen.
Zo moet bijvoorbeeld een e-mail adres altijd een '@'-karakter bevatten. Indien uw invoer hier niet aan voldoen, verschijnt er een rode
streep om het invoer-veld. Zo weet u dat de invoer hiervan dient te worden gecontroleerd.
In het voorbeeld hieronder is bijvoorbeeld "Aanhef" niet ingevuld, terwijl dit veld niet leeg mag zijn. Daarom is dit veld dus niet valide!

![Screenshot Invalid](/assets/img/nietValide.png)

Als een veld is aangepast door een gebruiker, zal het veld een rode driehoek krijgen. Dit veld is dan gemarkeerd als gewijzigd en zo kan de gebruiker eenvoudig zien welke velden de originele waardes nog hebben en welke zijn
aangepast. In het voorbeeld hieronder zijn de velden "Titel" en "Aanhef" gewijzigd en dus voorzien van zo'n rode driehoek.

![Screenshot dirty](/assets/img/dirty.png)

Het markeren van deze velden is handig voor bepaalde functionaliteiten. Een voorbeeld is dat wanneer een formulier wordt gesloten,
er dan een waarschuwing op het scherm verschijnt of je zeker weet dat je deze wijzigingen wilt annuleren.

####<a class="anchor" name="geschiedenis"></a> Geschiedenis is per document
Elke keer dat een document wordt opgeslagen, wordt dit toegevoegd aan de geschiedenis van dit document. Als er dan een
fout is gemaakt door een gebruiker, kan het document worden hersteld naar een eerdere versie (waarin de fout nog niet
aanwezig was). Deze versies kunnen worden gevonden in het formulier van het document (bijvoorbeeld wanneer een
document wordt bewerkt). Rechtsboven het formulier staat dan een menu met alle versies die beschikbaar zijn voor het
document. Er staat bij wanneer de versie is gemaakt en door wie, zodat de gebruiker precies de versie kan uitkiezen
die hij/zij nodig heeft. Via de bovenstaande markeringen is te zien wat er precies gewijzigd is ten opzichte van de huidige versie.

![Screenshot History](/assets/img/geschiedenis.png)

Mocht een document verwijderd zijn dan is ook "terug te draaien". Zie hiervoor het onderdeel "prullenbak".

####<a class="anchor" name="boxen"></a> Werking van documentboxen
In sommige formulieren kan een documentbox voorkomen. Dit zijn velden waarin een verwijzing wordt verwacht naar een
ander document. In het geval van een debiteur kan het bijvoorbeeld een verwijzing zijn naar een persoon of bedrijf.
Zodra de gebruiker de documentbox heeft geselecteerd, kan er een verwijzing worden toegevoegd. Dit kan op meerdere
manieren gebeuren.

* Een persoon kan worden gekozen uit de lijst die verschijnt. Dit gebeurt gewoon door op de betreffende persoon te
klikken. De lijst verschijnt zodra er op de box geklikt wordt.
![Screenshot Dropdown](/assets/img/comboboxDropdown.png)
* Als de gebruiker al weet welk object hij/zij wil toevoegen, kan hij/zij gewoon de naam of titel van het object intypen
in de combobox. Als het object bestaat, verschijnt het vanzelf onder de box. Als het document dan wordt aangeklikt, wordt
de verwijzing toegevoegd.
![Screenshot Search](/assets/img/comboboxZoeken.png)
* Tot slot kan er ook nog een nieuw document worden toegevoegd door op de "Maak nieuw"-knop te drukken onder de lijst van
de documentbox. Het nieuwe document wordt dan opgeslagen in de administratie.
![Screenshot New Combobox](/assets/img/comboboxNieuw.png)

####<a class="anchor" name="acties"></a> Opslaan, verwijderen en prullenbak
Zodra een nieuw of bewerkt document gevalideerd is, kan het worden opgeslagen door op de "Opslaan" knop rechtsonder
in het scherm te drukken.

![Screenshot Save](/assets/img/opslaan.png)

Opslaan houdt in dat het document naar de database gestuurd wordt, er komt een melding voor de gebruiker of het object
correct is opgeslagen en de gebruiker wordt terug gestuurd naar het overzicht van alle documenten.

Een document kan ook worden verwijderd. Dit wordt gedaan door op de verwijder knop linksonder in het scherm te
drukken (zie het voorbeeld hierboven). Zodra een document verwijderd wordt, komt het terecht in de prullenbak. Dit
zorgt ervoor dat het document niet voorgoed verwijderd is, maar nog altijd terug gezet kan worden. De prullenbak kan
worden bezocht door te gaan naar het menu "Overzichten" en dan "Prullenbak"

![Screenshot Bin](/assets/img/prullenbak.png)

####<a class="anchor" name="bulk"></a> Wat is bulk bewerken en hoe gebruik ik het?
Als je meerdere objecten tegelijk wilt wijzigen, kun je de bulk bewerk functie gebruiken. Het werkt op bijna dezelfde wijze
als de gewone bewerk-optie, behalve dan dat het formulier er anders uit ziet. In het formulier staan namelijk alleen de
gegevens die in alle geselecteerde objecten hetzelfde zijn. Als dus bijvoorbeeld de personen Henk de Vries en Henk de Ruiter
worden bewerkt, dan staat er in het formulier Voornaam: Henk, Tussenvoegsel: de, Achternaam: <niks>. Achternaam wordt niet
ingevuld, omdat de achternaam verschillend is van Henk de Vries en Henk de Ruiter. Het voorbeeld staat hieronder:

![Screenshot Bulk](/assets/img/bulk.png)

Zodra je dan bijvoorbeeld Achternaam: Vries invult, dan worden beide personen aangepast en krijgen beide personen dus
de achternaam "Vries": ze heten dus allebei Henk de Vries.

Dit is een handige functie voor als een grote hoeveelheid objecten tegelijk moet worden aangepast. Als bijvoorbeeld 20
personen een extra adres krijgen, kan deze functie gebruikt worden en kan door het eenmalig invullen van een formulier
dit probleem opgelost zijn, in plaats van 20 keer een persoon te moeten aanpassen.

Als een bulk bewerk formulier wordt opgeslagen, controleert het systeem of alle velden correct bewerkt zijn. Mocht dat
niet het geval zijn, dan krijgt het veld een rode rand en kan de gebruiker alsnog de correcte gegevens invullen.