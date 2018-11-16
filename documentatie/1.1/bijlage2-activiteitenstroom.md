# Bijlage 2: Activiteitenstroom koppelvlak Geo-BAG 

Hieronder staat een overzicht van de verschillende activiteitenstromen inclusief aanleiding en gebeurteniscode voor het koppelvlak Geo-BAG. 

Aanleiding voor de start van activiteitenstroom kan zijn:

| **Scenario** | **Omschrijving** | **codeGebeurtenis** |
| --- | --- | --- |
| A) | BAG benodigt geometrie voor een bepaald object | BAG-\*\*\* |
| B) | BAG wil eerder verzonden geometrieverzoek intrekken | BAG-NEG |
| C) | Geo heeft nieuwe / gewijzigde geometrie geconstateerd | GEO-\*\*\* |
| D) | Geo wil eerder verzonden geometrieLevering intrekken | GEO-NEG |
| E) | BAG heeft wijziging doorgevoerd op een bepaald object | BAG-\*\*\* |

Een aanleiding leidt tot de volgende activiteiten/stappen in een scenario.

| **Stap** | **Omschrijving** | **Scenario** | 
| --- | --- | --- |
| BF1. | BAG stuurt geometrieVerzoek aan GEO | A,B  |
| BF2. | Geo start verwerking geometrieVerzoek | A,B   |
| BF3. | Geo stuurt geometrieLevering aan BAG | A,C,D |
| BF4. | BAG beoordeelt geometrieLevering | A,C,D |
| BF5. | BAG keurt geometrieLevering goed en stuurt bevestiging naar Geo | A,C|
| BF6. | BAG verwerking geometrieLevering in eigen applicatie | A,C|
| BF7. | BAG stuurt actuele stand van object in BAG-kennisgeving naar Geo | A,C,E |
| BF8. | Geo verwerkt BAG-kennisgeving in eigen applicatie | A,C,E |
| AF1.1 | Geo negeert geometrieVerzoek | B |
| AF2.1 | BAG negeert geometrieLevering | D |

Indien een verzoek of levering tijdens een activiteitenstroom niet verwerkbaar[^41] blijkt voor ontvanger volgt een foutscenario.

| **Stap** | **Omschrijving** | **Scenario** |
| --- | --- | --- |
| BF1. | BAG stuurt geometrieVerzoek aan GEO | A,B  |
| BF2. | Geo start verwerking geometrieVerzoek | A,B   |
| BF3. | Geo stuurt geometrieLevering aan BAG | A,B,C,D |
| BF4. | BAG beoordeelt geometrieLevering | A,B,C,D |
| EX1.1 | Geo keurt geometrieVerzoek af en stuurt functioneel foutbericht aan BAG | |
| EX1.2 | BAG keurt geometrieLEvering af en stuurt functioneel foutbericht aan Geo | C,D|

[^41] Dit betreft functioneel niet verwerkbaar dus m.b.t. de inhoud van een bericht na beoordeling.

De activiteitenstromen zijn gevisualiseerd in het activiteitendiagram Geo-BAG koppelvlak. 

![Activiteitenstroom Geo-BAG koppelvlak](media/fig-activiteitenstroom-geo-bag-koppelvlak.png) 
