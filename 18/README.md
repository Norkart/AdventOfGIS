# 18. Desember
SleighPadden begynner å bli riktig så fresh! Rudolf er fornøyd og klar til avspark. Men der kom 3D-ønskene inn 🌍 Plutselig har Julenissen sett en demo av et snasent 3D-kart på web. Han vil ha det! Nå! Vi må lage en MVP! Eller en POC! 

Alle har alltid lyst på et kart som er i 3D, eller "tilted 2D". Det har en kulhet over seg, ser avansert ut - men gir ofte veldig liten direkte nytteverdi sammenlignet med helt vanlig 2D-kart. Men det finnes gode verktøy for å teste litt - og det skal du gjøre for å stagge nissens sug etter 3D-kart! Kepler.gl er verktøy som både har en enkel "dra og slipp"-klient for testing - og er mulig å programmere mot som en komponent. 

Nyttige linker:
* https://kepler.gl/
* https://cesium.com/platform/cesiumjs/
* https://maplibre.org/maplibre-gl-js-docs/example/add-3d-model/

Oppgaven i dag:
---------------
Lag noen kule visualiseringer / demoer på analysene i tidligere luker ved å bruke Kepler.gl
1. Last inn [gaver_land.geojson](../9/gaver_land.geojson) i Kepler og prøv ut ulike visualiseringer. Får du til noe "3D"?
1. Bruk geojson-data fra ogr2ogr-eksporten din og prøv ut
1. Hvor mange features "tåler" Kepler før ytelsen går ned? Hvor store data kan du laste inn?