# 2. Desember
Endelig! Julenissen er klar for å planlegge sin døgnturné for å besøke alle snille GIS-utviklere i verden. Programmet er stramt og han må prioritere de mest befolkede stedene først. Derfor trenger han et kart over alle verdens land og de mest befolkede stedene. 

YES! Datasettene er i GeoJSON! Og vi skal lage webkart i Leaflet! WOW SHIT! Noen har køddet det til med GeoJSON-filen med befolkede steder.. Den er i Web Mercator. Krise!!1

---

GeoJSON er en måte å beskrive geografisk data i vanlig JSON, men som følger en standard for geografiske data. GeoJSON er enkelt å utvikle mot siden det er vanlig JSON og har bred støtte og massevis av verktøy i ulike språk. Det er JSON, så du får ikke indekser, binæroptimalisering eller noe annet snacks. 

Som du allerede har lest deg opp på, så skiller vi mellom punkt, linje, flate/polygon i GIS-verden. En "rad/objekt" med geometri omtales som en "feature". Geometrien i en GeoJSON er som regel beskrevet i WGS84/LatLng. Hver feature kan ha attributter/egenskaper knyttet til seg - akkurat som en normal "tabell". 

Nyttige linker:
* https://geojson.org/
* https://geojson.io/
* https://en.wikipedia.org/wiki/GeoJSON


Oppgaven i dag:
---------------
Julenissen skal lage seg et webkart for å ha med i SleighPaden
1. Transformer GeoJSON-filene til WGS84-latlng (hint: QGIS eller ogr2ogr)
1. Lag et webkart i Leaflet som viser alle land-polygoner fra GeoJSON-filen. I tillegg skal kartet vise alle befolkede steder som punkter. 
1. Lag forskjellige farger på punktene basert på befolkningsmengden(nissen liker å skille mellom: rød, grønn, hvit)
1. Legg på labels på punktene som viser befolkningsmengden

Datasett:
* [populated_places.geojson](./populated_places.geojson)
* [countries](./countries.geojson)



Tips til software:
* ogr2ogr som du har i OSGEO4Win Shell (https://gdal.org/programs/ogr2ogr.html)
* QGIS Desktop
* [FME](mailto://sigbjorn.tillerli.herstad@norkart.no)
* https://leafletjs.com/
* https://github.com/proj4js/proj4js
