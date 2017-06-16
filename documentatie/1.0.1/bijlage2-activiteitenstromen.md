# Bijlage 2 Activiteitenstroom koppelvlak Geo-BAG 

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
|   |   | **A)** | **B)** | **C)** | **D)** | **E)** |
| BF1. | BAG stuurt geometrieVerzoek aan GEO | X | X |   |   |   |
| BF2. | Geo start verwerking geometrieVerzoek | X | X |   |   |   |
| BF3. | Geo stuurt geometrieLevering aan BAG | X |   | X | X |   |
| BF4. | BAG beoordeelt geometrieLevering | X |   | X | X |   |
| BF5. | BAG keurt geometrieLevering goed en stuurt bevestiging naar Geo | X |   | X |   |   |
| BF6. | BAG verwerking geometrieLevering in eigen applicatie | X |   | X |   |   |
| BF7. | BAG stuurt actuele stand van object in BAG-kennisgeving naar Geo | X |   | X |   | X |
| BF8. | Geo verwerkt BAG-kennisgeving in eigen applicatie | X |   | X |   | X |
| AF1.1 | Geo negeert geometrieVerzoek |   | X |   |   |   |
| AF2.1 | BAG negeert geometrieLevering |   |   |   | X |   |

Indien een verzoek of levering tijdens een activiteitenstroom niet verwerkbaar[^41] blijkt voor ontvanger volgt een foutscenario.

| **Stap** | **Omschrijving** | **Scenario** |
| --- | --- | --- |
|   |   |
1. A)**/ B)**
 | **C) / D)** |
| BF1. | BAG stuurt geometrieVerzoek aan GEO | X |   |
| BF2. | Geo start verwerking geometrieVerzoek | X |   |
| BF3. | Geo stuurt geometrieLevering aan BAG | X | X |
| BF4. | BAG beoordeelt geometrieLevering | X | X |
| EX1.1 | Geo keurt geometrieVerzoek af en stuurt functioneel foutbericht aan BAG |   |   |
| EX1.2 | BAG keurt geometrieLEvering af en stuurt functioneel foutbericht aan Geo |   | X |

[^41] Dit betreft functioneel niet verwerkbaar dus m.b.t. de inhoud van een bericht na beoordeling.

De activiteitenstromen zijn gevisualiseerd in het activiteitendiagram Geo-BAG koppelvlak. 

![Activiteitenstromen Geo-BAG koppelvlak](afbeeldingen/fig-activiteitenstromen-geo-bag-koppelvlak.png) 
