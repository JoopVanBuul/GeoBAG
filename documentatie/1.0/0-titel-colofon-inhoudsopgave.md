# Koppelvlakspecificatie Geo-BAG berichtenverkeer

__Beschrijving koppelvlak tussen de registratiesystemen van Geo en BAG__

Geonovum

versie: v1.0
datum: 2 december 2015

## Colofon

Auteur: Arnoud de Boer

Beheer: Geonovum

Geonovum
Barchman Wuytierslaan 10,
3818 LH Amersfoort
Postbus 508
3800 AM Amersfoort
Email: info@geonovum.nl

De sequentiediagrammen in dit functioneel ontwerp zijn gemaakt met de online modelleersoftware van www.websequencediagrams.com.

###Licentie

Dit document is beschikbaar onder de volgende Creative Commons licentie:

http://creativecommons.org/licenses/by-nd/3.0/nl/

##Inhoudsopgave


1. Inleiding 5<br />
1.1 Waarom dit koppelvlak? 5<br />
1.2 Leeswijzer 5<br />
1.3 Verbinding met de GEMMA Informatiearchitectuur 6<br />
1.4 Referenties 8<br />
<br />
2. Uitgangspunten 10<br />
2.1 Actoren en verantwoordelijkheden: Geo en BAG 10 <br />
2.2 Berichten 10 <br />
2.3 Uitwisselen van gegevens van BAG-objecten 11 <br />
2.3.1 Objecttypen 11 <br />
2.3.1 Geometrie 11 <br />
2.3.2 Samengesteld uitwisselen en alleen actuele stand 12 <br />
2.4 Gebeurtenissen als aanleiding voor berichtenverkeer 12 <br />
2.5 Identificaties van en relaties tussen berichten 13 <br />
2.6 Corrigeren en intrekken van berichten 13 <br />
2.7 Identificaties van en relaties tussen objecten 14 <br />
2.8 Verzenden en verwerken van berichten 15 <br />
2.8.1 Transacties en bundeling van berichten 15<br />
2.8.2 Verplichte of niet-verplichte overname 15 <br />
2.8.3 Volgorde van verzenden en verwerken 15 <br />
2.8.4 Synchroniteit 16 <br />
<br />
3. Scenario’s 17<br />
3.1 Verzoek om geometrie door BAG 18 <br />
3.1.1 Basisscenario 18 <br />
3.1.2 Alternatief scenario: BAG keurt levering af 19 <br />
3.1.3 Alternatief scenario: BAG wil eerder verzonden geometrieVerzoek intrekken 19 <br />
3.1.4 Alternatief scenario: Geo keurt geometrieVerzoek af 20 <br />
3.2 Constatering en/of signalering door Geo 21 <br />
3.2.1 Basisscenario 21 <br />
3.2.2 Alternatief scenario: BAG keurt geometrie af 21 <br />
3.2.3 Alternatief scenario: Geo wil eerder verzonden geometrieLevering intrekken 22 <br />
3.3 Kennisgeving op object door BAG 23 <br />
<br />
4. Berichten 24<br />
4.1 StUF-Geo BAG berichten 24 <br />
4.1.1 GeometrieVerzoek 24 <br />
4.1.2 GeometrieLevering 25 <br />
4.1.3 Goedkeuringsbericht 26 <br />
4.1.4 Afkeuringsbericht 27 <br />
4.2 BAG-kennisgevingen 29 <br />
<br />
5. Entiteiten 30<br />
5.1 Entiteiten met objectgegevens 30 <br />
5.1.1 ligplaats 30 <br />
5.1.2 overigGebouwdObject 30 <br />
5.1.3 overigTerrein 30 <br />
5.1.4 pand 31 <br />
5.1.5 standplaats 32<br /> 
5.1.6 verblijfsobject 32 <br />
5.1.7 woonplaats 32 <br />
<br />
6. Attributen 33<br />
6.1 Parameters 33 <br />
6.1.1 idVerzoek 33 <br />
6.1.2 idLevering 33 <br />
6.1.3 gerelateerdVerzoek 33 <br />
6.1.4 gebeurtenisCode 33 <br />
6.1.5 documentverwijzing 34 <br />
6.1.6 toelichting 34 <br />
6.1.7 foutcode 34 <br />
6.1.8 foutomschrijving 34 <br />
6.1.9 plek 34 <br />
6.1.10 details 35 <br />
6.2 Elementen in entiteiten 35 <br />
6.2.1 identificatie 35 <br />
6.2.2 typering 35 <br />
6.2.3 adresAanduiding 35<br /> 
6.2.4 geometrie 36 <br />
6.2.5 puntGeometrie 36 <br />
6.2.6 vlakGeometrie 36 <br />
6.2.7 status 36 <br />
6.2.8 geconstateerd 36<br /> 
6.2.9 brondocument 37 <br />
6.2.10 tijdvakGeldigheid 37 <br />
6.2.11 maaktDeelUitVan 37 <br />
<br />
Bijlage 1 Gebeurtenissen 38 <br />
Bijlage 2 Activiteitenstroom koppelvlak Geo-BAG 40 <br />
Bijlage 3 Gegevensmodel koppelvlak Geo-BAG 42 <br />
Bijlage 4 Ontwerpbeslissingen en keuzes verStUFfing 43<br />
