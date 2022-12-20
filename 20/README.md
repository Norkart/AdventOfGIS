# 20. Desember
Nissen er over seg av begeistring! For en magi! For en interaksjon med kartet! Det er levende! Nei - vent! GPS'en må jo brukes til noe nyttig!

Vi bruker samme API'et for å lage SQL-spørringer og få tilbake GeoJSON som resultater rett i Leaflet. Men nå må vi kombinere HTML GeoLocation, Leaflet og PostGIS 🚀🎅

```
| gaver_urban_areas          	| countries            	|
|----------------------------	|----------------------	|
| id (int)                   	| id (int)             	|
| wkb_geometry (point, 4326) 	| geom (polygon, 4326) 	|
|                            	| name (varchar)       	|
```

API'et finner du her
```
Syntax: https://alenos-tester-sql-api.azurewebsites.net/api/sqlapi?code={APIKEY}&sql={SQL-SELECT}

Eksempel: https://alenos-tester-sql-api.azurewebsites.net/api/sqlapi?code=mQALCq1cmHPgUiPesWtwQIp82VbuF2KpGRWk0lX1guGTAzFuPevqzg==&sql=SELECT * FROM gaver_urban_areas LIMIT 10

URL Encoded: https://alenos-tester-sql-api.azurewebsites.net/api/sqlapi?code=mQALCq1cmHPgUiPesWtwQIp82VbuF2KpGRWk0lX1guGTAzFuPevqzg==&sql=SELECT%20*%20FROM%20gaver_urban_areas%20LIMIT%2010

Response:
HTTP 200: GeoJSON
HTTP 500: alt annet - ingen feilmelding
```

Nyttige linker:
* https://www.w3schools.com/html/html5_geolocation.asp
* https://leafletjs.com/reference.html#geojson
* https://rapidapi.com/guides/fetch-api-async-await
* https://postgis.net/workshops/postgis-intro/knn.html

Oppgaven i dag:
---------------
1. Hent ut posisjonen til enheten hvert femte sekund. Lag en KNN-spørring som henter ut de 10 nærmeste gavepunktene gitt posisjonskoordinaten.

<sub>(NB! Alvene blir blinkende i rødt og grønt hvis du prøver deg på noe ufin SQL 😡 Alle julegaver og ønskelister du og din familie kommer med vil umiddelbart brenne opp på veien til Nordpolen hvis du prøver deg!)</sub>