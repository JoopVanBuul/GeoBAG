Attributen
==========

Dit hoofdstuk beschrijft de attributen van de StUF-Geo BAG berichten en
objectkennisgevingen.

Parameters
----------

### idVerzoek

| Naam attribuut      | idVerzoek                              |
|---------------------|----------------------------------------|
| Definitie attribuut | Identificatie van het geometrieVerzoek |
| Herkomst            | StUF-Geo BAG                           |
| Multipliciteit      | [1-1]                                  |
| Waardetype          | String(40)                             |
| Waardenverzameling  |                                        |
| Toelichting         |                                        |

### idLevering

| Naam attribuut      | idLevering                              |
|---------------------|-----------------------------------------|
| Definitie attribuut | Identificatie van de geometrieLevering. |
| Herkomst            | StUF-Geo BAG                            |
| Multipliciteit      | [1-1]                                   |
| Waardetype          | String(40)                              |
| Waardenverzameling  |                                         |
| Toelichting         |                                         |

### gerelateerdVerzoek

| Naam attribuut      | gerelateerdVerzoek                                                                |
|---------------------|-----------------------------------------------------------------------------------|
| Definitie attribuut | Identificatie van het geometrieverzoek waarop een geometrielevering wordt gedaan. |
| Herkomst            | StUF-Geo BAG                                                                      |
| Multipliciteit      | [0..1]                                                                            |
| Waardetype          | String(40)                                                                        |
| Waardenverzameling  |                                                                                   |
| Toelichting         |                                                                                   |

### gebeurtenisCode

| Naam attribuut      | gebeurteniscode                                                            |
|---------------------|----------------------------------------------------------------------------|
| Definitie attribuut | BAG- of Geo gebeurtenis als aanleiding voor het verzoek/levering geometrie |
| Herkomst            | StUF-BG                                                                    |
| Multipliciteit      | [1-1]                                                                      |
| Waardetype          | string(var)                                                                |
| Waardenverzameling  | codeGebeurtenisList                                                        |
| Toelichting         | Zie bijlage 1 voor de waardenlijst.                                        |

### documentverwijzing

| Naam attribuut      | documentverwijzing                                      |
|---------------------|---------------------------------------------------------|
| Definitie attribuut | Verwijzing (URL) naar een achterliggend (bron)document. |
| Herkomst            | StUF-Geo BAG                                            |
| Multipliciteit      | [0..1]                                                  |
| Waardetype          | String(200)                                             |
| Waardenverzameling  |                                                         |
| Toelichting         |                                                         |

### toelichting

| Naam attribuut      | Toelichting                                      |
|---------------------|--------------------------------------------------|
| Definitie attribuut | Toelichting op het verzoek in de vorm van tekst. |
| Herkomst            | StUF-Geo BAG                                     |
| Multipliciteit      | [0..1]                                           |
| Waardetype          | String(500)                                      |
| Waardenverzameling  |                                                  |
| Toelichting         |                                                  |

### foutcode

| Naam attribuut      | Foutcode                                                                  |
|---------------------|---------------------------------------------------------------------------|
| Definitie attribuut | Code van de fout cf. standaard StUF of foutlijst StUF-Geo BAG sectormodel |
| Herkomst            | StUF                                                                      |
| Multipliciteit      | [1-1]                                                                     |
| Waardetype          | String(7)                                                                 |
| Waardenverzameling  |                                                                           |
| Toelichting         |                                                                           |

### foutomschrijving

| Naam attribuut      | foutomschrijving                        |
|---------------------|-----------------------------------------|
| Definitie attribuut | Toelichting op de fout als vrije tekst. |
| Herkomst            | StUF                                    |
| Multipliciteit      | [0..-1]                                 |
| Waardetype          | String(200)                             |
| Waardenverzameling  |                                         |
| Toelichting         |                                         |

### plek

| Naam attribuut      | plek                                |
|---------------------|-------------------------------------|
| Definitie attribuut | Plek waar de fout is geconstateerd. |
| Herkomst            | StUF                                |
| Multipliciteit      | [0..1]                              |
| Waardetype          | String()                            |
| Waardenverzameling  | "client", "server"                  |
| Toelichting         |                                     |

### details

| Naam attribuut      | details                |
|---------------------|------------------------|
| Definitie attribuut | Toelichting op de fout |
| Herkomst            | StUF                   |
| Multipliciteit      | [0..1]                 |
| Waardetype          | String(1000)           |
| Waardenverzameling  |                        |
| Toelichting         |                        |

Elementen in entiteiten
-----------------------

### identificatie

| Naam attribuut      | identificatie                |
|---------------------|------------------------------|
| Definitie attribuut | BAG-identificatie van object |
| Herkomst            | StUF-BG                      |
| Multipliciteit      | [1-1]                        |
| Waardetype          | String(16)                   |
| Waardenverzameling  |                              |
| Toelichting         |                              |

### typering

| Naam attribuut      | typering                                    |
|---------------------|---------------------------------------------|
| Definitie attribuut | typering van object                         |
| Herkomst            | StUF-BG                                     |
| Multipliciteit      | [1-1]                                       |
| Waardetype          | varchar                                     |
| Waardenverzameling  |                                             |
| Toelichting         | Bijv. Nummeraanduiding, Verblijfobject etc. |

### adresAanduiding

| Naam attribuut      | adresAanduidingGrp                       |
|---------------------|------------------------------------------|
| Definitie attribuut | Aanduiding van het adres van het object. |
| Herkomst            | StUF-BG                                  |
| Multipliciteit      | [1-1]                                    |
| Waardetype          | \<adresAanduidingGrp\>                   |
| Waardenverzameling  |                                          |
| Toelichting         |                                          |

### geometrie

| Naam attribuut      | Geometrie                                                    |
|---------------------|--------------------------------------------------------------|
| Definitie attribuut | De geometrie van het object                                  |
| Herkomst            | StUF-BG                                                      |
| Multipliciteit      | [1-1]                                                        |
| Waardetype          | GM_Surface                                                   |
| Waardenverzameling  |                                                              |
| Toelichting         | De geometrie is de vlakgeometrie van een Pand of Woonplaats. |

### puntGeometrie

| Naam attribuut      | puntGeometrie                                                                    |
|---------------------|----------------------------------------------------------------------------------|
| Definitie attribuut | De puntgeometrie van het object                                                  |
| Herkomst            | StUF-BG                                                                          |
| Multipliciteit      | [1-1]                                                                            |
| Waardetype          | GM_Point                                                                         |
| Waardenverzameling  |                                                                                  |
| Toelichting         | De geometrie is de puntgeometrie van een overigGebouwdObject of Verblijfsobject. |

### vlakGeometrie

| Naam attribuut      | vlakGeometrie                                                                                                                           |
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| Definitie attribuut | De vlakgeometrie van het object                                                                                                         |
| Herkomst            | StUF-BG                                                                                                                                 |
| Multipliciteit      | [1-1]                                                                                                                                   |
| Waardetype          | GM_Surface                                                                                                                              |
| Waardenverzameling  |                                                                                                                                         |
| Toelichting         | De geometrie is de vlakgeometrie van een Stand/Ligplaats of overigTerrein, of optioneel van een overigGebouwdObject of Verblijfsobject. |

### status

| Naam attribuut      | status                   |
|---------------------|--------------------------|
| Definitie attribuut | De status van het object |
| Herkomst            | StUF-BG                  |
| Multipliciteit      | [1-1]                    |
| Waardetype          | String                   |
| Waardenverzameling  |                          |
| Toelichting         |                          |

### geconstateerd

| Naam attribuut      | geconstateerd                        |
|---------------------|--------------------------------------|
| Definitie attribuut | Indicatie of object geconstateerd is |
| Herkomst            | StUF-BG                              |
| Multipliciteit      | [1-1]                                |
| Waardetype          | boolean                              |
| Waardenverzameling  |                                      |
| Toelichting         |                                      |

### brondocument

| Naam attribuut      | Brondocument                                          |
|---------------------|-------------------------------------------------------|
| Definitie attribuut | Het onderliggende brondocument van dit object         |
| Herkomst            | StUF-BG                                               |
| Multipliciteit      | [1-1]                                                 |
| Waardetype          | string                                                |
| Waardenverzameling  |                                                       |
| Toelichting         | Bevat de identificatie en datum van het brondocument. |

### tijdvakGeldigheid

| Naam attribuut      | beginGeldigheid                                                                                                |
|---------------------|----------------------------------------------------------------------------------------------------------------|
| Definitie attribuut | De datums waarop de geldigheid van gegevens van dit object begint (beginGeldigheid) en eindigt (eindGeldigheid |
| Herkomst            | StUF-BG                                                                                                        |
| Multipliciteit      | [1-1]                                                                                                          |
| Waardetype          | date                                                                                                           |
| Waardenverzameling  |                                                                                                                |
| Toelichting         |                                                                                                                |

### maaktDeelUitVan

| Naam attribuut      | maaktDeelUitVan                                                                                    |
|---------------------|----------------------------------------------------------------------------------------------------|
| Definitie attribuut | Verwijzing naar een Pand waartoe Verblijfsobject behoort.                                          |
| Herkomst            | StUF-BG                                                                                            |
| Multipliciteit      | [0-1]                                                                                              |
| Waardetype          | \<elementen\> van maaktDeelUitVan                                                                  |
| Waardenverzameling  |                                                                                                    |
| Toelichting         | Alleen bij Verblijfsobject. In XSD is de multipliciteit [1-1] met toepassing van een StUF:noValue. |
