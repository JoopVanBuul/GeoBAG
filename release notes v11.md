Release notes StUF-Geo BAG versie 1.1 (Geo-BAG koppelvlak)
==========================================================

In BAG 2.0 zijn een aantal wijzingen doorgevoerd die ook horizontaal in het
Geo-BAG berichtenverkeer uitgewisseld gaan worden. Om die reden is het StUF-Geo
BAG berichtschema aangepast. De wijzigingen betreffen uitbreidingen van
attributen, geometrieën, veldlengten en statussen. Als gevolg daarvan
(B-wijziging), leidt dit tot een nieuwe versie van de berichtschema’s en
koppelvlak: StUF-Geo BAG versie 1.1.

Functioneel
-----------

De volgende functionele wijzigingen zijn doorgevoerd (zie ook
[\#50](https://github.com/Geonovum/GeoBAG/issues/50)):

-   Versie-identificatie is toegevoegd als onderdeel van de historie van een
    object

-   Woonplaatsgeometrie is uitgebreid met geometrietype multivlak

-   Het documentnummer van een brondocument is verlengd van 20 naar 40 karakters

-   De statussen van Pand en Verblijfobject zijn uitgebreid de statussen
    ‘Verbouwing …’ en ‘… ten onrechte opgevoerd’.

Technisch
---------

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

Overige issues
--------------

In deze versie worden naast de aanpassingen op BAG 2.0 de volgende issues
opgelost:

[\#49](https://github.com/Geonovum/GeoBAG/issues/49) Gebeurtenis Geo-CEG in
specificaties vervangen door Geo-COG

In de voetnoot behorende bij tabel 2. Voorbeeld intrekken en corrigeren van een
GeometrieVerzoek is de gebeurtenis Geo-CEG verwijderd. Voorts is de toelichting
op het invullen van de identificaties en technische sleutels in hoofdstuk 2
verder toegelicht.

[\#48](https://github.com/Geonovum/GeoBAG/issues/48) Gebeurtenissen in Geo-BAG
berichtenverkeer wijken af van BAG

In de documentatie en waardenlijst is het volgende aangepast:

-   BAG-AO Onderzoek afgerond toegevoegd

-   Definitie BAG-IN aangepast naar ‘Intrekken nevenadres’

In de documentatie is bij gebeurtenis BAG-VG Verbouwing gereed de BGT-mutatie
gewijzigd van 3(C)naar 4(D).

[\#46](https://github.com/Geonovum/GeoBAG/issues/46) sleutelVerzendend moet
sleutelOntvangend zijn bij goedkeurings en afkeuringsberichten.

In geoBAG0101_bg0310_ent.xsd is voor in complexType \*-geoBAG-identificatie voor
alle objecttypen de 'use' van attributen StUF:sleutelVerzendend en
StUF:sleutelOntvangend gewijzigd naar resp. 'optional' en 'required'.

[\#39](https://github.com/Geonovum/GeoBAG/issues/39) Opnemen samengestelde
attributen in H6

[\#38](https://github.com/Geonovum/GeoBAG/issues/38) Inconsistentie tussen
vullen woonplaatsWaarinGelegen in Geo-BAG en BAG

Toelichting in H6 bij adresAanduidingGrp is geschrapt omdat deze niet consistent
was met de invulling in het berichtschema.

[\#13](https://github.com/Geonovum/GeoBAG/issues/13) Multivlak geometrie wordt
niet ondersteund in Geo-BAG berichtenverkeer

In geoBAG0101_bg0310_ent.xsd is voor Woonplaats een choice toegevoegd voor Vlak
of Multivlak naar aanleiding van BAG 2.0 (zie hierboven).

In geoBAG0101_bg0310_ent.xsd is vergelijkbaar met Woonplaats opgenomen voor
maaiveld geometrie bij pand: het type GeometrieVlakOfMultiVlak-geoBAG-BAG20 met
choice tussen vlak of multivlak opgenomen als type van element
geometrieOpMaaiveld in complexType PND-geoBAG-basis

[\#6](https://github.com/Geonovum/GeoBAG/issues/6) fout geo-bag berichtenverkeer
t.a.v. aantal posities URL (MANTIS: 4664)

In complexType ParametersLevering en ParametersVerzoek is voor element
‘documentVerwijzing’ een nieuw SimpleType GeoBAGUrl met lengte 2000 gedefinieerd
en opgenomen. (In StUF-BG basisschema’s was BG:Url gedefinieerd met lengte 200).
