Inleiding
=========

De specificaties van het Geo-BAG berichtenverkeer beschrijven de uitwisseling
van berichten tussen één zender en één ontvanger. Bij dit 1:1 berichtenverkeer
is er altijd sprake van één Geo-applicatie en één BAG-applicatie.

In een Geo-BAG bericht wordt in de StUF:stuurgegevens de adressering van zender
en ontvanger opgenomen bestaande uit de volgende elementen:

-   Organisatie: gemeente, samenwerking of andere type publiek of
    privaatrechtelijke vorm die werkzaamheden uitvoert of applicatie
    onderhoud/hoost voor Geo of BAG

-   Applicatie: software voor Geo of BAG bronhouder werkzaamheden

-   Administratie: een dataset binnen een applicatie die specifiek voor een
    bepaalde gemeente is als bronhouder

-   Gebruiker:

In het Geo-BAG berichtenverkeer is afgesproken dat tenminste organisatie,
applicatie en administratie opgenomen dient te worden bij zender en ontvanger in
de StUF:stuurgegevens.

Waarom deze praktijkrichtlijn?
==============================

In de praktijk komen binnen een organisatie configuraties voor waarbij er één of
meer Geo-applicaties berichten uitwisselen met één of meer BAG applicaties. Een
applicatie kan weer uit één of meer administraties bestaan, waarbij elke
administratie een eigen unieke adressering heeft conform StUF. Dit noemen we n:m
berichtenverkeer. Onder andere kunnen de volgende situatie voorkomen:

-   Er is één Geo-applicatie en er zijn meerdere BAG-applicaties (1:m)

-   Er is één Geo-applicatie en er is één BAG applicatie met meerdere
    BAG-administraties van verschillende gemeenten (1:m)

-   Er is één BAG-applicatie en er zijn meerdere GEO-applicaties (n:1)

-   Er is één BAG applicatie en er is één Geo-applicatie met meerdere
    BGT-administraties van verschillende gemeenten (n:1)

-   Meerdere Geo-applicaties en/of administraties wisselen uit met meerdere
    BAG-applicaties en/of administraties (n:m).

Een applicatie kan uit één of meer administraties bestaan, waarbij elke
administratie een eigen unieke adressering heeft conform StUF.

Om een n:m berichtenverkeer werkend te krijgen binnen een organisatie, worden de
volgende aanvullende afspraken in deze praktijkrichtlijn vastgelegd.

Uitgangspunten
==============

De volgende uitgangspunten gelden:

1.  De zendende applicatie is verantwoordelijk voor het verzenden van een
    bericht aan juiste ontvanger.

2.  Er wordt altijd 1 bericht verstuurd naar 1 ontvanger bij
    leveringen/verzoeken en goed-/afkeuringen.

3.  StUF:stuurgegevens moeten een zender en ontvanger uniek adresseren, d.w.z.
    de combinatie van organisatie, applicatie en administratie is uniek voor
    elke zender en ontvanger.

4.  De BAG-gemeentecode is in de regel gelijk aan de BGT-bronhoudercode minus de
    vaste prefix ‘G’ voor gemeentelijke BGT-bronhouders. Dus voor gemeente
    Amersfoort geldt, BAG-gemeentecode = 0307 en BGT-bronhoudercode = G0307.

Stuurgegevens
=============

Voor de unieke adressering van berichten wordt afgesproken dat elke Geo- en
BAG-applicatie in de adressering van de berichten tenminste de combinatie van
\<organisatie\>, \<applicatie\>, en \<administratie\> in de StUF:stuurgegevens
van ontvanger en zender opneemt, en wel als volgt.

-   \<organisatie\> code of naam van de organisatie die de Geo of BAG-applicatie
    beheert.

-   \<applicatie\> Unieke aanduiding van de applicatie

-   \<administratie\> de code of naam van de administratie van de gemeente
    waarbinnen het (geconstateerde) object ligt conform de gemeentegrens van de
    BAG

>   De \<organisatie\> mag/kan gelijk zijn aan \<administratie\>.

De volgende uitgangspunten gelden voor de stuurgegevens van de Geo-applicatie:

-   In het Geo-BAG berichtenverkeer hanteert de Geo-applicatie dezelfde
    stuurgegevens als wordt toegepast in het berichtenverkeer met SVB-BGT.

-   In het BGT berichtenverkeer geldt dat één organisatie één BGT administratie
    heeft; voor het Geo-BAG berichtenverkeer geldt dit ook.

-   Het stuurgegeven \<organisatie\> is gelijk aan de bronhoudercode.

-   Onder een samenwerkingsverband kunnen meerdere organisaties (=bronhouders)
    vallen, echter de naam of code van het samenwerkingsverband wordt niet
    opgenomen in de stuurgegevens.

Scenario’s
==========

Geometrieverzoeken en –leveringen
---------------------------------

Bij 1 Geo en meerdere BAG-applicaties:

-   Bij een verzoek vanuit BAG, vult de BAG-applicatie de stuurgegevens zo
    specifiek in dat Geo altijd 1 bericht terug kan sturen naar de juiste
    ontvanger. Filtering aan de kant van Geo is niet nodig.

-   Bij een levering voor bestaande BAG-objecten is de gemeentecode bekend, en
    kan Geo de juiste ontvangende stuurgegevens ( o.a. administratie) invullen.

-   Bij een levering met geconstateerde objecten vanuit Geo filtert Geo
    (bijvoorbeeld geometrisch op de gemeentegrens om de gemeentecode te bepalen)
    zodanig dat de levering naar de juiste ontvangende organisatie wordt
    gestuurd.

Geo vult de *stuurgegevens* als volgt in: \<organisatie\> is gemeentecode,
\<applicatie\> is naam BAG-applicatie, en \<administratie\> de uitfiltering
verkregen gemeentecode bij meerdere BAG-administraties[^1].

[^1]: immers de exacte BAG-administratie kan Geo niet bepalen

Bij 1 BAG-applicatie en meerdere Geo-applicaties:

-   Als er 1 Geo-applicatie voor een gemeente is, dan filtert BAG op
    gemeentecode om de naam van de BGT-administratie te bepalen. Vervolgens
    krijgt de betreffende Geo-applicatie o.b.v. de gemeentecode het juiste
    bericht (waarbij gemeentecode als code voor de BGT-administratie in
    \<administratie\> wordt ingevuld).

>   De *stuurgegevens* voor de ontvangende Geo-applicatie worden als volgt door
>   BAG bepaald/ingevuld: in \<organisatie\> de organisatie waar de applicatie
>   staat, in \<applicatie\> de naam van de Geo-applicatie, in \<administratie\>
>   de code van de gemeente van de BGT-administratie.

Bij 1 BAG-applicatie en één Geo-applicatie met meerdere BGT-administratie van
verschillende gemeenten:

-   Als er meerdere BGT-applicaties in een gemeente zijn, dan wordt er één
    centrale BGT applicatie aangewezen waarnaar steeds 1 bericht wordt verstuurd
    door BAG.

Responsberichten
----------------

Een respons-bericht wordt altijd verstuurd naar met in de stuurgegevens van de
ontvanger, de stuurgegevens van de zender van het bericht waarop het respons
wordt teruggegeven.
