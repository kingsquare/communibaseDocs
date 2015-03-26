---
layout: default
title: Contact met leden
group: "client"
weight: 2
---

#### Wat is contact?
In Communibase kan alle communicatie met personen worden vastgelegd. Het betreft hier vaak e-mail, maar het systeem is ook
ingericht om zaken als faxen, brieven en telefoongesprekken te kunnen administreren. Op deze manier kan _alle_ relevante
informatie worden vastgelegd in één centraal systeem. Communibase is niet bedoeld als vervanging van jouw e-mail programma:
je kunt op de door jou gewenste manier blijven werken.

Soms kan het echter handig zijn om via het systeem te mailen. Zeker wanneer er in bulk e-mails worden uitgestuurd, biedt
het systeem diverse handvatten om eenvoudig de leden van een groep of de debiteuren voor bepaalde facturen snel, eenvoudig
en gepersonaliseerd te mailen.

####<a class="anchor" name="mailmerge"></a> Mailmerge velden
Als er een e-mail wordt opgesteld naar meerdere personen, bijvoorbeeld alle deelnemers van een bepaald evenement, kan
er bij het opstellen van de e-mail gebruik worden gemaakt van mailmerge velden. Zodra de betreffende personen naar het
veld ```Contact``` in het communibase menu gesleept worden, verschijnt de vraag ```Wilt u de e-mail personaliseren?```. Als er
wordt gekozen voor ```Ja```, en vervolgens voor ```Volgende stap```, ziet de gebruiker een voorbeeld e-mail. Dit ziet er
bijvoorbeeld als volgt uit:

![Screenshot mailmerge](/assets/img/mailmerge.png)

De stukken tekst tussen de dubbele accolades zijn mailmerge velden. Deze velden zijn variabelen die er voor iedere
ontvanger van de e-mail er anders uitzien. Als er bijvoorbeeld staat {{ debtor.salutation }}, wordt er per debiteur
de door hem/haar opgegeven aanhef gebruikt. Zo kan dezelfde e-mail er dus voor verschillende mensen er anders uitzien!
Dit is handig voor als er veel e-mails tegelijkertijd verstuurd worden. Een mailmerge veld kan worden toegevoegd
door op de toverstaf te drukken in het menu.

![Screenshot mailmerge "toverstaf"](/assets/img/toverstaf.png)

In de lijst die dan verschijnt kan de juiste waarde worden gekozen. Als de gebruiker begint te typen zonder iets te
selecteren in de lijst, worden de waardes in de lijst aangepast aan wat de gebruiker al heeft getypt. Als een gebruiker
bijvoorbeeld al ```invoice``` heeft ingetypt, zullen er alleen nog maar waardes beginnend met ```invoice``` worden laten zien.

####<a class="anchor" name="mailen"></a> Mailen naar personen, leden, deelnemers, debiteuren.
Buiten de "normale" manier om e-mails te maken en verzenden (bij het tabblad ```Contact``` een nieuwe e-mail toevoegen),
kunnen er ook objecten naar het Contact veld in het Communilinks menu gesleept worden. Deze handeling heeft verschillende
gevolgen aan de hand van welk type objecten er naar het veld gesleept worden. Als er personen gesleept worden, zal de e-mail
(vanzelfsprekend) naar het favoriete e-mail adres van deze personen gestuurd worden. Als dit het geval is bij bedrijven,
zal de contactpersoon van dit bedrijf een e-mail ontvangen. In het geval van groepsdeelnames, zullen
de leden (personen of bedrijven) en de debiteuren van deze groepsdeelname gecontacteerd worden. Zodra er evenementen
gesleept worden, zullen de verschillende deelnemers (en deelnemers van de sessies) een e-mail ontvangen. Tot slot kan
ook een factuur naar het Contact-veld gesleept worden en dan zal de debiteur van deze factuur een bericht krijgen.

####<a class="anchor" name="sync"></a> Mailsync
Mocht je ook de mail uit één of meer e-mailboxen in de administratie willen hebben, kan er een zogenaamde mailbox koppeling
worden geïnstalleerd. Deze zorgt ervoor dat e-mail uit bepaalde mailboxen automatisch wordt uitgelezen en gesynchroniseerd
naar Communibase. Neem contact op met Kingsquare voor de mogelijkheden.

####<a class="anchor" name="wizard"></a> Wizard
Als er contact wordt opgenomen met bijvoorbeeld een debiteur voor een factuur, dan komt de gebruiker terecht in een
wizard voor het maken van contact. Als een of meer facturen gesleept worden naar het veld ```Contact``` en
nog niet alle facturen zijn nog niet ```Definitief``` gemaakt, dan verschijnt eerste de vraag ```Wilt u deze facturen definitief
maken voordat deze naar de debiteur worden verstuurd?```. Het wordt aangeraden om de factuur eerst definitief te maken,
maar dit is niet noodzakelijk om de e-mail te kunnen versturen. Als u niet de factuur definitief maakt, betreft het
"proforma"-facturen.

Vervolgens verschijnt er een nieuw menu met verschillende mogelijke acties:

![Screenshot factuur wizard](/assets/img/contactActieMenu.png)

Als er wordt gekozen voor ```Verstuur factuur per e-mail```, dan komt de gebruiker in een voorbeeld e-mail waarin gebruik
gemaakt kan worden van mailmerge velden (zie hierboven). Voor de tweede optie ```Verstuur factuur per post``` geldt hetzelfde,
alleen zal er dan geen e-mail opgesteld worden, maar een pdf die uitgeprint en verstuurd kan worden. Tot slot kan er
nog gekozen worden voor ```Verstuur factuur volgens voorkeur debiteur``` en dan zal de voorkeursmedium van de debiteur
gebruikt worden om te beslissen welk medium gebruikt wordt voor het contact.