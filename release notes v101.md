Release notes StUF-Geo BAG versie 1.0.1 (Geo-BAG koppelvlak)
============================================================

De 1.0.1-release is een bug-fix release van de StUF-Geo BAG berichtenstandaard.

De volgende issues zijn opgelost:

Issue \#3 Koppelvlak Geo-BAG berichtenverkeer 1.0 onduidelijk voor
goedkeuringsbericht bij constatering door Geo (MANTIS: 4740)

Issue \#4 Voetnoot 21: 'geen BAG-identificatie' i.p.v. 'een BAG-identificatie'
(MANTIS: 4695)

Issue \#5 fout geo-bag berichtenverkeer t.a.v. voetnoot 31 (MANTIS: 4665)

Issue \#7 fout geo-bag berichtenverkeer t.a.v. positionering pag. 6 (MANTIS:
4663)

Issue \#8 Stuurgegevens voor een geometrieLevering zijn gedefinieerd als
stuurgegevens voor een geometrieVerzoek

Issue \#11 Gebeurtenis bgrSSVSAMEN en bgrSSVSPLITS hebben dezelfde code in
Geo-BAG berichtenverkeer

Issue \#18 Multipliciteit Brondocument [1-1] niet juist

Issue \#21 tijdvakGeldigheid/beginGeldigheid moet optioneel zijn bij
geometrieLevering

Issue \#26 enumeration value voor bevestigingDu01 ontbreekt

Issue \#27 Veldlengte voor foutcode-geoBAG te kort.

Issue \#28 Attribuutnaam niet gelijk: gmv: gebeurtenis && gml: gebeurtenisCode

Gedeeltelijk opgelost zijn issues:

Issue \#1 Statussen bij overigTerrein en overigGebouwdObject (MANTIS: 4936)

Issue \#10 Gebeurteniscode BGR-MAV en BGR-HMO komen niet voor in StUF-BG.

**1-inleiding.md**

Aanpassing tekst positionering naar Dit koppelvlak is als apart sectormodel
(geoBAG) gepositioneerd NAAST de BAG berichtencatalogus. (issue \#7)

**2-uitgangspunten.md**

In voetnoot 21 'een BAG-identificatie' aangepast naar 'geen BAG-identificatie'
(issue \#4)

**3-scenarios.md**

Voetnoot 31 verwijderd (issue \#5)

In 3.7.2 Aanpassing volgorde basisscenario Constatering eo signalering door Geo
(issue \#3)

**bijlage1-gebeurtenissen.md**

Gebeurtenis BGR-MAV verwijderd (issue \#10)

Gebeurtenis BGR-HMO verwijderd (issue \#10)

Gebeurtenis BGR-SSV aangepast naar BGR-SSVSAMEN en BGR-SSVSPLITS voor resp.
samenvoegen VBO's en splitsen VBO's (issue \#11)

Aan de gebeurtenissentabel is een kolom BGT-mutatie toegevoegd. In de kolom
‘BGT-mutatie’ wordt aangegeven of een BAG-kennisgeving met deze gebeurtenis
aanleiding geeft tot een bepaalde mutatie in de BGT. (issue \#25)

**xmlschema/1.0.1-concept/geoBAG0101/geoBAG0101\_bg0310\_ent.xsd**

De enumeraties van status voor Ligplaats, Standplaats en Verblijfsobject zijn
aangepast naar de juiste waardelijst (issue \#1):

-   In LIG-geoBAG-basis en LIG-geoBAG-basis-geometrieLevering bij aot.status het
    type gewijzigd naar BG:StatusLigplaatsStandplaats-e

-   In STA-geoBAG-basis en STA-geoBAG-basis-geometrieLevering bij aot.status het
    type gewijzigd naar BG:StatusLigplaatsStandplaats-e

-   In VBO-geoBAG-basis en VBO-geoBAG-basis-geometrieLevering bij aot.status het
    type gewijzigd naar BG:StatusVerblijfsobject-e

StUF:noValue toegevoegd voor voidable elementen (nillable=”true) om reden-leeg
te kunnen invullen; nillable=”true” verwijderd bij optionele elementen met
minOccurs=”0” (issue \#2 en issue \#32):

-   ComplexType ObjectNummering-geoBAG toegevoegd met restrictie op
    BG:Objectnummering-e voor toepassing attribuut StUF:noValue

-   ComplexType GeometrieVlak-geoBAG toegevoegd met restrictie op
    BG:GeometrieVlak-e voor toepassing attribuut StUF:noValue

-   ComplexType GeometriePunt-geoBAG toegevoegd met restrictie op
    BG:GeometriePunt-e voor toepassing attribuut StUF:noValue

-   Attribuut nillable="true" verwijderd bij element vlakGeometrie van
    OGO-geoBAG-basis en OGO-geoBAG-basis-geometrieLevering

-   Attribuut nillable="true" verwijderd bij element geometrieMaaiveld van
    PND-geoBAG-basis en PND-geoBAG-basis-geometrieLevering

-   Attribuut nillable="true" verwijderd bij element
    inwinningswijzeGeometrieMaaiveld van PND-geoBAG-basis en
    PND-geoBAG-basis-geometrieLevering

**xmlschema/1.0.1-concept/geoBAG0101/geoBAG0101\_bg0310\_msg.xsd**

Bij gmlDi01 element stuurgegevens type gewijzigd naar geometrie
"StUF:Stuurgegevens-geometrieLevering" (tevens documentation aangepast naar
geometrieLevering i.p.v. -Verzoek) (issue \#8)

De pattern voor de foutcodes in een afkeuringsbericht is aangepast conform de
koppelvlakspecificaties (issue \#27)

-   In simpleType FoutCode-geoBAG de pattern aangepast van 'StUFGeoBAG[0-9]{5}'
    naar '[a-zA-Z0-9]{7}'

De naamgeving van het gebeurteniscode-attribuut is consistent gemaakt met de
koppelvlakspecificatie (issen \#28)

-   In ParametersVerzoek het element 'gebeurtenis' hernoemt naar
    gebeurtenisCode'

**xmlschema/1.0.1-concept/geoBAG0101/geoBAG0101\_stuf0310\_msg.xsd**

De verplichte waarde van de StUF:functie voor elk bericht is consistent, kort en
duidelijk gemaakt (issue \#26)

-   Bij Functie-Bevestiging is enumeration 'goedkeuring' toegevoegd.

-   Bij Functie-Fout is enumeration gewijzigd naar 'afkeuring'.

-   Bij Functie-GeometrieLevering is enumeration gewijzigd naar 'levering'

-   Bij Functie-GeometrieVerzoek is enumeration gewijzigd naar 'verzoek'.

**GeoBAG/waardelijst/1.0.1-concept/codeList\_Gebeurtenis.rdf**

Gebeurtenis bgrSSVSAMEN en bgrSSVSPLITS hebben dezelfde code in Geo-BAG
berichtenverkeer (issue \#11)

-   Aanpassing BGR-SSV voor Samenvoegen en Splitsen naar resp. BGR-SSVSAMEN en
    BGR-SSVSPLITS
