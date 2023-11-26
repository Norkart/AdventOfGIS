# 13. Desember
Det er [Luciadagen](https://no.wikipedia.org/wiki/Luciadagen) og Julenissen blir umiddelbart bekymret! Er det fare for skogbranner i desember? Må han ta med seg røykdykker-utstyr til Rudolf og resten av gjengen? Hvor brenner det egentlig i desember? 

Heldigvis er nissen heldig! Satellittene til NASA og ESA svirrer rundt jorden og [noen av de](https://firms.modaps.eosdis.nasa.gov/) klarer å detektere skogbranner og brannlignende hendelser på bakken. Dagens oppgave har et lite uttrekk av brannhendelser over 7 dager [J1_VIIRS_C2_Global_7d.zip](./J1_VIIRS_C2_Global_7d.zip) som er en zippet shapefile. I tillegg er alle land med i [countries.geojson](./countries.geojson).

Nyttige linker:
* https://postgis.net/workshops/postgis-intro/introduction.html


Oppgaven i dag:
---------------
Hjelp nissen med å dempe bekymringene rundt brannrisiko på sin ferd! Lag SQL-spørringer som finner svarene på:
1. Last inn brannhendelser fra [J1_VIIRS_C2_Global_7d.zip](./J1_VIIRS_C2_Global_7d.zip) i PostGIS-databasen din
1. Hvilken dag var det flest brannhendelser?
1. Hvor langt Nord brant det?
1. Hvilket land har flest brannhendelser over hele perioden?
1. Hvor var det færrest branner?
1. Hvilke land har færre branner enn gjennomsnittet globalt?
1. (ekstraoppgave) prøv ut cluster-funksjoner og lag clustere av branner. Lag polygoner av clusterne du får. (https://postgis.net/docs/ST_ClusterDBSCAN.html)



Tips til software:
* https://www.crunchydata.com/developers/tutorials
* https://postgis.net/workshops/postgis-intro/
* https://postgis.net/docs/manual-3.3/
* https://postgis.net/docs/manual-3.3/reference.html