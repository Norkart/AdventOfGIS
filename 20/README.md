# 20. Desember - PMTiles og Maplibre

SleighPadden begynner å bli riktig så fresh! Rudolf er fornøyd og klar til avspark. Men der kom 3D-ønskene inn 🌍 Plutselig har Julenissen sett en demo av et snasent 3D-kart på web. Han vil ha det! Nå! Vi må lage en MVP! Eller en POC!

Alle har alltid lyst på et kart som er i 3D, eller "tilted 2D". Det har en kulhet over seg, ser avansert ut - [men gir ofte veldig liten direkte nytteverdi sammenlignet med helt vanlig 2D-kart](https://thematicmapping.org/downloads/Using_KML_for_Thematic_Mapping.pdf). Men det finnes gode verktøy for å teste litt - og det skal du gjøre for å stagge nissens sug etter 3D-kart! 

[PMTiles](https://docs.protomaps.com/pmtiles/) er kanonkul filstandard for vector tiles (MVT) levert direkte fra fil til frontend - såkalt Cloud Native. Dette skjer ved at filen er strukturert for å hentes med HTTP Range Request. Altså kan kartet (websiden) hente __deler__ av filen __uten__ å laste hele filen. Med smart geografisk indeksering funker dette __serverless__ og lynraskt. Hele verden kan faktisk være i PMTiles og effektivt leveres direkte til frontend-kartklienter: fks slik: https://protomaps.com/

MapLibre er et kartbibliotek i Javascript - litt som Leaflet - men litt mer avansert - og lagd for vector-tiles og rendring i browseren. Litt som Mapbox - men Open Source 🥳

Nyttige linker:
* https://maplibre.org/maplibre-gl-js-docs/example/add-3d-model/
* https://bertt.wordpress.com/2023/01/06/creating-vector-pmtiles-with-tippecanoe/
* https://gdal.org/drivers/vector/pmtiles.html

```
PMTiles-fil med all samferdsel direkte fra N50-datasettet i Norge (lagd fra >1M objekter - 1.5gb geojson)
https://adventofgis-data.ams3.digitaloceanspaces.com/n50_samferdsel_senterlinje_zg-option.pmtiles

```

Du kan lage din egen ved å bruke Tippecanoe eller ogr2ogr. Noen eksempler:

```
docker run -it --rm -v c:\dev\datasets:/data tippecanoe:latest tippecanoe -zg --output=/data/n50_samferdsel_senterlinje_3.pmtiles /data/n50_samferdsel_senterlinje.fgb --force --drop-densest-as-needed --extend-zooms-if-still-dropping

ogr2ogr -f PMTiles N50_z14.pmtiles Basisdata_0000_Norge_25833_N50Kartdata_FGDB\Basisdata_0000_Norge_25833_N50Kartdata_FGDB.gdb -progress
```

Visning av datasettet: [https://protomaps.github.io/PMTiles](https://protomaps.github.io/PMTiles/?url=https%3A%2F%2Fadventofgis-data.ams3.digitaloceanspaces.com%2Fn50_samferdsel_senterlinje_zg-option.pmtiles#map=11.11/58.1648/7.9708)

Oppgaven i dag:
---------------
Lag noen kule visualiseringer / demoer på analysene i tidligere luker ved å bruke PMTiles og MapLibre. Hent inspirasjon fra ChatGPT, Google eller bare på [maplibre_pmtiles.html](./maplibre_pmtiles.html)
1. Last inn dine egne PMTiles - eller bruk datasettet over
1. Sleng på terrain-tiles som background og endre på pitchen til cirka 42+42 (Du kan laste ned 142gb eller få deg en gratis nøkkel på [raster-dem hos Maptiler](https://cloud.maptiler.com/tiles/terrain-rgb-v2/))