Bijlage Mapping BAG 2.0: StUF BG ExtraElementen vs. StUF-Geo BAG
================================================================

Hieronder staat een vertaling (mapping) tussen de BAG 2.0 elementen zoals
uitgewisseld in de ExtraElementen van StUF BG, en in de elementen bij de
entiteittypen in StUF-GeoBAG.

|                     |                                   | StUF BG Extra Elementen BAG 2.0 |                                  |            | StUF-Geo BAG |                |                       |
|---------------------|-----------------------------------|---------------------------------|----------------------------------|------------|--------------|----------------|-----------------------|
| *BAG 2.0 attribuut* | *Entiteittypen*                   | namespace                       | *naam extraElement*              | *Type*     | *namespace*  | *naam element* | *Type*                |
| documentnummer      | AOA, NUM, OPR, PND, TGO, VBO, WPL | bg0310                          | bag18_brondocument_identificatie | AN40       | geobag0101   | brondocument   | AN40                  |
| versie              | AOA, NUM, OPR, PND, TGO, VBO, WPL | bg0310                          | bag18_versienummer               | N          | geobag0101   | versie         | Integer               |
| status              | PND                               | bg0310                          | bag18_statusPand                 | Enumeratie | geobag0101   | status         | StatusPand            |
| status              | VBO                               | bg0310                          | bag18_statusVerblijfsobject      | Enumeratie | geobag0101   | status         | StatusVerblijfsobject |
