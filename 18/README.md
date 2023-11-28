# 18. Desember
## CHANGE!! PMTiles Maplibre

SleighPadden begynner å bli riktig så fresh! Rudolf er fornøyd og klar til avspark. Men der kom 3D-ønskene inn 🌍 Plutselig har Julenissen sett en demo av et snasent 3D-kart på web. Han vil ha det! Nå! Vi må lage en MVP! Eller en POC!

Alle har alltid lyst på et kart som er i 3D, eller "tilted 2D". Det har en kulhet over seg, ser avansert ut - [men gir ofte veldig liten direkte nytteverdi sammenlignet med helt vanlig 2D-kart](https://thematicmapping.org/downloads/Using_KML_for_Thematic_Mapping.pdf). Men det finnes gode verktøy for å teste litt - og det skal du gjøre for å stagge nissens sug etter 3D-kart! 

PMTiles er kanonkul filstandard for vector tiles (MVT) levert direkte fra fil til frontend. Dette skjer ved at filen er strukturert for å hentes med HTTP Range Request. Altså kan kartet (websiden) hente __deler__ av filen __uten__ å laste hele filen. Med smart geografisk indeksering funker dette __serverless__ og lynraskt. 

MapLibre er et kartbibliotek i Javascript - litt som Leaflet - men litt mer avansert - og lagd for vector-tiles og rendring i browseren. Litt som Mapbox - men Open Source 🥳

Nyttige linker:
* https://maplibre.org/maplibre-gl-js-docs/example/add-3d-model/

Oppgaven i dag:
---------------
Lag noen kule visualiseringer / demoer på analysene i tidligere luker ved å bruke PMTiles og MapLibre
1. Last inn XXXXX som PMTiles herfra: YYYYY
1. Sleng på terrain-tiles som background og endre på pitchen til cirka 42+42 (Du kan laste ned 142gb eller få deg en gratis nøkkel på [raster-dem hos Maptiler](https://cloud.maptiler.com/tiles/terrain-rgb-v2/))