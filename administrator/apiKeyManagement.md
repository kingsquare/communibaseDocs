---
layout: default
title: API sleutels beheren
group: "administrator"
weight: 4
---

#### Wat is een API sleutel?
Een API sleutel wordt gebruikt om te kijken welke gebruiker actief is in de administratie. Elke gebruiker krijgt, voor
elke afzonderlijke administratie, een API sleutel om eenvoudig te aan te tonen dat hij toegang heeft tot de administratie.
Deze API sleutel wordt dan meegegeven aan de administratie, om te voorkomen dat de gebruiker voor elke nieuwe pagina opnieuw
moet inloggen en het maakt de website dus een stuk sneller!

#### Het rechtensysteem
In Communibase wordt met het rechtensysteem bedoelt, dat gebruikers "rechten" kunnen hebben die ervoor zorgen
dat ze toegang hebben tot bepaalde administraties. Zo kan toegang tot administraties worden verleend aan gebruikers door
een administrator en ook kan toegang tot een administratie weer worden opgeheven. Dit kan worden gedaan in de "Communibase
Client" administratie onder de kop "Gebruiker". Als je daar een gebruiker selecteert, kun je bij de kop "Administratietoegang"
deze veranderingen maken.

Voor elke toegang die een gebruiker heeft, wordt een aparte API sleutel aangemaakt. Op deze manier heeft een gebruiker
dus recht om de administratie te bekijken en er veranderingen op te maken. Zo ontstaat dus het rechtensysteem, waarbij
verschillende gebruikers een andere administratietoegang kunnen hebben.

#### Een nieuwe API sleutel maken
Als een gebruiker toegang krijgt tot een administratie en daar in logt, dan wordt er automatisch een API sleutel voor
deze gebruiker en administratie aangemaakt. Dit is de meest eenvoudige manier om een API sleutel aan te maken en deze
manier zal ook het meest gebruikt worden. Het kan echter ook handmatig.

Een nieuwe API sleutel kun je handmatig aanmaken door naar de administratie van "Communibase beheer" te gaan. In de tab
"API sleutel" kunnen nieuwe API sleutels worden toegevoegd. Er moet dan een administratie worden opgegeven, een sleutel
worden gecreëerd (door op "Genereer nieuw wachtwoord" te klikken) en een passende omschrijving en e-mail adres worden
ingevoerd. Hieronder een voorbeeld van een ingevuld API sleutel formulier.

![Screenshot API key form](/assets/img/apiKey.png)