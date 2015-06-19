---
layout: default
title: Documentverwijzingen
group: "api"
---

Een minder "voor de hand liggende" data-constructie in Communibase zijn zogenaamde documentReferences (documentverwijzingen). De meest voorkomende documentverwijzigen zijn:

- `Membership.addressReference`
- `Membership.emailAddressReference`
- `Membership.phoneNumberReference`
- `Person.addressReference`
- `Person.emailAddressReference`
- `Person.phoneNumberReference`

Om even als voorbeeld `Membership.addressReference`` aan te houden: het beschrijft welk adres hoort bij het lidmaatschap. Dit kan zijn: een adres van de gekoppelde persoon, een adres van de gekoppeld organsatie of een compleet afwijkend adres. (de andere genoemde velden volgen dezelfde logica.)

Het beste kun je kijken naar een bestaand lidmaatschap waarbij het is ingevuld, bijvoorbeeld:
{
....

            "addressReference": {
                "documentReference": {
                    "rootDocumentEntityType": "Person",
                    "rootDocumentId": "557952b473940ab600a1dfea",
                    "path": [
                        {
                            "field": "addresses",
                            "objectId": "557951db261c1c094d000001",
                            "_id": "55795531a0ce45ba007fe882"
                        }
                    ]
                },
                "address": null
            },

....
}

`address` is hier null, dit betekent dat er geen afwijkend adres is gespecificeerd. Dit betekent dat er gekeken kan worden naar de verwijzing naar een bestaand adres, ergens in de administratie. Als het wél is ingevuld, volgt het de definitie van wat een "Address"-entiteit is binnen de adminstratie.

`addressReference.documentReference.rootDocumentEntityType` = "Person" => geeft aan dat dit van een Persoon in de adminsitratie kan worden gelezen.

`addressReference.documentReference.rootDocumentId` = "557952b473940ab600a1dfea" => geeft aan dat om welke persoon het gaat.

Om te weten welk adres het betreft zal dus eerst dit persoon-document moeten worden opgevraagd. Normaal gesproken is dit de persoon van wie het lidmaatschap is. Daarna kan binnen dit "Persoon"-document het gevraagde adres worden opgezocht. Dat werkt met het laatste kenmerk "addressReference.documentReference.path". Deze beschrijft de stappen binnen het persoon-document welke moeten worden doorlopen om tot het adres te komen. In dit voorbeeld zal dus in de "addresses" - lijst gezocht moeten worden naar het adres met id-nummer "557951db261c1c094d000001".

 De logica voor het "opzoeken" van de data achter verwijzingen is ook verwerkt in de verschillende [http://docs.communibase.nl/api#voorbeeldcode]("connectors")
