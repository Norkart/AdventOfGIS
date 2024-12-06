# 18. Desember - SQL API
Det er lett å bli fanget inn i SQL'ens gleder og frustrasjon! SQL gir glede i seg selv, men lite nytteverdi alene. SleighPaden må få nytte av all den deilige PostGIS-julemagien! Heldigvis har nissens alver rigget opp et [GeoJSON SQL-API på Supabase](https://github.com/alexanno/supabase_geojson_sqlapi) som du kan bruke frem til nyttårsaften for å få GeoJSON som resultater fra en PostGIS-SQL direkte i Leaflet. Databasen er fylt opp med to tabeller:

```
| gaver_urban_areas          	| countries            	|
|----------------------------	|----------------------	|
| id (int)                   	| id (int)             	|
| geom (point, 4326)         	| geom (polygon, 4326) 	|
|                            	| name (varchar)       	|
```

API'et finner du her
```
Syntax: https://sbmvbaxdiylrglcxgfws.supabase.co/functions/v1/geojson-sql-api?q={SQL-SELECT}

Eksempel: https://sbmvbaxdiylrglcxgfws.supabase.co/functions/v1/geojson-sql-api?q=SELECT * FROM gaver_urban_areas LIMIT 1
```

[Eksempelet](https://sbmvbaxdiylrglcxgfws.supabase.co/functions/v1/geojson-sql-api?q=SELECT%20*%20FROM%20gaver_urban_areas%20LIMIT%202) returnerer følgende GeoJSON:
```json
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "geometry": {
        "type": "Point",
        "coordinates": [
          -1.672624564,
          37.367764428
        ]
      },
      "properties": {
        "id": 0
      }
    },
    {
      "type": "Feature",
      "geometry": {
        "type": "Point",
        "coordinates": [
          -1.682911133,
          37.368253346
        ]
      },
      "properties": {
        "id": 1
      }
    }
  ]
}
```


Nyttige linker:
* https://leafletjs.com/reference.html#geojson
* https://rapidapi.com/guides/fetch-api-async-await
* https://postgis.net/workshops/postgis-intro/knn.html
* https://colorbrewer2.org/

Oppgaven i dag:
---------------
Hjelp nissen å utnytte PostGIS direkte på SleighPadden
1. Når nissen klikker på kartet - spør du databasen: "Er det et land som ble klikket på?"
1. Hva er gavetettheten på landet?
1. Fargelegg landet basert på gavetettheten - bruk kartografisk fargeskala fra fks ColorBrewer

<sub>(NB! Alvene blir blinkende i rødt og grønt hvis du prøver deg på noe ufin SQL 😡 Alle julegaver og ønskelister du og din familie kommer med vil umiddelbart brenne opp på veien til Nordpolen hvis du prøver deg!)</sub>