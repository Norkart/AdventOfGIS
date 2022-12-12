# 12. Desember
Nå har du på plass analyseriggen din for Julenissen! Klar for litt romlige analyser! Nissen vil, som alle andre, ha en analytisk tilnærming til sin reise i verden. Rudolf blir fort sliten og lei hvis ikke det er lagt en god plan og godt beslutningsgrunnlag for gaveutdelingsrekkefølgen. Dette løser PostGIS-spørringer lett som en lek! 

Nyttige linker:
* https://postgis.net/workshops/postgis-intro/introduction.html


Oppgaven i dag:
---------------
Nissen trenger stats for å planlegge effektivt! Bruk databasen fra tidligere i adventen. Lag SQL-spørringer som finner svarene på:
1. Hvor mange piper er det egentlig i `gaver_urban_areas.geojson`
1. Hvor mange piper (punkt) er det innenfor Frankrike (polygon)? (hint `join where st_intersects group by`)
1. Hva er arealet til Frankrike i kvadratkilometer (hint: `st_area, st_transform`)?
1. Hvilket land har minst areal (hint: `sort by`)?
1. Hvor stor tetthet er av piper pr land og pr urban area?

**Legg inn svar som comments her**: https://gist.github.com/alexanno/e0465c8e03183012f17e40abe58346fd

Tips til software:
* https://www.crunchydata.com/developers/tutorials
* https://postgis.net/workshops/postgis-intro/
* https://postgis.net/docs/manual-3.3/
* https://postgis.net/docs/manual-3.3/reference.html