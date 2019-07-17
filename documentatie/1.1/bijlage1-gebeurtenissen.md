Bijlage 1: Gebeurtenissen
=========================

De tabel in deze bijlage geeft een overzicht van de voor het Geo-BAG
berichtenverkeer relevante[\^40] BAG- en Geo-gebeurtenissen en tot welk bericht
een bepaalde gebeurtenis leidt[^1]. De lijst van BAG gebeurteniscodes is
overgenomen uit het landelijk vastgestelde BAG-processenhandboek. Voor Geo zijn
voor-dit-koppelvlak relevante gebeurtenissen toegevoegd.

[^1]:  

In de kolom ‘BGT-mutatie’ wordt aangegeven of een gebeurtenis aanleiding geeft
tot een bepaalde mutatie in de BGT:

1.  Toevoegen BGT Pand als planinformatie

2.  Beëindigen BGT Pand als planinformatie

3.  Toevoegen BGT Pand

4.  Wijzigen geometrie BGT Pand

5.  Wijzigen nummeraanduidingreeks van BGT Pand

6.  Beëindigen BGT Pand

7.  Toevoegen OpenbareRuimte(Label)

8.  Wijzigen naam OpenbareRuimte(Label)

9.  Beëindigen OpenbareRuimte(Label)

| **Code**      | **Gebeurtenis**                                                 | **Ontstaat bij** | **Aanleiding tot** | **BGT-mutatie** |
|---------------|-----------------------------------------------------------------|------------------|--------------------|-----------------|
| BAG-BN        | Benoemen nevenadres                                             | BAG              | BAG-kennisgeving   | 5               |
| BAG-AGO       | Archivering geconstateerd object                                | BAG              | BAG-kennisgeving   | 5,6             |
| BAG-AOC       | Archivering bestaand object na constatering                     | BAG              | BAG-kennisgeving   | 5,6             |
| BAG-COR       | Correctie naar aanleiding van een signalering                   | BAG              | geometrieVerzoek   | 3,4,5,6         |
| BAG-FGO       | Formalisering geconstateerd object                              | BAG              | BAG-kennisgeving   | 5               |
| BAG-HLG       | Heropname legitiem gegeven                                      | BAG              | geometrieVerzoek   | 3,5             |
| BAG-IN        | Intrekken nevenadres                                            | BAG              | BAG-kennisgeving   | 5               |
| BAG-AIO        | Attribuut in onderzoek plaatsen                                | BAG              | geometrieVerzoek   | 2,4,5,6, 8,9    |
| BAG-OA        | Onderzoek afgerond                                              | BAG              | geometrieVerzoek   | 2,4,5,6, 8,9    |
| BAG-MUT       | Mutatie naar aanleiding van een signalering                     | BAG              | geometrieVerzoek   | 3,4,5,6         |
| BAG-NEG       | Negeer eerder gestuurd GeometrieVerzoek                         | BAG              | geometrieVerzoek   |                 |
| BAG-VG        | Verbouwing gereed                                               | BAG              | geometrieVerzoek   | 4               |
| BAG-VTP       | Verblijfsobject toevoegen aan pand                              | BAG              | geometrieVerzoek   | 5               |
| BGR-BIG       | Beschikbaar gekomen ingemeten geometrie                         | BAG              | BAG-kennisgeving   | 4               |
| BGR-BSLLP     | Benoemen ligplaats                                              | BAG              | geometrieVerzoek   |                 |
| BGR-BSLSP     | Benoemen standplaats                                            | BAG              | geometrieVerzoek   |                 |
| BGR-COG       | Constatering nieuw object                                       | BAG              | geometrieVerzoek   | 3,5             |
| BGR-IBV       | Intrekken bouwvergunning                                        | BAG              | BAG-kennisgeving   | 6               |
| BGR-ISLLP     | Intrekken ligplaats                                             | BAG              | BAG-kennisgeving   |                 |
| BGR-ISLSP     | Intrekken standplaats                                           | BAG              | BAG-kennisgeving   |                 |
| BGR-KVO       | Kleine verbouwing object                                        | BAG              | geometrieVerzoek   | 4               |
| BGR-MAB       | Afzien van bouw                                                 | BAG              | BAG-kennisgeving   | 6               |
| BGR-MGB       | Melding gebruiksgereed                                          | BAG              | geometrieVerzoek   |                 |
| BGR-MGS       | Melding sloop afgerond                                          | BAG              | BAG-kennisgeving   | 5,6             |
| BGR-OBA       | Ontvangst bouwaanvraag                                          | BAG              | geometrieVerzoek   |                 |
| BGR-SSVSAMEN  | Samenvoegen verblijfsobjecten                                   | BAG              | geometrieVerzoek   | 5               |
| BGR-SSVSPLITS | Splitsen verblijfsobjecten                                      | BAG              | geometrieVerzoek   | 5               |
| BGR-VBI       | Verlenen bouwvergunning ingrijpende verbouwing                  | BAG              | geometrieVerzoek   | 4,5             |
| BGR-VBN       | Verlenen bouwvergunning                                         | BAG              | geometrieVerzoek   | 1               |
| BGR-VOCDEEL   | Gedeeltelijk verdwijnen objecten door calamiteit                | BAG              | BAG-kennisgeving   | 4               |
| BGR-VOCHEEL   | Geheel verdwijnen objecten door calamiteit                      | BAG              | BAG-kennisgeving   | 5,6             |
| BRA-BOR       | Benoemen openbare ruimte                                        | BAG              | BAG-kennisgeving   | 7               |
| BRA-BWP       | Benoemen woonplaats                                             | BAG              | geometrieVerzoek   |                 |
| BRA-GHO       | Gedeeltelijk hernoemen openbare ruimte                          | BAG              | BAG-kennisgeving   | 8               |
| BRA-HNU       | Hernummeren adresseerbaar object                                | BAG              | BAG-kennisgeving   | 5               |
| BRA-HOR       | Hernoemen openbare ruimte                                       | BAG              | BAG-kennisgeving   | 8               |
| BRA-IOR       | Intrekken openbare ruimte                                       | BAG              | BAG-kennisgeving   | 9               |
| BRA-KWGW      | Kleine wijziging grens woonplaats                               | BAG              | geometrieVerzoek   |                 |
| BRA-OHN       | Hoofdadres en nevenadres van een adresseerbaar object omdraaien | BAG              | BAG-kennisgeving   | 5               |
| BRA-WGW       | Wijzigen grens woonplaats                                       | BAG              | geometrieVerzoek   |                 |
| GEO-AOC       | Constatering gesloopt object                                    | GEO              | geometrieLevering  | 5,6             |
| GEO-COG       | Constatering nieuw object                                       | GEO              | geometrieLevering  | 3,5             |
| GEO-MUT       | Constatering afwijkende geometrie                               | GEO              | geometrieLevering  | 4               |
| GEO-NEG       | Negeer eerder gestuurd geometrielevering                        | GEO              | geometrielevering  |                 |

[\^40] In werksessies met betrokken Geo- en BAG-leveranciers is een lijst
samengesteld met de voor dit koppelvlak relevant geachte gebeurtenissen op basis
van de vigerende versie van het landelijk vastgestelde BAG-Processenhandboek.
