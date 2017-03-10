# Hoofdstuk 6 Attributen 
Dit hoofdstuk beschrijft de attributen van de StUF-Geo BAG berichten en objectkennisgevingen. 

## 6.1 Parameters

### 6.1.1 idVerzoek

| Naam attribuut | idVerzoek |
| --- | --- |
| Definitie attribuut | Identificatie van het geometrieVerzoek |
| Herkomst | StUF-Geo BAG |
| Multipliciteit | [1-1] |
| Waardetype | String(40) |
| Waardenverzameling |   |
| Toelichting |    |

### 6.1.2 idLevering

| Naam attribuut | idLevering |
| --- | --- |
| Definitie attribuut | Identificatie van de geometrieLevering. |
| Herkomst | StUF-Geo BAG |
| Multipliciteit | [1-1] |
| Waardetype | String(40) |
| Waardenverzameling |   |
| Toelichting |    |

### 6.1.3 gerelateerdVerzoek

| Naam attribuut | gerelateerdVerzoek |
| --- | --- |
| Definitie attribuut | Identificatie van het geometrieverzoek waarop een geometrielevering wordt gedaan. |
| Herkomst | StUF-Geo BAG |
| Multipliciteit | [0..1] |
| Waardetype | String(40) |
| Waardenverzameling |   |
| Toelichting |    |

### 6.1.4 gebeurtenisCode

| Naam attribuut | gebeurteniscode |
| --- | --- |
| Definitie attribuut | BAG- of Geo gebeurtenis als aanleiding voor het verzoek/levering geometrie |
| Herkomst | StUF-BG |
| Multipliciteit | [1-1] |
| Waardetype | string(var) |
| Waardenverzameling | codeGebeurtenisList |
| Toelichting | Zie bijlage 1 voor de waardenlijst.  |

### 6.1.5 documentverwijzing

| Naam attribuut | documentverwijzing |
| --- | --- |
| Definitie attribuut | Verwijzing (URL) naar een achterliggend (bron)document. |
| Herkomst | StUF-Geo BAG |
| Multipliciteit | [0..1] |
| Waardetype | String(200) |
| Waardenverzameling |   |
| Toelichting |     |

### 6.1.6 toelichting

| Naam attribuut | Toelichting |
| --- | --- |
| Definitie attribuut | Toelichting op het verzoek in de vorm van tekst. |
| Herkomst | StUF-Geo BAG |
| Multipliciteit | [0..1] |
| Waardetype | String(500) |
| Waardenverzameling |   |
| Toelichting |    |

### 6.1.7 foutcode

| Naam attribuut | Foutcode |
| --- | --- |
| Definitie attribuut | Code van de fout cf. standaard StUF of foutlijst StUF-Geo BAG sectormodel |
| Herkomst | StUF |
| Multipliciteit | [1-1] |
| Waardetype | String(7) |
| Waardenverzameling |   |
| Toelichting |    |

### 6.1.8 foutomschrijving

| Naam attribuut | foutomschrijving |
| --- | --- |
| Definitie attribuut | Toelichting op de fout als vrije tekst. |
| Herkomst | StUF |
| Multipliciteit | [0..-1] |
| Waardetype | String(200) |
| Waardenverzameling |   |
| Toelichting |    |

### 6.1.9 plek

| Naam attribuut | plek |
| --- | --- |
| Definitie attribuut | Plek waar de fout is geconstateerd. |
| Herkomst | StUF |
| Multipliciteit | [0..1] |
| Waardetype | String() |
| Waardenverzameling | &quot;client&quot;, &quot;server&quot; |
| Toelichting |    |

### 6.1.10 details

| Naam attribuut | details |
| --- | --- |
| Definitie attribuut | Toelichting op de fout |
| Herkomst | StUF |
| Multipliciteit | [0..1] |
| Waardetype | String(1000) |
| Waardenverzameling |   |
| Toelichting |    |


## 6.2 Elementen in entiteiten
### 6.2.1 identificatie

| Naam attribuut | identificatie |
| --- | --- |
| Definitie attribuut | BAG-identificatie van object |
| Herkomst | StUF-BG |
| Multipliciteit | [1-1] |
| Waardetype | String(16) |
| Waardenverzameling |   |
| Toelichting |   |

6.2.2typering

| Naam attribuut | typering |
| --- | --- |
| Definitie attribuut | typering van object |
| Herkomst | StUF-BG |
| Multipliciteit | [1-1] |
| Waardetype | varchar |
| Waardenverzameling |   |
| Toelichting | Bijv. Nummeraanduiding, Verblijfobject etc. |

6.2.3adresAanduiding

| Naam attribuut | adresAanduidingGrp |
| --- | --- |
| Definitie attribuut | Aanduiding van het adres van het object. |
| Herkomst | StUF-BG |
| Multipliciteit | [1-1] |
| Waardetype | &lt;adresAanduidingGrp&gt; |
| Waardenverzameling |   |
| Toelichting | Binnen het element adresAanduidingGrp zijn uitsluitend de namen opgenomen van de woonplaats en de openbare ruimte en niet ook hun identificaties. Alle elementen zijn verplicht, ook aoa.woonplaatsWaarinGelegen /wpl.woonplaatsnaam. Indien het object ligt in de woonplaats aangeduid door wpl.woonplaatsnaam, dan dient in aoa.woonplaatsWaarinGelegen /wpl.woonplaatsnaam dezelfde waarde te worden opgenomen als inwpl.woonplaatsnaam, zo niet dan wordt woonplaats opgenomen waarin het adresseerbaar object feitelijk ligt. |

6.2.4 geometrie

| Naam attribuut | Geometrie |
| --- | --- |
| Definitie attribuut | De geometrie van het object |
| Herkomst | StUF-BG |
| Multipliciteit | [1-1] |
| Waardetype | GM\_Surface |
| Waardenverzameling |   |
| Toelichting | De geometrie is de vlakgeometrie van een Pand of Woonplaats.  |

6.2.5 puntGeometrie

| Naam attribuut | puntGeometrie |
| --- | --- |
| Definitie attribuut | De puntgeometrie van het object |
| Herkomst | StUF-BG |
| Multipliciteit | [1-1] |
| Waardetype | GM\_Point |
| Waardenverzameling |   |
| Toelichting | De geometrie is de puntgeometrie van een overigGebouwdObject of Verblijfsobject.  |

6.2.6 vlakGeometrie

| Naam attribuut | vlakGeometrie |
| --- | --- |
| Definitie attribuut | De vlakgeometrie van het object |
| Herkomst | StUF-BG |
| Multipliciteit | [1-1] |
| Waardetype | GM\_Surface |
| Waardenverzameling |   |
| Toelichting | De geometrie is de vlakgeometrie van een Stand/Ligplaats of overigTerrein, of optioneel van een overigGebouwdObject of Verblijfsobject.  |

6.2.7 status

| Naam attribuut | status |
| --- | --- |
| Definitie attribuut | De status van het object |
| Herkomst | StUF-BG |
| Multipliciteit | [1-1] |
| Waardetype | String |
| Waardenverzameling |   |
| Toelichting |    |

6.2.8 geconstateerd

| Naam attribuut | geconstateerd |
| --- | --- |
| Definitie attribuut | Indicatie of object geconstateerd is |
| Herkomst | StUF-BG |
| Multipliciteit | [1-1] |
| Waardetype | boolean |
| Waardenverzameling |   |
| Toelichting |    |

6.2.9brondocument

| Naam attribuut | Brondocument |
| --- | --- |
| Definitie attribuut | Het onderliggende brondocument van dit object |
| Herkomst | StUF-BG |
| Multipliciteit | [1-1] |
| Waardetype | string |
| Waardenverzameling |   |
| Toelichting | Bevat de identificatie en datum van het brondocument.  |

6.2.10 tijdvakGeldigheid

| Naam attribuut | beginGeldigheid |
| --- | --- |
| Definitie attribuut | De datums waarop de geldigheid van gegevens van dit object begint (beginGeldigheid) en eindigt (eindGeldigheid |
| Herkomst | StUF-BG |
| Multipliciteit | [1-1] |
| Waardetype | date |
| Waardenverzameling |   |
| Toelichting |   |

6.2.11 maaktDeelUitVan

| Naam attribuut | maaktDeelUitVan |
| --- | --- |
| Definitie attribuut | Verwijzing naar een Pand waartoe Verblijfsobject behoort. |
| Herkomst | StUF-BG |
| Multipliciteit | [0-1] |
| Waardetype | &lt;elementen&gt; van maaktDeelUitVan |
| Waardenverzameling |   |
| Toelichting | Alleen bij Verblijfsobject. In XSD is de multipliciteit [1-1] met toepassing van een StUF:noValue.  |
