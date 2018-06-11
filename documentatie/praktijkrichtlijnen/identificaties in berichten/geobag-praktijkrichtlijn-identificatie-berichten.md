Aanleiding
==========

In het Geo-BAG berichtenverkeer wordt onderscheid gemaakt tussen functionele (of
logische) identificaties en logistieke identificaties in berichten.

Een **functionele identificatie** is een identificerend kenmerk dat hoort bij
meerdere berichten behorende bij één mutatie/transactie bundelt. De functionele
identificatie wordt opgenomen:

in \<bg:idLevering\<bg:identificatie\> van de \<bg:parameters\>.

**Logistieke identificatie** is de unieke identificatie van een bericht. De
logistieke identificatie wordt opgenomen in het \<StUF:referentienummer\> in de
\<StUF:stuurgegevens\>.

De gerelateerde identificatie kan worden opgenomen in

Bijvoorbeeld, bij het verlenen van een bouwvergunning door BAG zijn er meerdere
berichten voor het opvoeren van een pand en verblijfsobject. Of na
mutatiesignalering door Geo worden meerdere berichten met constateringen van
panden verstuurd. Deze berichten hebben een eigen unieke logistieke
identificatie, maar worden gebundeld door eenzelfde functionele identificatie.

Deze praktijkrichtlijn geeft extra toelichting op het invullen van functionele
identificaties en logistieke identificaties in Geo-BAG berichten voor bepaalde
scenario’s.

Scenario’s
==========

Intrekken van een levering
--------------------------

Eerst wordt een levering gestuurd als reactie op een geometrieverzoek. De
geometrielevering heeft de volgende identificaties:

| **Identificaties** | **XML-element**         | **Waarde** |
|--------------------|-------------------------|------------|
| Logistiek          | StUF:referentienummer   | 186        |
| Functioneel        | BG:idLevering           | 186        |
|                    | BG:idGerelateerdVerzoek | verzoek123 |

Vervolgens wordt deze levering ingetrokken, voor dat een goed- of afkeuring op
de eerdere levering is ontvangen. Hiervoor wordt een geometrielevering met
gebeurtenis ‘Geo-NEG’ verzonden met de volgende identificaties:

| **Identificaties** | **XML-element**       | **Waarde** |
|--------------------|-----------------------|------------|
| Logistiek          | StUF:referentienummer | 187        |
| Functioneel        | BG:idLevering         | 186        |

### Situatie A. Goedkeuring op levering, afkeuring op intrekking.

BAG keurt de levering goed, en keurt de intrekking van de geometrielevering af.

| **Identificaties** | **XML-element**       | **Waarde** |
|--------------------|-----------------------|------------|
| Logistiek          | StUF:referentienummer | 187        |
|                    | StUF:crossRefnummer   |            |
| Functioneel        | BG:idLevering         | 186        |
| **Identificaties** | **XML-element**       | **Waarde** |
| Logistiek          | StUF:referentienummer | 187        |
| Functioneel        | BG:idLevering         | 186        |

Goedkeuring op geometrieverzoek

\<StUF:referentienummer\>                         10643

\<StUF:crossRefnummer\>                            186

\<BG:identificatie\>                                        186

### Situatie B. Goedkeuring op intrekking, afkeuring op levering.

Op levering

En daarop is een goedkeuring ontvangen.

\<StUF:referentienummer\>                         10643

\<StUF:crossRefnummer\>                            186

\<BG:identificatie\>                                        186

**Respons op de intrekking (is dan een fout, omdat levering al goedgekeurd) op
intrekking zou moeten hebben:**

**\<StUF:referentienummer\>                         10644**

**\<StUF:crossRefnummer\>                            187**

**\<BG:identificatie\>                                        186**

Het is nu onduidelijk of deze goedkeuring de levering of de intrekking betreft.
Het crossrefnummer lijkt op de levering te duiden (de identificatie is in dit
scenario onbruikbaar?).  
  
Hoe zou dit scenario moeten verlopen?
