# Entiteiten 
Dit hoofdstuk beschrijft de attributen van de objectkennisgevingen in de StUF-Geo BAG 
berichten. 

## Entiteiten met objectgegevens 
### ligplaats 

| Naam entiteit | ligplaats |
|--------------|-------------------| 
| Definitie entiteit | Entiteit met de attribuutgegevens voor object Ligplaats |
| Herkomst entiteit | BAG |
| Toelichting entiteit | «leeg» |
| Overzicht attributen | <ul><li>identificatie [1-1][^39]</li><li>typering [1-1]</li><li>adresAanduidingGrp [1-1]</li><li>vlakGeometrie [1-1]</li><li>aot.status [1-1]</li><li>aot.geconstateerd [1-1]</li><li>brondocument [1-1]</li><li>StUF:tijdvakGeldigheid [1-1]</li></ul> |

### overigGebouwdObject 
| Naam entiteit | overigGebouwdObject | 
|---------------|---------------------| 
| Definitie entiteit | Entiteit met de attribuutgegevens voor het object overigGebouwdObject |
| Herkomst entiteit | RSGB |
| Toelichting entiteit | «leeg» |
| Overzicht attributen | <ul><li>identificatie [1-1][^39]</li><li>typering [1-1]</li><li>adresAanduidingGrp [1-1]</li><li>gbo.puntGeometrie [1-1]</li><li>vlakgeometrie [0-1]</li><li>aot.status [1-1]</li><li>aot.geconstateerd [1-1]</li><li>brondocument [1-1]</li><li>StUF:tijdvakGeldigheid [1-1]</li></ul> |

### overigTerrein 
| Naam entiteit | overigTerrein | 
|---------------|---------------------| 
| Definitie entiteit | Entiteit met de attribuutgegevens voor het object overigTerrein|
| Herkomst entiteit | RSGB | 
| Toelichting entiteit | «leeg» | 
| Overzicht attributen | <ul><li>identificatie [1-1][^39]</li><li>typering [1-1]</li><li>adresAanduidingGrp [1-1]</li><li>vlakgeometrie [0-1]</li><li>aot.status [1-1]</li><li>aot.geconstateerd [1-1]</li><li>brondocument [1-1]</li><li>StUF:tijdvakGeldigheid [1-1]</li></ul> |

### pand 

| Naam entiteit | pand | 
|---------------|---------------------| 
| Definitie entiteit | Entiteit met de attribuutgegevens voor object Pand |
| Herkomst entiteit | BAG |
| Toelichting entiteit | «leeg» | 
| Overzicht attributen | <ul><li>identificatie [1-1][^39]</li><li>geometrie [1-1]</li><li>status [1-1]</li><li>geconstateerd [1-1]</li><li>brondocument [1-1]</li><li>StUF:tijdvakGeldigheid [1-1]</li></ul> | 

### standplaats 

| Naam entiteit | standplaats |
|--------------|-------------------| 
| Definitie entiteit | Entiteit met de attribuutgegevens voor object Standplaats |
| Herkomst entiteit | BAG |
| Toelichting entiteit | «leeg» |
| Overzicht attributen | <ul><li>identificatie [1-1][^39]</li><li>typering [1-1]</li><li>adresAanduidingGrp [1-1]</li><li>vlakGeometrie [1-1]</li><li>aot.status [1-1]</li><li>aot.geconstateerd [1-1]</li><li>brondocument [1-1]</li><li>StUF:tijdvakGeldigheid [1-1]</li></ul> |

### verblijfsobject 

| Naam entiteit | verblijfsobject |
|--------------|-------------------| 
| Definitie entiteit | Entiteit met de attribuutgegevens voor object Verblijfsobject |
| Herkomst entiteit | BAG |
| Toelichting entiteit | «leeg» |
| Overzicht attributen | <ul><li>identificatie [1-1][^39]</li><li>typering [1-1]</li><li>adresAanduidingGrp [1-1]</li><li>. gbo.puntGeometrie [1-1]</li><li>vlakGeometrie [0-1]</li><li>aot.status [1-1]</li><li>aot.geconstateerd [1-1]</li><li>brondocument [1-1]</li><li>StUF:tijdvakGeldigheid [1-1]</li><li>vbo.maaktDeelUitVan [1..n]</li></ul> |

### woonplaats 

| Naam entiteit | woonplaats |
|--------------|-------------------| 
| Naam entiteit | woonplaats  |
| Definitie entiteit | Entiteit met attribuutgegevens voor object Woonplaats |
| Herkomst entiteit | BAG |
| Toelichting entiteit | «leeg» |
| Overzicht attributen |  <ul><li>identificatie [1-1][^39]</li><li>woonplaatsNaam [1-1]</li><li>geometrie [1-1]</li><li>status [1-1]</li><li>geconstateerd [1-1]</li><li>brondocument [1-1]</li><li>StUF:tijdvakGeldigheid [1-1]</li></ul> |
 
[^39] Een goedkeuringsbericht of afkeuringsbericht bevat in het respons alleen de identificatie van het object in de entiteit 
