---
layout: default
title: Geavanceerd sjabloongebruik
group: "client"
weight: 5
---

#### Algemene informatie
Voor het opmaken van facturen, e-mails en brieven wordt HTML als opmaaktaal gebruikt. PDF documenten, zoals facturen, worden
opgesteld op basis van HTML opmaak instructies. Dit maakt het inrichten van opmaak zo eenduidig en eenvoudig mogelijk. Voor
gevanceerde functies van sjablonen is (enige) ervaring met HTML een pré.

Bovenop de opmaak-taal HTML wordt gebruik gemaakt van de sjabloon-taal ```Handlebars```. In het hoofdstuk [Contact met leden](/client/contact/#mailmerge)
is de basis-werking reeds besproken. Voor meer informatie over de inhoudelijke werking kunt u terecht op de website van het
[Handlebars project](http://handlebarsjs.com/). Experimenteren met constructies kan via [een speciale site](http://tryhandlebarsjs.com/)

####<a class="anchor" name="alsdan"></a> Als-dan vergelijkingen

Eenvoudige als-dan controles kunt u doen via {{ "{{ #if " }}}}. Bekijk het volgende voorbeeld:

    {{ "{{#if firstName" }}}}
        Hoi {{ "{{ firstName" }}}},
    {{ "{{else" }}}}
        L.s.
    {{ "{{/if" }}}}

Wanneer in uw e-mail, factuur of brief er een bekende ```firstName``` door het systeem kan worden bepaald (bijv. ```Karin```), zal de
uitvoer in het document zijn:

Hoi Karin,

Wanneer er geen firstName kan worden herleid, valt wordt het alternatief getoond:

L.s.

Bedenk dat de sjabloon-taal kijkt naar de engelse, technische benaming van velden. Welke velden beschikbaar zijn hangt
af van de procedure waarin u het sjabloon gebruikt. Bekijk een van de bestaande voorbeelden voor meer informatie.

####<a class="anchor" name="complex"></a> Complexere Vergelijkingen

In bepaalde gevallen is het niet mogelijk om met eenvoudige vergelijkingen het gewenste resultaat te bereiken. In deze gevallen
kan een uitgebreidere help-functie worden gebruikt welke in de Communibase Client beschikbaar is. Neem het volgende voorbeeld:


    {{ "{{#compare paymentType 'directDebit'" }}}}
        Deze factuur wordt geincasseerd.
    {{ "{{/compare"}}}}

In dit geval wordt de zin ```Deze factuur wordt geincasseerd.``` alleen getoond, wanneer het veld ```paymentType``` in een bepaalde
context de waarde ```directDebit``` bevat. Er is ook nog geavanceerder gebruik mogelijk, bijvoorbeeld:

    {{ "{{#compare openAmount 'gt' 100 "}}}}
        Deelbetaling is mogelijk
    {{ "{{/compare" }}}}

Dit maakt het mogelijk om, bijvoorbeeld op een factuur, bij een totaalbedrag van meer dan 100 euro de melding
```Deelbetaling is mogelijk``` op de factuur op te nemen.

#####<a class="anchor" name="lijst"></a> Lijst operatoren

'eq' ( '==' )
:  Dit is een `gelijk aan`-vergelijking. Dit is tevens de *standaard* vergelijking als er geen expliciete operator is meegegeven.
 Een voorbeeld is hierboven al gebruikt.

'eqeq' ( '===' )
: Dit is een `stricte gelijk aan`-vergelijking. Hierbij is de typering van belang. Een tekst en een getal wat als
tekst wordt gebruikt zijn dan niet gelijk.
 bv. '12' en 12 niet *niet gelijk*

'neq' ( '!=' )
: Dit is een `niet gelijk aan`-vergelijking.
 bv.
    {{ "{{#compare paymentType 'neq' 'directDebit'" }}}}
        Deze factuur wordt niet geincasseerd.
    {{ "{{/compare"}}}}

'neqeq' ( '!==' )
: Dit is een `niet exact gelijk aan`-vergelijking.
 bv.
    {{ "{{#compare openAmount 'neqeq' '100'" }}}}
        Dit zal niet getoond worden omdat openAmount een getal is, maar '100' hier een tekst.
    {{ "{{/compare"}}}}

'lt' ( '<' )
: Dit is een `kleiner dan`-vergelijking.
 bv.
    {{ "{{#compare openAmount 'lt' 5" }}}}
        Uw factuur valt onder onze grens waarde van € 5,- en dus wordt er geen bedrag in rekening gebracht.
    {{ "{{/compare"}}}}

'gt' ( '>' )
: Dit is een `groter dan`-vergelijking.
  bv.
     {{ "{{#compare openAmount 'gt' 10000" }}}}
         Op uw factuur staat een dermate hoog bedrag open dat wij contact met u opnemen.
     {{ "{{/compare"}}}}

'lte' ( '<=' )
: Dit is een `kleinder dan of gelijk aan`-vergelijking.
   bv.
      {{ "{{#compare openAmount 'lte' 10" }}}}
          het openstaande bedrag is kleiner of gelijk aan 10.
      {{ "{{/compare"}}}}

'gte' ( '>=' )
: Dit is een `groter dan of gelijk aan`-vergelijking.
    bv.
       {{ "{{#compare openAmount 'gte' 10" }}}}
           het openstaande bedrag is groter of gelijk aan 10.
       {{ "{{/compare"}}}}

'mod' ( '%' )
: Dit is een `modulo`-vergelijking.
    bv.
       {{ "{{#compare @key 'mod' 2 }}}}
          toon alleen de "even"-rijen van een lijst.
       {{ "{{/compare"}}}}

'regexp'
: Op deze manier kunt u met Reguliere Expressies (tekst-patronen) vergelijken.

'typeof'
: Dit is een technisch type-vergelijking en alleen bedoeld voor meer geavanceerde toepassingen.

####<a class="anchor" name="datum"></a> Datumvelden

In Communibase beschrijft een datumveld een moment in de tijd. Dit is dus naast een datum ook een tijd, maar dit wordt
in veel gevallen niet getoond. De presentatie is afhankelijk van de gewenste notatievorm. Datumnotatie kan in veel gevallen
op een andere manier gewenst zijn. Waar in Nederland bijvoorbeeld vaak de aanduiding dag-maand-jaar gebruikelijk is, is
dit in het buitenland vaak anders. Hoe een datum geschreven dient te worden hangt dus af van de manier waarop u de datum
gebruikt. Hiervoor is ook een help-functie ingericht:

    Uw lidmaatschap begon op {{ "{{dateFormat startDate" }}}}

Soms is het wenselijk om een datum als ```tot-en-met``` weer te geven. Een lidmaatschap kan bijvoorbeeld lopen tot 1 januari
van het volgende jaar, maar het kan dan wenselijk zijn om iets weer te geven als ```tot en met 31 december```. In dat geval
kunt gebruik maken van de volgende notatie.

    Uw lidmaatschap verloopt op {{ "{{untilDateFormat endDate" }}}}

Plaatst bijvoorbeeld in een sjabloon voor bijvoorbeeld een brief n.a.v. een lidmaatschap, de nederlandse notatie van de
startdatum van een lidmaatschap (bijv. ```1 januari 2015``` ). Alternatieve notatie is mogelijk als volgt:

    Your membership started {{ "{{dateFormat startDate format='j F Y'" }}}}


Formaatcodes zijn als volgt te gebruiken:

    Format      Description                                                               Example returned values
    ------      -----------------------------------------------------------------------   -----------------------
      d         Day of the month, 2 digits with leading zeros                             01 to 31
      D         A short textual representation of the day of the week                     Mon to Sun
      j         Day of the month without leading zeros                                    1 to 31
      l         A full textual representation of the day of the week                      Sunday to Saturday
      N         ISO-8601 numeric representation of the day of the week                    1 (for Monday) through 7 (for Sunday)
      S         English ordinal suffix for the day of the month, 2 characters             st, nd, rd or th. Works well with j
      w         Numeric representation of the day of the week                             0 (for Sunday) to 6 (for Saturday)
      z         The day of the year (starting from 0)                                     0 to 364 (365 in leap years)
      W         ISO-8601 week number of year, weeks starting on Monday                    01 to 53
      F         A full textual representation of a month, such as January or March        January to December
      m         Numeric representation of a month, with leading zeros                     01 to 12
      M         A short textual representation of a month                                 Jan to Dec
      n         Numeric representation of a month, without leading zeros                  1 to 12
      t         Number of days in the given month                                         28 to 31
      L         Whether it's a leap year                                                  1 if it is a leap year, 0 otherwise.
      o         ISO-8601 year number (identical to (Y), but if the ISO week number (W)    Examples: 1998 or 2004
                belongs to the previous or next year, that year is used instead)
      Y         A full numeric representation of a year, 4 digits                         Examples: 1999 or 2003
      y         A two digit representation of a year                                      Examples: 99 or 03
      a         Lowercase Ante meridiem and Post meridiem                                 am or pm
      A         Uppercase Ante meridiem and Post meridiem                                 AM or PM
      g         12-hour format of an hour without leading zeros                           1 to 12
      G         24-hour format of an hour without leading zeros                           0 to 23
      h         12-hour format of an hour with leading zeros                              01 to 12
      H         24-hour format of an hour with leading zeros                              00 to 23
      i         Minutes, with leading zeros                                               00 to 59
      s         Seconds, with leading zeros                                               00 to 59
      u         Decimal fraction of a second                                              Examples:
                (minimum 1 digit, arbitrary number of digits allowed)                     001 (i.e. 0.001s) or
                                                                                          100 (i.e. 0.100s) or
                                                                                          999 (i.e. 0.999s) or
                                                                                          999876543210 (i.e. 0.999876543210s)
      O         Difference to Greenwich time (GMT) in hours and minutes                   Example: +1030
      P         Difference to Greenwich time (GMT) with colon between hours and minutes   Example: -08:00
      T         Timezone abbreviation of the machine running the code                     Examples: EST, MDT, PDT ...
      Z         Timezone offset in seconds (negative if west of UTC, positive if east)    -43200 to 50400
      c         ISO 8601 date
                Notes:                                                                    Examples:
                1) If unspecified, the month / day defaults to the current month / day,   1991 or
                   the time defaults to midnight, while the timezone defaults to the      1992-10 or
                   browser's timezone. If a time is specified, it must include both hours 1993-09-20 or
                   and minutes. The "T" delimiter, seconds, milliseconds and timezone     1994-08-19T16:20+01:00 or
                   are optional.                                                          1995-07-18T17:21:28-02:00 or
                2) The decimal fraction of a second, if specified, must contain at        1996-06-17T18:22:29.98765+03:00 or
                   least 1 digit (there is no limit to the maximum number                 1997-05-16T19:23:30,12345-0400 or
                   of digits allowed), and may be delimited by either a '.' or a ','      1998-04-15T20:24:31.2468Z or
                Refer to the examples on the right for the various levels of              1999-03-14T20:24:32Z or
                date-time granularity which are supported, or see                         2000-02-13T21:25:33
                http://www.w3.org/TR/NOTE-datetime for more info.                         2001-01-12 22:26:34
      U         Seconds since the Unix Epoch (January 1 1970 00:00:00 GMT)                1193432466 or -2138434463
      MS        Microsoft AJAX serialized dates                                           \/Date(1238606590509)\/ (i.e. UTC milliseconds since epoch) or
                                                                                          \/Date(1238606590509+0800)\/
      time      A javascript millisecond timestamp                                        1350024476440
      timestamp A UNIX timestamp (same as U)                                              1350024866


####<a class="anchor" name="prijs"></a> Prijsvelden

Ook prijs-notatie kan afhankelijk zijn van factoren, zoals valuta. Ook hiervoor is een help-functie beschikbaar, deze
kan als volgt gebruikt worden:

    {{ "{{price total" }}}}

Maakt van een totaalbedrag van 100.1231 (technische aanduiding) de tekst € 100,12 .

####<a class="anchor" name="briefpapier"></a> Briefpapier

U kunt in Communibase briefpapier instellen voor facturen of andere PDF-documenten. Dit kunt u doen door in de broncode
het gewenste briefpapier te vermelden in de broncode als onderdeel van de <body>-tag. Ergens aan het begin van uw sjabloon
kan bijvoorbeeld in de broncode staan:

    <body letterPaper="http://www.kingsquare.nl/img/briefpapier.png">

Daarmee geeft u aan dat dit bestand mag worden gebruikt als briefpapier. Briefpapier wordt achter uw .pdf geplaatst, wanneer
deze opgesteld wordt voor digitaal gebruik. (Dus bijvoorbeeld om een .pdf te e-mailen.). Voor een normale "brief" wordt het
briefpapier doorgaans niet geplaatst: u kunt het document op uw eigen briefpapier uitprinten.

Het briefpapier wordt automatisch op het eerste en op volgbladen geplaatst. De print-marges die op de 1e en op volgbladen
komen zijn niet via HTML in te stellen: HTML is immers in principe gemaakt om webpagina's op te maken, voor drukwerk zullen
we hier dus een alternatief moeten vinden. Printmarges kunt u instellen in een document door het volgende blokje code op te
nemen;

    <script type="text/javascript">
        PhantomJSPrinting = {
            "margin": {
                "top": "320px",
                "left": "100px",
                "bottom": "240px",
                "right": "100px"
             }
        };
    </script>

Achter de termen top, left, bottom en right kunt u respectievelijk de marges opgeven in pixels welke bij het printen op
.pdf, per blad zouden moeten worden gehanteerd. U kunt het blokje code op een willekeurige plaats neerzetten, bijvoorbeeld
direct na de ```<body>```-tag.
