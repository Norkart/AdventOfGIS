# 14. Desember
Flere bekymringer! Hvorfor kan ikke luftfarten være fri for hinder?? Julenissen har lite lyst til å krasje på selveste julaften. Og sant og si så kan det bli litt tåkete med mye gløgg i sleden. SleighPaden trenger luftfartshinder i seg for å unngå krasj - og for å droppe gaver til de barna som tenkte at de skulle lure selveste julenissen til å komme på besøk nærme et luftfartshinder. Nix! Denne nissen vet bedre!  

Nyttige linker:
* https://postgis.net/workshops/postgis-intro/introduction.html
* https://www.kartverket.no/geodataarbeid/nrl

Oppgaven i dag:
---------------
Julenissen følger selvfølgelig alle [ISO/TC20-standardene](https://www.iso.org/committee/46484/x/catalogue/) og trenger trygg reisevei og få vekk tullete gavesteder med høy risiko! 
1. Last inn [luftfartshinder.geojson](./luftfartshinder.geojson) i databasen din
1. Finn alle [gaver_urban_areas](../11/gaver_urban_areas.geojson) som er innenfor 3141.5 meter av alle luftfartshinder (hint: `st_buffer, st_dwithin, st_transform, 32633`)
1. Lag et nytt VIEW som ikke inkluderer gaver_urban_areas som er høyrisiko for nissen.

**Legg inn svar som comments her**: https://gist.github.com/alexanno/4931f3e24de156518d013816f00c4bef

Tips til software:
* Gavedatasett [gaver_urban_areas.geojson](../11/gaver_urban_areas.geojson)
* https://www.crunchydata.com/developers/tutorials
* https://postgis.net/workshops/postgis-intro/
* https://postgis.net/docs/manual-3.3/
* https://postgis.net/docs/manual-3.3/reference.html