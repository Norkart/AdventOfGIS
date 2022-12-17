# 17. Desember
Alle disse analysene! Alle gavene! Rudolf er som alltid utålmodig. Når kommer resultatet til SleighPadden? Hvordan får vi de vakre SQL-resultatene ut i GeoJSON og vist på et webkart? 

Det er mange måter å få transportert data fra PostGIS til webklienter på. Blant annet finnes det mange internasjonale åpne standarder - OGC-standarder. Det er to hovedstrategier å velge mellom: 1) Ferdig visualisert respons (fks WMS, tiles) 2) ren datarespons (OGC-API-Features, WFS, REST-API/GeoJSON)

Du skal teste ut et enkelt verktøy - ogr2ogr - som kan  konvertere SQL til GeoJSON. GeoJSON-filen kan du hente inn i Leaflet med fetch/async. ogr2ogr er et kommandolinjeverktøy - men har også bindings i diverse språk - som Python. 

Eksempel på ogr2ogr i terminalen (fks 'osgeo4w shell' som følger med QGIS). 

_Eksportere en SQL fra en PostGIS til en geojson-fil:_
```
ogr2ogr -f GeoJSON output.geojson PG:"host='yourdbserver.postgres.database.azure.com' user='yourusername' dbname='yourdatabasename' password='yourpassword'" -sql "SELECT * FROM countries LIMIT 35"
```

Nyttige linker:
* https://gdal.org/drivers/vector/pg.html
* https://gdal.org/drivers/vector/pg_advanced.html#vector-pg-advanced
* https://www.bostongis.com/PrinterFriendly.aspx?content_name=ogr_cheatsheet
* https://rapidapi.com/guides/fetch-api-async-await
* https://leafletjs.com/reference.html#geojson

Oppgaven i dag:
---------------
Hjelp Rudolf med utålmodigheten!
1. Eksporter noen SQL-spørringer som GeoJSON. Husk WGS84 som koordinatsystem
1. Hent inn eksporterte filer i Leaflet ved å bruke async/fetch og L.GeoJSON