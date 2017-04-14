# Hoofdstuk 2 Uitgangspunten 
Dit hoofdstuk beschrijft de uitgangspunten voor uitwisseling van gegevens tussen BAG en Geo via StUF-Geo BAG berichtenverkeer. 

# 2.1 Actoren en verantwoordelijkheden: Geo en BAG 
Het StUF-Geo BAG berichtenverkeer kent twee actoren[^4}: (het registratiesysteem[^5] van) BAG en (het registratiesysteem van) Geo, hierna respectievelijk BAG en Geo. 

BAG is eindverantwoordelijk voor de volledigheid van de BAG-objecten, het op een correcte manier afbakenen van BAG-objecten en de vastlegging en distributie van de juiste BAG-gegevens volgens de hiervoor geldende wettelijke eisen. 

Geo is veelal faciliterend voor de geometrische inwinning en vastlegging van de geometrie van BAG-objecten conform de eisen van de BAG. Voorts is Geo verantwoordelijk voor de afstemming van de BGT met de BAG. 

De beheerder van Geo[^6] kan vanuit BAG gemandateerd zijn voor de vaststelling van de definitieve geometrie van BAG-panden en BAG-verblijfsobjecten. Het brondocument voor de geometrische mutaties voor BAG-objecten kan en mag opgemaakt en ondertekend worden door de beheerder van Geo. 

[^4] In het geval dat BAG zelf de inwinning en vastlegging van de geometrie verzorgt, is een deel van het in dit koppelvlak beschreven berichtenverkeer niet van toepassing. Geo heeft dan voldoende aan de kennisgevingsberichten vanuit BAG voor de bijhouding van de gegevens van BGT objecten. 
[^5] Registratiesysteem wordt hierna “applicatie” genoemd. 
[^6] In praktijk zijn dit de medewerkers van Geo, danwel de ambtenaar die belast is me de uitbesteding van inwinning van de geometrie voor Geo. 

## 2.2 Berichten 
Het berichtenverkeer tussen Geo en BAG maakt gebruik van de volgende typen berichten: 

* StUF-Geo BAG berichten: specifiek voor dit koppelvlak gedefinieerde dienstberichten t.w. 
  * geometrieVerzoek (gmvDi01): een asynchroon inkomend vrij bericht als verzoek tot levering van geometrie[^7] voor een bepaald object. 
  * geometrieLevering (gmlDi01): een asynchroon inkomend vrij bericht met de te leveren geometrie[^7] voor een bepaald object. 
  * goedkeuringsbericht (bevestigingDu01): een asynchroon responsbericht met de goedkeuring van (een deel van de inhoud van) een geometrieVerzoek of geometrieLevering. 
  * afkeuringsbericht (foutDu01): een asynchroon responsbericht met een afkeuring van (een deel van de inhoud van) een geometrieVerzoek of geometrieLevering. 
* StUF-BG / BAG-kennisgevingsberichten 
* Logistieke StUF bevestigings- en foutberichten, o.a. 
  * Bv03[^8]: een bevestigingsbericht als technische synchrone respons op een asynchroon bericht waarbij het bericht op basis van berichtstuurgegevens verwerkbaar wordt geacht[^9] 
  * Fo03: een foutbericht als technische synchrone respons op een asynchroon bericht waarbij het bericht niet verwerkbaar wordt geacht. 

[^7] Naast geometrie worden ook enkele administratieve gegevens uitgewisseld; zie H4 Berichten. 

[^8] Of Bv04: een servicebus stuurt een Bv04 als technisch synchrone respons op een asynchroon bericht 

[^9] Een technische synchrone respons wordt op elk samengesteld of kennisgevingsbericht teruggeven cf. StUF conventies, en 
is dan ook verder niet opgenomen in de uitwerking van het berichtenverkeer. 

De StUF-Geo BAG berichten zijn gespecifieerd in §4.1. 

## 2.3 Uitwisselen van gegevens van BAG-objecten 
In het StUF-Geo BAG berichtenverkeer worden gegevens uitgewisseld van BAG-objecten. 

### 2.3.1 Objecttypen 
De volgende BAG-objecttypen worden ondersteund in het Geo-BAG berichtenverkeer: 
* Pand 
* Verblijfsobject 
* Stand-/ligplaats 
* Woonplaats 
* Nummeraanduiding[^10]
* OpenbareRuimte[^11]

Dit berichtschema’s van van het Geo-BAG koppelvlak zijn daarnaast uitgebreid met de optionele objecttypen OverigGebouwdObject en OverigTerrein voor aansluiting met RSGB. Overig optionele BAG+-objecttypen worden in het Geo-BAG berichtenverkeer niet ondersteund. In de StUF-Geo BAG berichten worden alleen de gegevens opgenomen die noodzakelijk zijn voor een goede verwerking van dit bericht door de ontvanger (zie gegevensmodel in Bijlage 3.). 

[^10] Alleen in BAG-kennisgeving, niet in geometrieVerzoek of geometrieLevering. 

[^11] Alleen in BAG-kennisgeving, niet in geometrieVerzoek of geometrieLevering. 

### 2.3.2 Geometrie 
Voor dit koppelvlak geldt dat de geometrie conform de inwinningsregels ten aanzien van nauwkeurigheid en inwinningswijze van de BAG wordt opgenomen. Een BAG-object kan een vlak- of puntgeometrie hebben. 

De verplichte geometrie voor een Pand in de BAG is een vlakgeometrie in bovenaanzicht. In het kader van de BGT is Geo ook verantwoordelijk voor de geometrische inwinning van grootschalige topografie. Voor de BGT is de keuze gemaakt om van een pand de geometrie op maaiveldniveau op te nemen. Door modernere bouwvormen komt het daarbij steeds vaker voor dat de geometrie van een pand op maaiveldniveau aanzienlijk kan afwijken van de geometrie van een pand op een ander niveau. De geometrie op maaiveld van een Pand kan in de StUF-BG kennisgevingsberichten als optionele geometrie bij dit object worden opgenomen naast de verplichte geometrie van bovenaanzicht. 

* In dit koppelvlak wordt in de StUF-Geo BAG dienstberichten[^12] de geometrie van objecten als volgt opgenomen: objecttype Verblijfsobject wordt uitgewisseld met puntgeometrie, en optioneel met vlakgeometrie. 
* objecttype Pand wordt uitgewisseld met geometrie van het bovenaanzicht, en optioneel met geometrie op het maaiveld. 
* alle overige objecttypen[^13] in §2.3.1. met vlakgeometrie. 

[^12] Dus niet van toepassing voor de StUF-BG kennisgevingsberichten. 

[^13] M.u.v. Nummeraanduiding en OpenbareRuimte, deze objecttypen hebben geen geometrie. 

### 2.3.3 Samengesteld uitwisselen en alleen actuele stand 
In de StUF-Geo BAG berichten worden de gegevens van objecten samengesteld uitgewisseld, d.w.z. een geometrieVerzoek of geometrieLevering bevat de gegevens van één of meerdere BAG-objecten welke tot één bepaalde transactie of gebeurtenis behoren. Bijvoorbeeld, indien een door Geo uitgevoerde mutatiesignalering uit luchtfoto’s mutaties oplevert op meerdere objecten, worden een of meer mutaties van deze objecten in een bericht (geometrieLevering) door Geo aan BAG verstuurd. 

In dit Geo-BAG berichtenverkeer wordt in een StUF-Geo BAG dienstbericht[^14] alleen de actuele stand (WORDT) van een BAG-object uitgewisseld, en niet in combinatie met de vorige stand (WAS) van het BAG-object[^15]. Zowel BAG als Geo hebben de gegevens van een vorige stand van een object niet nodig voor het overnemen van de gegevens uit een bericht. In het bijzonder geval dat op enig moment de gegevens van een bepaald object bij Geo en BAG verschillen (asynchroniteit), zijn de gegevens van de actuele stand in de applicatie van BAG leidend voor dit object. 

[^14] Dus niet van toepassing voor de StUF-BG kennisgevingsberichten. 

[^15] Dit in afwijking van het StUF-BG en StUF-Geo IMGeo berichtenverkeer waar in een bericht WAS én WORDT van een 
object wordt uitgewisseld. 

## 2.4 Gebeurtenissen als aanleiding voor berichtenverkeer 
Het berichtenverkeer tussen BAG en Geo ontstaat naar aanleiding van een bepaalde gebeurtenis aan de kant van BAG of Geo. In Bijlage 1 is een overzicht met alle gebeurtenissen[^16] van Geo en BAG opgenomen en tot welke berichten zij leiden. 

Naar aanleiding van een BAG-gebeurtenis (bijv. verlenen vergunning) stuurt BAG aan Geo een verzoek om geometrie aan te leveren, ofwel een geometrieVerzoek. 

Naar aanleiding van een Geo-gebeurtenis (bijv. constatering[^17] nieuw pand door mutatiesignalering uit luchtfoto’s) of de geometrische inwinning voor BAG na een geometrieVerzoek, stuurt Geo aan BAG een levering van nieuwe of gewijzigde geometrie, ofwel een geometrieLevering[^18] 

Naar aanleiding van een levering van nieuwe of gewijzigde geometrie door Geo, stuurt BAG altijd een functionele respons om de acceptatie en verwerking, of afkeuring van de levering aan Geo te melden, ofwel een responsbericht. 

Naar aanleiding van een doorgevoerde mutatie op een BAG-object , stuurt BAG een kennisgeving van deze wijziging aan Geo, ofwel een BAG-kennisgevingsbericht (= StUF-BG). Geo filtert hieruit de voor de Geo/BGT relevante mutaties (bijv. wijziging van een nummeraanduiding door BAG) en verwerkt deze in de eigen applicatie. 

[^16] Dit overzicht is gebaseerd op de lijst met gebeurtenissen van het formele BAG-processenhandboek en aangevuld met de Geo-gebeurtenissen.  

[^17] Dit is een vorm van terugmelding op de registratie van BAG. 

[^18] Geo krijgt de BAG-identificatie van een geconstateerd nieuw pand retour na overname van BAG via een BAG-kennisgevingsbericht. 

## 2.5 Identificaties van en relaties tussen berichten 
De StUF-Geo BAG berichten hebben een logistieke identificatie en functionele identificatie, resp. het <StUF:referentienummer> in de <StUF:stuurgegevens> en <BG:identificatie> in de entiteittypen <BG:parameters>. 

Indien een geometrieLevering een respons is op een geometrieVerzoek bevat de geometrieLevering een eigen unieke logistieke identificatie en een verwijzing naar de functionele identificatie van het geometrieVerzoek. 

Daarnaast bevat de geometrieLevering in de eigen functionele identificatie <BG:identificatie> de functionele identificatie van het geometrieVerzoek in het element <BG:idGerelateerdVerzoek>. De functionele identificatie geldt als een kenmerk om berichten bij een bepaalde gebeurtenis of transactie te kunnen bundelen[^19]. 

[^19] De functionele identificatie is ook nodig voor het corrigeren en intrekken van eerder verzonden bericht, omdat een geometrieVerzoek en geometrieLevering geen StUF:crossReferencenummer in de stuurgegevens hebben. 

*Tabel 1. Voorbeeld logistieke en functionele identificatie in een geometrieVerzoek.*

| «leeg» | geometrieVerzoek | geometrieLevering | 
|--------|------------------|-------------------|
| StUF:referentienummer | BAG12345678 | GEO23456789 |
| StUF:crossRefnummer | | BAG12345678 | 
| BG:identificatie | GMV09876543 | GMV09876543 |

## 2.6 Corrigeren en intrekken van berichten 
In het StUF-Geo BAG berichtenverkeer kan het voorkomen dat BAG of Geo een eerder verstuurd StUF-Geo BAG bericht wil corrigeren of intrekken. Een bericht kan door zender worden gecorrigeerd of ingetrokken indien deze nog niet door ontvanger is afgehandeld, d.w.z. dat er nog niet door 
* BAG een goed- of afkeuringsbericht als respons op een geometrieLevering, of 
* Geo een geometrieLevering of afkeuringsbericht als respons op een geometrieVerzoek 
is verstuurd. 

Voor het intrekken van een StUF-Geo BAG bericht wordt een nieuw bericht gestuurd met daarin opgenomen een eigen unieke logistieke identificatie en een functionele identificatie gelijk aan de functionele identificatie van het in-te-trekken bericht. Bijvoorbeeld, BAG wil een geometrieVerzoek n.a.v. een BAG-gebeurtenis BAG-*** met een logistieke en functionele identificatie resp. BAG12345678 en GMV09876543 intrekken. BAG stuurt daarop een geometrieVerzoek met gebeurteniscode BAG-NEG met een nieuwe logistieke identificatie en een gelijke functionele identificatie GMV09876543 als het eerder verzonden geometrieVerzoek. 

Voor het corrigeren van een StUF-Geo BAG bericht wordt eerst het vorige bericht ingetrokken en vervolgens een nieuw bericht met een nieuwe functionele identificatie verstuurd. Bijvoorbeeld, na het intrekken van een geometrieVerzoek met functionele identificatie GMV09876543 stuurt BAG een nieuw geometrieVerzoek met functionele identificatie GMV09876544. 

*Tabel 2. Voorbeeld intrekken en corrigeren van een geometrieVerzoek*

|«leeg» | origineel | intrekken | nieuw bericht t.b.v. corrigeren |
|-------|-----------|-----------|---------------------------------|
|StUF:referentienummer | BAG12345678 | BAG12345679 | BAG12345680 |
|BG:identificatie | GMV09876543 | GMV09876543 | GMV09876544 | 
| BG:gebeurtenisCode[^20] | BAG-*** | BAG-NEG | BAG-*** |

[^20] Idem voor geometrieLevering met gebeurtenissen resp. GEO-***, GEO-CEG, en GEO-NEG. 

## 2.7 Identificaties van en relaties tussen objecten 
Een BAG-object in een StUF-Geo BAG bericht heeft functionele en technische identificaties, t.w. 
* BAG-identificatie: de functionele identificatie van een BAG-object zijnde een 16-cijferige code welke wordt toegewezen door de applicatie van BAG nadat het object in de registratie van BAG is opgenomen. Met dit nummer is het object ook bekend in de Landelijke Voorziening BAG zodra het authentiek is verklaard. 
* sleutelVerzendend: de technische systeemsleutel van het BAG-object in de applicatie van de verzender van het bericht (dus BAG of Geo) 
* sleutelOntvangend: de technische systeemsleutel van het BAG-object in de applicatie van de ontvanger van het bericht (dus BAG of Geo). 

Het opnemen van de BAG-identificatie bij een object is verplicht, behalve in de volgende twee situaties: 
* Bij het versturen van een geometrieVerzoek na gebeurtenis ‘BGR-OBA Ontvangst bouwaanvraag’, waarbij het object nog niet is opgenomen in de applicatie van BAG en dus de BAG-identificatie voor dit object nog niet is uitgedeeld. 
* Bij het versturen van een geometrieLevering na gebeurtenis ‘GEO-COG Constatering nieuw object’ (bijvoorbeeld bij vergunningsvrije bouw) waarbij het object ontstaat in de applicatie van Geo. Het object is nog niet opgenomen in de applicatie van BAG en dus is de BAG-identificatie voor dit object nog niet uitgedeeld. 

Het opnemen van de technische systeemsleutels StUF:sleutelVerzendend en StUF:sleutelOntvangend bij een object is verplicht als de BAG-identificatie niet kan worden meegestuurd (zie bovenstaande). De StUF:sleutelOntvangend mag alleen leeggelaten worden als het object is ontstaan in de zendende applicatie en nog niet voorkomt in de applicatie van ontvanger (en dus de technische systeemsleutel van ontvangende applicatie niet bestaat). Na het opnemen van het object in de applicatie van ontvanger stuurt ontvanger de technische systeemsleutel in een responsbericht aan zender: 
* na een geometrieVerzoek van BAG wordt technische systeemsleutel van BAG en Geo in een geometrieLevering teruggegeven aan BAG, 
* na een geometrieLevering van Geo wordt de technische systeemsleutel van Geo samen met de BAG-identificatie in een goedkeuringsbericht teruggegeven aan Geo. 

In zijn algemeenheid geldt dat als de functionele BAG-identificatie bekend is deze wordt meegestuurd in een geometrieVerzoek, geometrieLevering of goedkeuringsbericht. Als de functionele BAG-identificatie niet bekend is, worden de technische sleutels van Geo en/of BAG meegeleverd, voor zover bekend. Dus de uitwisseling van idenfiticaties is als volgt: 

1. Indien wel BAG-identificatie bij BAG bekend, stuurt BAG de BAG-identificatie mee en optioneel de technische systeemsleutel van BAG. 
2. Indien geen BAG-identificatie bij BAG bekend, stuurt BAG de technische systeemsleutel van BAG mee. 
3. Indien BAG identificatie bij Geo bekend, dan stuurt Geo de BAG identificatie mee. 
4. Indien geen BAG-identificatie bij Geo bekend en object is ontstaan bij BAG[^21], stuurt Geo de technische systeemsleutel van BAG en Geo mee. 
5. Indien geen BAG-identificatie bij Geo bekend en een object is ontstaan bij Geo, stuurt Geo alleen de technische systeemsleutel van Geo mee[^22].

Ofwel: Geo stuurt altijd de technische systeemsleutel mee. 

[^21] Deze situatie komt alleen voor als een BAG-object een status ‘vergunning aangevraagd’ heeft, maar nog niet is opgevoerd in de registratie (en dus nog geen BAG-identificatie heeft).

[^22] Deze situatie komt voor indien een object geconstateerd wordt door Geo. 

## 2.8 Verzenden en verwerken van berichten 
In StUF-Geo BAG berichtenverkeer kunnen berichten in willekeurige volgorde worden verzonden en verwerkt. 

### 2.8.1 Transacties en bundeling van berichten 
Bij bepaalde gebeurtenissen (bijv. bij het verlenen van een bouwvergunning voor een pand met meerdere verblijfsobjecten en nummeraanduidingen) komt het voor dat gegevens van meerdere objecten uitgewisseld gaan worden. Per transactie[^23] wordt een StUF-Geo BAG bericht met een eigen logistieke identificatie en een gemeenschappelijke functionele identificatie (betreffende de gebeurtenis ‘bouwvergunning verleend’) voor deze transactie samengesteld en in willekeurige volgorde verstuurd. Het is niet de bedoeling om bijvoorbeeld in één geometrieverzoek voor alle objecten die op die dag zijn opgevoerd in het hele gebied van een gemeente de geometrie te vragen. De eenheid van werk dient zo klein mogelijk gehouden te worden aan de ontvangende kant, om snelle afhandeling van een verzoek of levering mogelijk te maken. 

[^23] Een transactie is een samenstelling / bundeling van (gewijzigde) gegevens van één of meer objecten wat tot een bepaalde gebeurtenis of eenheid van werk toebehoord. 

### 2.8.2 Verplichte of niet-verplichte overname 
De gegevens van een object in het StUF-Geo BAG berichtenverkeer welke worden uitgewisseld met asynchrone kennisgevingsberichten kunnen verplicht zijn om te verwerken in de ontvangende applicatie of informatief bedoeld zijn. Of een BAG-kennisgeving in een bericht verplicht of informatief is, wordt opgenomen in de parameter <StUF:indicatorOvername> met resp. “V” (Verplicht) of “I” (Informatief). 

Voor het Geo-BAG berichtenverkeer heeft een BAG-kennisgeving een indicatorOvername “V” (Verplicht), omdat BAG eindverantwoordelijk is voor de (kwaliteit van) gegevens van de BAG-objecten. Geo neemt de gegevens van BAG verplicht over in de eigen registratie. 

In een StUF-Geo BAG bericht komt het element indicatorOvername niet voor, omdat geen gebruik wordt gemaakt van kennisgevingen24 maar van elementen met een StUF:functie:”entiteit” (hierna: entiteit. De objectgegevens in een geometrieLevering of geometrieVerzoek zijn niet verplicht om over te nemen, en dienen enkel ter identificatie van het object waarvoor geometrie wordt gevraagd of geleverd. 

[^24] Dit omdat alleen de actuele stand van een object wordt uitgewisseld en geen WAS/WORDT structuur.

###2.8.3 Volgorde van verzenden en verwerken 
Het verzenden van een bericht wordt geïnitieerd door zender en is eenrichtingsverkeer (push-mechanisme). De zendende applicatie kan meerdere berichten achter elkaar versturen, waarbij een volgend bericht niet per sé verzonden wordt na bevestiging van ontvangst van het vorige bericht. 

De ontvanger bevestigt te allen tijde de ontvangst van een bericht met een technisch synchrone respons t.b.v. de logistiek (Bv03/Bv04 of Fo03). Als op een bericht binnen een bepaalde termijn geen bevestiging van ontvangst is teruggekomen, mag de zender veronderstellen dat het bericht niet is aangekomen. Omdat het de verantwoordelijkheid van zender is dat berichten ‘aankomen’, dient de zender opnieuw het bericht te versturen aan ontvanger. 

De afhandeling van het bericht door ontvanger is asynchroon, d.w.z. dat het ontvangen bericht op later moment (dus niet gelijk = synchroon) verwerkt wordt. De berichten in de wachtrij van de ontvangende applicatie worden conform StUF verwerkt, ofwel: op volgorde van tijdstipBericht. 

###2.8.4 Synchroniteit 
Op bepaalde momenten kunnen de gegevens van BAG-objecten in de applicaties van BAG en Geo tijdelijk uit elkaar lopen (bijv. na afwijzing van een nieuw geconstateerd Pand in een levering van Geo welke na beoordeling door BAG een niet-relevant BAG-object blijkt te zijn, dus geen BAG-Pand). Geo is verantwoordelijk voor de synchronisatie van de eigen applicatie met BAG voor o.a. overname van gegevens bij het BGT-object Pand. 
