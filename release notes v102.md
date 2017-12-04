Release notes StUF-Geo BAG versie 1.0.2 (Geo-BAG koppelvlak)
============================================================

De 1.0.2-release is een bug-fix release van de StUF-Geo BAG berichtenstandaard.

De volgende issues zijn opgelost:

- #27 Veldlengte voor foutcode-geoBAG te kort.
- #33 een geometriën toegestaan in GeoBAG1.0.1
- #34 Kennisgevingen van invloed op BGT
- #35 BGR-VOC vervangen door BGR-VOCDEEL en BGR-VOCHEEL

**1-inleiding.md**

URL-verwijzing naar GEMMA referentiecomponenten gerepareerd.

**4-berichten.md**

In paragraaf BAG-kennisgevingen de gebeurtenissen verwijderd met verwijzing naar bijlage 1.

**bijlage1-gebeurtenissen.md**

- BGR-VOC gesplitst in BGR-VOCDEEL en BGR-VOCHEEL (issue #35)
- Toegevoegd concepten/waarden: BAG-IO, BAG-BN, BAG-FGO, BAG-IN, BGR-BIG (issue #34)
- Sortering waarden alfabetisch

**xmlschema/1.0.1-concept/geoBAG0101/geoBAG0101\_bg0310\_ent.xsd**

- ComplexType BG:GeometrieVlak-geoBAG en BG:GeometriePunt-geoBAG verwijderd; verwijzing bij elementen gewijzigd van BG:GeometrieVlak-geoBAG naar BG:GeometrieVlak-e en BG:GeometriePunt-geoBAG naar BG:GeometrieVlak-e (issue #33)

**xmlschema/1.0.1-concept/geoBAG0101/geoBAG0101\_bg0310\_msg.xsd**

- Pattern value bij FoutCode-geoBAG gewijzigd van [a-zA-Z0-9]{7} naar [a-zA-Z0-9]{1,7} (issue #27)

**GeoBAG/waardelijst/1.0.2/codeList\_Gebeurtenis.rdf**

- BGR-VOC gesplitst in BGR-VOCDEEL en BGR-VOCHEEL (issue #35)
- Toegevoegd concepten/waarden: BAG-IO, BAG-BN, BAG-FGO, BAG-IN, BGR-BIG (issue #34)
- Sortering waarden alfabetisch

