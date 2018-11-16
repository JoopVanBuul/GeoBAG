Release notes StUF-Geo BAG versie 1.1 (Geo-BAG koppelvlak)

In BAG 2.0 zijn een aantal wijzingen doorgevoerd die ook horizontaal in het
Geo-BAG berichtenverkeer uitgewisseld gaan worden. Om die reden is het StUF-Geo
BAG berichtschema aangepast. De wijzigingen betreffen uitbreidingen van
attributen, geometrieën, veldlengten en statussen. Als gevolg daarvan
(B-wijziging), a it leidt tot een nieuwe versie van de berichtschema’s en
koppelvlak: StUF-Geo BAG versie 1.1.

Functioneel
-----------

De volgende functionele wijzigingen zijn doorgevoerd:

-   Versie-identificatie is toegevoegd als onderdeel van de historie van een
    object

-   Woonplaatsgeometrie is uitgebreid met geometrietype multivlak

-   Het documentnummer van een brondocument is verlengd van 20 naar 40 karakters

-   De statussen van Pand en Verblijfobject zijn uitgebreid de statussen
    ‘Verbouwing …’ en ‘… ten onrechte opgevoerd’.

Technisch 
----------

De volgende technische wijzigingen zijn doorgevoerd:

In bestand **geoBAG0101/geoBAG0101_bg0310_ent.xsd**

1.  namespace wijzigt van geobag0100 naar geobag0101

2.  \*\*\*-geoBAG-basis en \*\*-geoBAG-identificatie is niet langer als
    restriction base op BG0310 gedefinieerd.

3.  element versie toegevoegd aan LIG, OTR, OGO, STA, PND, VBO met type
    versie-BAG20

4.  DocumentNummering-BAG20 met restricion maxLength=40 toegevoegd en opgenomen
    in nieuw complexType Brondocument-BAG20 en toegevoegd als type aan element
    brondocument in de \*\*\*-geoBAG-basis complexTypes

5.  BG:StatusPand is uitgebreid met twee BAG2.0 enumeraties en in union in nieuw
    simpletype StatusPand-geoBAG-BAG20 opgenomen als type van element status in
    complexType PND-geoBAG-basis

6.  BG:StatusVerblijfobject is uitgebreid met twee BAG2.0 enumeraties en in
    union in nieuw simpletype StatusVerblijfsobject-geoBAG-BAG20 opgenomen als
    type van element aot.status in complexType VBO-geoBAG-basis

7.  GeometrieVlakOfMultiVlak-geoBAG-BAG20 met choice tussen vlak of multivlak
    opgenomen als type van element geometrie in complexType WPL-geoBAG-basis
