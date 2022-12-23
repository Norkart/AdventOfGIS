# 23. Desember
Der er vi! Men brukervennligheten trenger update! Snøen og Tundraen må fremheves! Havet er jo helt uinteressant! Bruk snø-rasteret fra gårsdagen - men gjør litt mer fancy fargelegging!

```
På URL'en her er 1.21gb stor COG med global snødekning. 
https://adventofgis-data.ams3.digitaloceanspaces.com/SnowClass_GL_01km_30.0arcsec_2021_v01.0.cog.nocomp.tif

Klassene til rasteret (pikselverdiene) representerer følgende:
1 = Tundra
2 = Boreal Forest
3 = Maritime
4 = Ephemeral (includes no snow)
5 = Prairie
6 = Montane Forest
7 = Ice (glaciers and ice sheets)
8 = Ocean
9 = Fill
```

Nyttige linker:
* https://github.com/GeoTIFF/georaster-layer-for-leaflet/blob/master/ADVANCED.md
* https://www.cogeo.org/in-depth.html
* https://github.com/GeoTIFF/georaster-layer-for-leaflet-example
* https://github.com/GeoTIFF/georaster-layer-for-leaflet 
* https://leafletjs.com
* https://nsidc.org/data/nsidc-0768/versions/1
* https://daacdata.apps.nsidc.org/pub/DATASETS/nsidc0768_global_seasonal_snow_classification_v01/
* https://geotiff.github.io/georaster-layer-for-leaflet-example/examples/load-cog-via-url-param.html?url=https://adventofgis-data.ams3.digitaloceanspaces.com/SnowClass_GL_01km_30.0arcsec_2021_v01.0.cog.nocomp.tif 
* https://codepen.io/alexanno/pen/VwBYraN 

Oppgaven i dag:
---------------
Få inn snøkartet i SleighPadden (Leaflet) så nissen kan finne trygge snødekte steder å lande
1. Fargelegg "tundra" og "ice" med spesielle julefarger
1. Ta vekk alt "ocean" i visualiseringen