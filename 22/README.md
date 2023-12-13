# 22. Desember
Nå nærmer det seg med stormskritt! Julen er rett rundt hjørnet og snøen laver ned. Noen steder. Men hvor? Hvor er det tundra som nissefar kan lande trygt på? Heldigvis observerer satellittene oss hele tiden. Deriblant [NSIDC](https://nsidc.org/home) som samler sammen hvor det er snø og is. Satellittdata er nesten alltid distribuert som rasterdata - fks GeoTIFF. Og det blir fort store datamengder - typisk noen gigabyte per "bilde"/raster. Så hvordan få dette ut på webappen din til SleighPadden? Det er to ulike strategier: 1) Ha en middleware som fks GeoServer som klipper opp rasterbildet og leverer mindre og mer håndterbare tiles/bilder til webappen 2) Bruke Cloud Optimized GeoTIFF (COG) som er en ultrasmart måte å strukturere en vanlig GeoTIFF sammen med å utnytte HTTP Range-spørringer. Dette skal du teste nå for nissen. 

```
På URL'en her er 1.21gb stor COG med global snødekning. 
https://adventofgis-data.ams3.digitaloceanspaces.com/SnowClass_GL_01km_30.0arcsec_2021_v01.0.cog.nocomp.tif

Eksempel på visning i Leaflet med GeoRaster-layer
https://geotiff.github.io/georaster-layer-for-leaflet-example/examples/load-cog-via-url-param.html?url=https://adventofgis-data.ams3.digitaloceanspaces.com/SnowClass_GL_01km_30.0arcsec_2021_v01.0.cog.nocomp.tif

Eksempel med flyfoto over et område med mye piper i Kristiansand: Takk til GeoVekst!
https://adventofgis-data.ams3.digitaloceanspaces.com/Agder_og_Telemark_2021_cog_jpeg.tif

og
https://geotiff.github.io/georaster-layer-for-leaflet-example/examples/load-cog-via-url-param.html?url=https://adventofgis-data.ams3.digitaloceanspaces.com/Agder_og_Telemark_2021_cog_jpeg.tif

```

Nyttige linker:
* https://www.cogeo.org/in-depth.html
* https://github.com/GeoTIFF/georaster-layer-for-leaflet-example
* https://github.com/GeoTIFF/georaster-layer-for-leaflet 
* https://leafletjs.com
* https://daacdata.apps.nsidc.org/pub/DATASETS/nsidc0768_global_seasonal_snow_classification_v01/
* https://geotiff.github.io/georaster-layer-for-leaflet-example/examples/load-cog-via-url-param.html?url=https://adventofgis-data.ams3.digitaloceanspaces.com/SnowClass_GL_01km_30.0arcsec_2021_v01.0.cog.nocomp.tif 

Oppgaven i dag:
---------------
Få inn snøkartet i SleighPadden (Leaflet) så nissen kan finne trygge snødekte steder å lande
1. Bruk georaster-layer-for-leaflet til å laste inn COG-rasteret i Leaflet
1. Lag funksjonalitet for å slå av og på layeret