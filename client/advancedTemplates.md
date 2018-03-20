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

    Your membership started {{ "{{dateFormat startDate format='D MMMM YYYY'" }}}}


Formaatcodes zijn als volgt te gebruiken:

|| Token|Output|
|--- |--- | -- |
|Month|M|1 2 ... 11 12|
||Mo|1st 2nd ... 11th 12th|
||MM|01 02 ... 11 12|
||MMM|Jan Feb ... Nov Dec|
||MMMM|January February ... November December|
|Quarter|Q|1 2 3 4|
||Qo|1st 2nd 3rd 4th|
|Day of Month|D|1 2 ... 30 31|
||Do|1st 2nd ... 30th 31st|
||DD|01 02 ... 30 31|
|Day of Year|DDD|1 2 ... 364 365|
||DDDo|1st 2nd ... 364th 365th|
||DDDD|001 002 ... 364 365|
|Day of Week|d|0 1 ... 5 6|
||do|0th 1st ... 5th 6th|
||dd|Su Mo ... Fr Sa|
||ddd|Sun Mon ... Fri Sat|
||dddd|Sunday Monday ... Friday Saturday|
|Day of Week (Locale)|e|0 1 ... 5 6|
|Day of Week (ISO)|E|1 2 ... 6 7|
|Week of Year|w|1 2 ... 52 53|
||wo|1st 2nd ... 52nd 53rd|
||ww|01 02 ... 52 53|
|Week of Year (ISO)|W|1 2 ... 52 53|
||Wo|1st 2nd ... 52nd 53rd|
||WW|01 02 ... 52 53|
|Year|YY|70 71 ... 29 30|
||YYYY|1970 1971 ... 2029 2030|
||Y|1970 1971 ... 9999 +10000 +10001|
|Week Year|gg|70 71 ... 29 30|
||gggg|1970 1971 ... 2029 2030|
|Week Year (ISO)|GG|70 71 ... 29 30|
||GGGG|1970 1971 ... 2029 2030|
|AM/PM|A|AM PM|
||a|am pm|
|Hour|H|0 1 ... 22 23|
||HH|00 01 ... 22 23|
||h|1 2 ... 11 12|
||hh|01 02 ... 11 12|
||k|1 2 ... 23 24|
||kk|01 02 ... 23 24|
|Minute|m|0 1 ... 58 59|
||mm|00 01 ... 58 59|
|Second|s|0 1 ... 58 59|
||ss|00 01 ... 58 59|
|Fractional Second|S|0 1 ... 8 9|
||SS|00 01 ... 98 99|
||SSS|000 001 ... 998 999|
||SSSS ... SSSSSSSSS|000[0..] 001[0..] ... 998[0..] 999[0..]|
|Time Zone|z or zz|EST CST ... MST PST|
||Z|-07:00 -06:00 ... +06:00 +07:00|
||ZZ|-0700 -0600 ... +0600 +0700|
|Unix Timestamp|X|1360013296|
|Unix Millisecond Timestamp|x|1360013296123|



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
