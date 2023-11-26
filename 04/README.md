# 4. Desember
Julenissen er klar for mer planlegging. Rudolf maser skrekkelig om matpauser og sleden trenger landingsplasser. Hovedveier bør unngåes. Skog er litt masete å lande i. Men kartet på SleighPaden viser jo ikke noe av dette!! Går det an å laste inn alle kartdata som GeoJSON-vektordata? Det blir jo for mye data!! SleighPaden krasjer. 

Bakgrunnskart er sentralt i et webkart. Veldig ofte bruker man en webtjeneste for å legge til et bakgrunnskart. Vanlige webtjenester er såkalte "tilecacher" på XYZ-standard. Dette er ferdig-rendret småbilder som er delt opp etter et fast mønster og dekker hele projeksjonen. Mest vanlig er projeksjonen Web Mercator. Bildeflisene (Tiles) deles opp pr zoom-nivå og deles i fire for neste zoom-nivå. Dette betyr at det blir milliarder av små bildefiler for å lage et kart på mange zoom-nivå. Et alternativ til statiske bildefiler er vektor-tiles - og da svært ofte på MVT-format/standard. Vektor-tiles er samme prinsippet som bilde-tiles, men det er generalisert vektordata som sendes til webklienten. Dermed er det klienten sitt ansvar å rendre vektor-tilene til faktiske kartbilder. 

Nyttige linker:
* [Vector vs raster tiles - MapTiler](https://documentation.maptiler.com/hc/en-us/articles/4411234458385-Raster-vs-Vector-Map-Tiles-What-Is-the-Difference-Between-the-Two-Data-Types)
* [100-metersbelte - GeoNorge](https://kartkatalog.geonorge.no/metadata/statlige-planretningslinjer-for-differensiert-forvaltning-av-strandsonen-langs-sjoeen-wms/14db463f-50cc-4531-8c00-8d48a9f00643)

Oppgaven i dag:
---------------
Nissen trenger et bakgrunnskart i Leaflet for sin SleighPad
1. Legg til noen åpne XYZ-karttjenester fra "scratch". Fks Stamen sine:
```
https://stamen-tiles.a.ssl.fastly.net/toner/{z}/{x}/{y}.png

https://stamen-tiles.a.ssl.fastly.net/terrain/{z}/{x}/{y}.jpg

https://stamen-tiles.a.ssl.fastly.net/watercolor/{z}/{x}/{y}.jpg
``` 


Tips til software:
* https://leafletjs.com/
* https://codepen.io/alexanno/pen/EzrjEb