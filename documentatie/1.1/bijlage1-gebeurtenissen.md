Bijlage 1: Gebeurtenissen
========================

De tabel in deze bijlage geeft een overzicht van de voor het Geo-BAG
berichtenverkeer relevante[\^40] BAG- en Geo-gebeurtenissen en tot welk bericht
een bepaalde gebeurtenis leidt[^1]. De lijst van BAG gebeurteniscodes is
overgenomen uit het landelijk vastgestelde BAG-processenhandboek. Voor Geo zijn
voor-dit-koppelvlak relevante gebeurtenissen toegevoegd.

[^1]:  

In de kolom ‘BGT-mutatie’ wordt aangegeven of een gebeurtenis aanleiding geeft
tot een bepaalde mutatie in de BGT:

A.  Toevoegen BGT Pand als planinformatie

B.  Beëindigen BGT Pand als planinformatie

C.  Toevoegen BGT Pand

D.  Wijzigen geometrie BGT Pand

E.  Wijzigen nummeraanduidingreeks van BGT Pand

F.  Beëindigen BGT Pand

G.  Toevoegen OpenbareRuimte(Label)

H.  Wijzigen naam OpenbareRuimte(Label)

I.  Beëindigen OpenbareRuimte(Label)

| **Code**      | **Gebeurtenis**                                                 | **Ontstaat bij** | **Aanleiding tot** | **BGT-mutatie** |
|---------------|-----------------------------------------------------------------|------------------|--------------------|-----------------|
| BAG-BN        | Benoemen nevenadres                                             | BAG              | BAG-kennisgeving   |               E |
| BAG-AGO       | Archivering geconstateerd object                                | BAG              | BAG-kennisgeving   | E,F             |
| BAG-AOC       | Archivering bestaand object na constatering                     | BAG              | BAG-kennisgeving   | E,F             |
| BAG-COR       | Correctie naar aanleiding van een signalering                   | BAG              | geometrieVerzoek   | C,D,E,F         |
| BAG-FGO       | Formalisering geconstateerd object                              | BAG              | BAG-kennisgeving   | E               |
| BAG-HLG       | Heropname legitiem gegeven                                      | BAG              | geometrieVerzoek   | C,E             |
| BAG-IN        | Intrekken adres                                                 | BAG              | BAG-kennisgeving   | E               |
| BAG-IO        | In onderzoek plaatsen                                           | BAG              | geometrieVerzoek   | B,D,E,F, H,I    |
| BAG-MUT       | Mutatie naar aanleiding van een signalering                     | BAG              | geometrieVerzoek   | C,D,E,F         |
| BAG-NEG       | Negeer eerder gestuurd GeometrieVerzoek                         | BAG              | geometrieVerzoek   |                 |
| BAG-VG        | Verbouwing gereed                                               | BAG              | geometrieVerzoek   | C               |
| BAG-VTP       | Verblijfsobject toevoegen aan pand                              | BAG              | geometrieVerzoek   | E               |
| BGR-BIG       | Beschikbaar gekomen ingemeten geometrie                         | BAG              | BAG-kennisgeving   | D               |
| BGR-BSLLP     | Benoemen ligplaats                                              | BAG              | geometrieVerzoek   |                 |
| BGR-BSLSP     | Benoemen standplaats                                            | BAG              | geometrieVerzoek   |                 |
| BGR-COG       | Constatering nieuw object                                       | BAG              | geometrieVerzoek   | C,E             |
| BGR-IBV       | Intrekken bouwvergunning                                        | BAG              | BAG-kennisgeving   | F               |
| BGR-ISLLP     | Intrekken ligplaats                                             | BAG              | BAG-kennisgeving   |                 |
| BGR-ISLSP     | Intrekken standplaats                                           | BAG              | BAG-kennisgeving   |                 |
| BGR-KVO       | Kleine verbouwing object                                        | BAG              | geometrieVerzoek   | D               |
| BGR-MAB       | Afzien van bouw                                                 | BAG              | BAG-kennisgeving   | F               |
| BGR-MGB       | Melding gebruiksgereed                                          | BAG              | geometrieVerzoek   |                 |
| BGR-MGS       | Melding sloop afgerond                                          | BAG              | BAG-kennisgeving   | E,F             |
| BGR-OBA       | Ontvangst bouwaanvraag                                          | BAG              | geometrieVerzoek   |                 |
| BGR-SSVSAMEN  | Samenvoegen verblijfsobjecten                                   | BAG              | geometrieVerzoek   | E               |
| BGR-SSVSPLITS | Splitsen verblijfsobjecten                                      | BAG              | geometrieVerzoek   | E               |
| BGR-VBI       | Verlenen bouwvergunning ingrijpende verbouwing                  | BAG              | geometrieVerzoek   | D,E             |
| BGR-VBN       | Verlenen bouwvergunning                                         | BAG              | geometrieVerzoek   | A               |
| BGR-VOCDEEL   | Gedeeltelijk verdwijnen objecten door calamiteit                | BAG              | BAG-kennisgeving   | D               |
| BGR-VOCHEEL   | Geheel verdwijnen objecten door calamiteit                      | BAG              | BAG-kennisgeving   | E,F             |
| BRA-BOR       | Benoemen openbare ruimte                                        | BAG              | BAG-kennisgeving   | G               |
| BRA-BWP       | Benoemen woonplaats                                             | BAG              | geometrieVerzoek   |                 |
| BRA-GHO       | Gedeeltelijk hernoemen openbare ruimte                          | BAG              | BAG-kennisgeving   | H               |
| BRA-HNU       | Hernummeren adresseerbaar object                                | BAG              | BAG-kennisgeving   | E               |
| BRA-HOR       | Hernoemen openbare ruimte                                       | BAG              | BAG-kennisgeving   | H               |
| BRA-IOR       | Intrekken openbare ruimte                                       | BAG              | BAG-kennisgeving   | I               |
| BRA-KWGW      | Kleine wijziging grens woonplaats                               | BAG              | geometrieVerzoek   |                 |
| BRA-OHN       | Hoofdadres en nevenadres van een adresseerbaar object omdraaien | BAG              | BAG-kennisgeving   | E               |
| BRA-WGW       | Wijzigen grens woonplaats                                       | BAG              | geometrieVerzoek   |                 | 
| GEO-AOC       | Constatering gesloopt object                                    | GEO              | geometrieLevering  | E,F             |
| GEO-COG       | Constatering nieuw object                                       | GEO              | geometrieLevering  | C,E             |
| GEO-MUT       | Constatering afwijkende geometrie                               | GEO              | geometrieLevering  | D               |
| GEO-NEG       | Negeer eerder gestuurd geometrielevering                        | GEO              | geometrielevering  |                 |


[^40] In werksessies met betrokken Geo- en BAG-leveranciers is een lijst
samengesteld met de voor dit koppelvlak relevant geachte gebeurtenissen op basis
van de vigerende versie van het landelijk vastgestelde BAG-Processenhandboek.
