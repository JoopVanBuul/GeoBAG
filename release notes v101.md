De 1.0.1-release is een bug-fix release van de StUF-Geo BAG berichtenstandaard.

De volgende issues zijn opgelost:

#3 Koppelvlak Geo-BAG berichtenverkeer 1.0 onduidelijk voor goedkeuringsbericht bij constatering door Geo (MANTIS: 4740)

#4 Voetnoot 21: 'geen BAG-identificatie' i.p.v. 'een BAG-identificatie' (MANTIS: 4695)

#5 fout geo-bag berichtenverkeer t.a.v. voetnoot 31 (MANTIS: 4665)

#7 fout geo-bag berichtenverkeer t.a.v. positionering pag. 6 (MANTIS: 4663)

#8 Stuurgegevens voor een geometrieLevering zijn gedefinieerd als stuurgegevens voor een geometrieVerzoek

#11 Gebeurtenis bgrSSVSAMEN en bgrSSVSPLITS hebben dezelfde code in Geo-BAG berichtenverkeer

#18 Multipliciteit Brondocument [1-1] niet juist

#21 tijdvakGeldigheid/beginGeldigheid moet optioneel zijn bij geometrieLevering

Gedeeltelijk opgelost is issue: 

#10 Gebeurteniscode BGR-MAV en BGR-HMO komen niet voor in StUF-BG.


_Nog op te lossen in deze versie:_

#1 Statussen bij overigTerrein en overigGebouwdObject (MANTIS: 4936)

#25 Specificeren welke BAG-kennisgevingen BGT relevante inhoud bevatten

***1-inleiding.md***

Aanpassing tekst positionering naar Dit koppelvlak is als apart sectormodel (geoBAG) gepositioneerd NAAST de BAG berichtencatalogus. (issue #7)

***2-uitgangspunten.md***

In voetnoot 21 'een BAG-identificatie' aangepast naar 'geen BAG-identificatie' (issue #4)

***3-scenarios.md***

Voetnoot 31 verwijderd (issue #5)

In 3.7.2 Aanpassing volgorde basisscenario Constatering eo signalering door Geo (issue #3)

***bijlage1-gebeurtenissen.md***

Gebeurtenis BGR-MAV aangepast naar BGR-MAB (issue #10)

Gebeurtenis BGR-HMO verwijderd (issue #10)

Gebeurtenis BGR-SSV aangepast naar BGR-SSVSAMEN en BGR-SSVSPLITS voor resp. samenvoegen VBO's en splitsen VBO's (issue #11)

***xmlschema/1.0.1-concept/geoBAG0101/geoBAG0101_bg0310_ent.xsd***

Attribuut nillable="true" verwijderd bij alle verplichte geometrie (issue #5):

- Bij LIG-geoBAG-basis  element vlakGeometrie nillable="true" verwijderd
- Bij OGO-geoBAG-basis  element gbo.puntGeometrie nillable="true" verwijderd
- Bij OTR-geoBAG-basis  element vlakGeometrie nillable="true" verwijderd
- Bij PND-geoBAG-basis  element geometrie nillable="true" verwijderd
- Bij STA-geoBAG-basis  element vlakGeometrie nillable="true" verwijderd
- Bij VBO-geoBAG-basis  element gbo.puntGeometrie nillable="true" verwijderd
- Bij WPL-geoBAG-basis  element geometrie nillable="true" verwijderd

Attributen brondocument en tijdvakGeldigheid zijn optioneel gemaakt (issue #18 en issue #21):

- ComplexType LIG-geoBAG-basis-geometrieLevering toegevoegd waarin brondocument en tijdvakGeldigheid een minOccurs="0" hebben.
- ComplexType OGO-geoBAG-basis-geometrieLevering toegevoegd waarin brondocument en tijdvakGeldigheid een minOccurs="0" hebben.
- ComplexType OTR-geoBAG-basis-geometrieLevering toegevoegd waarin brondocument en tijdvakGeldigheid een minOccurs="0" hebben.
- ComplexType PND-geoBAG-basis-geometrieLevering toegevoegd waarin brondocument en tijdvakGeldigheid een minOccurs="0" hebben.			
- ComplexType STA-geoBAG-basis-geometrieLevering toegevoegd waarin brondocument en tijdvakGeldigheid een minOccurs="0" hebben.
- ComplexType VBO-geoBAG-basis-geometrieLevering toegevoegd waarin brondocument en tijdvakGeldigheid een minOccurs="0" hebben.
- ComplexType WPL-geoBAG-basis-geometrieLevering toegevoegd waarin brondocument en tijdvakGeldigheid een minOccurs="0" hebben.

***xmlschema/1.0.1-concept/geoBAG0101/geoBAG0101_bg0310_msg.xsd***

Bij gmlDi01 element stuurgegevens type gewijzigd naar geometrie "StUF:Stuurgegevens-geometrieLevering".  (tevens documentation aangepast naar geometrieLevering i.p.v. -Verzoek) (issue #8)

In gmlDi01 is bij de enteiten de extension gewijzigd naar het toegevoegde complexType in geoBAG0101_bg0310_ent.xsd (issue #18 en issue #21): 

- In gmlDi01 bij element 'ligplaats' de extension gewijzigd van 'LIG-geoBAG-basis' naar 'LIG-geoBAG-basis-geometrieLevering'.
- In gmlDi01 bij element 'overigGebouwObject' de extension gewijzigd van 'OGO-geoBAG-basis' naar 'OGO-geoBAG-basis-geometrieLevering'.
- In gmlDi01 bij element 'overigTerrein' de extension gewijzigd van 'OTR-geoBAG-basis' naar 'OTR-geoBAG-basis-geometrieLevering'.
- In gmlDi01 bij element 'pand' de extension gewijzigd van 'PND-geoBAG-basis' naar 'PND-geoBAG-basis-geometrieLevering'.
- In gmlDi01 bij element 'standplaats' de extension gewijzigd van 'STA-geoBAG-basis' naar 'STA-geoBAG-basis-geometrieLevering'.
- In gmlDi01 bij element 'verblijfsobject' de extension gewijzigd van 'VBO-geoBAG-basis' naar 'VBO-geoBAG-basis-geometrieLevering' (issue #18 en issue #21)
- In gmlDi01 bij element 'woonplaats' de extension gewijzigd van 'WPL-geoBAG-basis' naar 'WPL-geoBAG-basis-geometrieLevering' (issue #18 en issue #21)
