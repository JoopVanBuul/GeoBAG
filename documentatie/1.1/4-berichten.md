# Berichten 

Dit hoofdstuk beschrijft de berichten in het berichtenverkeer tussen BAG en Geo. Enerzijds wordt hergebruik gemaakt van bestaande StUF-BAG kennisgevingsberichten en StUF bevestigings- en foutberichten, anderzijds zijn eigen voor dit koppelvlak specifieke StUF-Geo BAG gedefinieerd. 

## StUF-Geo BAG berichten 
De StUF-Geo BAG berichten geometrieVerzoek en geometrieLevering zijn eigen voor dit koppelvlak specifieke berichten. De berichten bevatten de volgende elementen: 

* Logistieke gegevens: standaard StUF-stuurgegevens bevatten o.a. de logistieke identificatie en gegevens van zender/ontvanger. 
* Procesgegevens: bevatten o.a. de functionele identificatie, een toelichting en verwijzing naar een gerelateerde (bron)document. 
* Inhoud: een objectkennisgeving met de gegevens van een BAG-object. Een objectkennisgeving bevat alleen de verplichte gegevens van een van de BAG-objecten. 

### GeometrieVerzoek 

| Naam bericht  | geometrieVerzoek | 
|---------------|------------------|
|Afkorting bericht | gmvDi01 |
| Herkomst | StUF-Geo BAG |
| Berichtcode | Di01 
| Omschrijving  | Een geometrieVerzoek is een verzoek van BAG aan Geo tot het inwinnen en/of karteren en/of intekenen van geometrie voor bepaalde BAG-objecten. Dit verzoek ontstaat n.a.v. een BAG-gebeurtenis; de gebeurteniscode is verplicht in het bericht. De BAG-identificatie en de bij BAG-aanwezige (schets)geometrie van een object wordt meegestuurd in het verzoek. <br/> De BAG-identificatie van een betreffend object mag alleen leeg zijn als het bericht wordt verstuurd na gebeurtenis ‘BGR-OBA Ontvangst bouwaanvraag’. 
| Zender | BAG |
| Ontvanger | Geo |
| Stuurgegevens | standaard StUF-stuurgegevens |
| Parameters | <ul><li>idVerzoek [1-1]</li><li>gebeurtenisCode [1-1]</li><li>documentVerwijzing [0-1]</li><li>toelichting [0-1]</li></ul> |
| Inhoud | Keuze uit één of meer entiteiten (choice [1..n]):<ul><li>ligplaats [1-1]</li><li>overigGebouwdObject [1-1]</li><li>overigTerrein [1-1]</li><li>pand [1-1]</li><li>standplaats [1-1]</li><li>verblijfsobject [1-1]</li><li>woonplaats [1-1]</li></ul> |

### GeometrieLevering 
| Naam bericht  | geometrieLevering | 
|---------------|-------------------| 
| Afkorting bericht | gmlDi01 |
| Herkomst | StUF-Geo BAG |
| Berichtcode | Di01 |
| Omschrijving | Een geometrieLevering bevat levering van de geometrie van één of meer BAG-objecten[^35]. De levering is op verzoek van BAG of op initiatief van Geo na constatering of signalering van mutaties en ontstaat dus n.a.v. een BAG- of Geo-gebeurtenis (zie bijlage 1); de gebeurteniscode is verplicht in het bericht. De BAG-identificatie (indien beschikbaar) en de door Geo ingewonnen en gekarteerde of ingetekende geometrie van het object wordt meegestuurd in de levering. De BAG-identificatie mag alleen leeg zijn na gebeurtenis ‘GEO-COG Constatering nieuw object’ of als een levering wordt gedaan op verzoek na gebeurtenis ‘BGR-OBA Ontvangst bouwaanvraag’. De geometrie van het betreffende object mag alleen leeg zijn na gebeurtenis ‘GEO-AOC Constatering gesloopt object’. |
| Zender | Geo |
| Ontvanger | BAG |
| Stuurgegevens | standaard StUF-stuurgegevens |
| Parameters | <ul><li>idLevering [1-1]</li><li>gerelateerdVerzoek [0-1]</li><li>gebeurtenisCode [1-1]</li><li>documentVerwijzing [0-1]</li><li>toelichting [0-1]</li></ul>|
| Inhoud | Keuze uit één of meer entiteiten (choice [1..n]):<ul><li>ligplaats [1-1]</li><li>overigGebouwdObject [1-1]</li><li>overigTerrein [1-1]</li><li>pand [1-1]</li><li>standplaats [1-1]</li><li>verblijfsobject [1-1]</li><li>woonplaats [1-1]</li></ul> |

[^35] Bij levering op initiatief van Geo, wordt vooralsnog verondersteld dat geconstateerd object een relevant BAG-object is. 

### Goedkeuringsbericht 
| Naam bericht  | goedkeuringsbericht  | 
|---------------|-------------------| 
| Afkorting bericht | bevestigingDu01 |
| Herkomst | StUF-Geo BAG |
| Berichtcode | Du01 |
| Omschrijving | Een goedkeuringsbericht is een functioneel asynchroon responsbericht, welke de succesvolle verwerking van (een deel van de inhoud van) een geometrieLevering, of het succesvol intrekken van een geometrieVerzoek bevestigt. De goedgekeurde objecten worden aan de hand van de identificaties en typering van deze objecten teruggegeven; de afgekeurde objecten worden in een separaat afkeuringsbericht opgenomen. In de parameters van een goedkeuringsbericht wordt de identificatie van het geometrieVerzoek of de geometrieLevering opgenomen, waarop het respons wordt gegeven. |
| Zender | Geo, BAG |
| Ontvanger | BAG, Geo |
| Stuurgegevens | standaard StUF-stuurgegevens |
| Parameters | <ul><li>identificatie [1-1]</li></ul>
| Inhoud |  Keuze uit één of meer entiteiten (choice [1..n]):<ul><li>ligplaats [1-1]</li><li>overigGebouwdObject [1-1]</li><li>overigTerrein [1-1]</li><li>pand [1-1]</li><li>standplaats [1-1]</li><li>verblijfsobject [1-1]</li><li>woonplaats [1-1]</li></ul> |

### Afkeuringsbericht 
| Naam bericht | afkeuringsbericht |
|--------------|-------------------| 
| Afkorting bericht | foutDu01 |
| Herkomst | StUF-Geo BAG |
| Berichtcode | Du01 |
| Omschrijving | Een afkeuringsbericht is een functioneel asynchroon responsbericht, welke de niet-succesvolle verwerking van (een deel van de inhoud van) een geometrieVerzoek of geometrieLevering terugmeldt. De afgekeurde objecten worden aan de hand van de identificaties en typering van deze objecten teruggegeven; de goedgekeurde objecten worden in een separaat goedkeuringsbericht opgenomen. Per soort reden van afkeuring (fout) wordt een afkeuringsbericht met één of meer identificatie van objecten verstuurd. In het afkeuringsbericht worden de code, omschrijving, plek en details van de fout opgenomen. In de parameters van een afkeuringsbericht wordt de identificatie van het geometrieVerzoek of de geometrieLevering opgenomen, waarop het respons wordt gegeven. |
| Zender | Geo, BAG |
| Ontvanger | BAG, Geo |
| Stuurgegevens | standaard StUF-stuurgegevens |
| Parameters | <ul><li>identificatie [1-1]</li><li>foutcode [1-1]</li><li>foutomschrijving [0-1]</li><li>plek [1-1]</li><li>details [0-1]</li></ul> |
| Inhoud |  Keuze uit één of meer entiteiten (choice [1..n]):<ul><li>ligplaats [1-1]</li><li>overigGebouwdObject [1-1]</li><li>overigTerrein [1-1]</li><li>pand [1-1]</li><li>standplaats [1-1]</li><li>verblijfsobject [1-1]</li><li>woonplaats [1-1]</li></ul> |

Naast de standaard StUF-foutcodes worden voor dit sectormodel de volgende foutcodes onderkend: 

| Foutsituatie (<StUF:omschrijving>) | Foutcode (<StUF:code>) | Plek  (<StUF:plek>) | Details[^36] (<StUF:details>) |
|------------------------------------|------------------------|---------------------|-------------------------------|
| geometrieLevering is afgekeurd | GB010 | Client | «vrij tekst» |
| geometrieLevering is afgekeurd; BAG-identificatie bestaat niet | GB011 | Client | «vrij tekst» |
| geometrieLevering is afgekeurd; SleutelOntvanger niet bekend | GB012 | Client | «vrij tekst» | 
| geometrieLevering is afgekeurd; Object is geen BAG-object | GB013 | Client | «vrij tekst» |
| geometrieLevering kan niet gecorrigeerd/ingetrokken worden, omdat reeds verwerkt is | GB020 | Client | «vrij tekst» |
| geometrieVerzoek is afgekeurd; | GB030 | Client | «vrij tekst» |
| geometrieVerzoek is afgekeurd; SleutelOntvanger niet bekend | GB031 | Client | «vrij tekst» |
| geometrieVerzoek kan niet gecorrigeerd/ingetrokken worden, omdat reeds verwerkt is | GB040 | Client | «vrij tekst» |

[^36] <StUF:details> kunnen door zender worden toegevoegd, bijvoorbeeld met identificaties, of andere fout bevonden gegevens. 

## BAG-kennisgevingen 
De BAG-kennisgevingsberichten uit StUF-BG worden in dit koppelvlak toegepast om mutaties van BAG door te geven aan Geo. Voor nummeraanduidingen en openbare ruimtenamen geeft BAG elke mutatie door, en Geo neemt de gegevens uit deze kennisgevingsberichten over in de eigen applicatie. 

BAG stuurt na elke mutatie een kennisgevingsbericht aan Geo[^37]. In bijlage 1: Gebeurtenissen is een tabel opgenomen met daarin welke mutaties relevante informatie voor de BGT bevatten.

[^37] En ook naar andere afnemers in de organisatie.

[^38] De overige gebeurtenissen van de BAG Processen lijken vooralsnog niet relevant voor het koppelvlak Geo-BAG. BAG 
stuurt een kennisgeving voor een bepaalde gebeurtenis aan Geo; het is aan Geo om te filteren of deze gebeurtenis relevant 
is om de gegevens uit de kennisgeving te verwerken. 
