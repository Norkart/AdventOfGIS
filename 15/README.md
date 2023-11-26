# 15. Desember
Du merker SleighPaden sliter kraftig med analysespørringene dine. Alt går treigt. Den gamle spinndisken OlfRudV1 har gitt seg på JuleClusteret til Nissen. Nei! Her må vi optimalisere databasen. Datasettene har blitt for massive og spørringene avanserte! Indekser må til!

Indekser i en database, og også for fillagringer, er ekstremt nyttig, selv på mindre datasett. Prøv å sammenligne et litt stort datasett (gaver_urban_areas) i QGIS som GeoJSON, Shapefile og med PostGIS-connection. Ytelsen er ekstremt forskjellig når du zoomer og panorerer. Dette er fordi en GeoJSON i utgangspunktet må leses komplett hver gang du gjør noe (hvis du ikke gjør noen tricks). Til forskjell har en Shapefile mulighet for (enkle) indekser. PostGIS har mulighet for veldig avanserte indekser. Dette gjør at QGIS - eller query planneren til PostgreSQL kan bruke en optimalisert trestruktur _før_ den leser selve dataene. Indekser er altså (som regel) [trestrukturer](https://en.wikipedia.org/wiki/Tree_(data_structure)) eller [hasher](https://en.wikipedia.org/wiki/Hash_table). Indekser ligger som regel i minnet og er raskt tilgjengelig. Datasett lagres som regel på disk og er "tyngre" tilgjengelig. Det "verste" i en spørring er en "sequential scan" - som betyr at databasemotoren går igjennom absolutt hele datasettet i søken etter riktige rader. Indekser unngår dette ved at databasemotoren går direkte på de områdene eller de radene den trenger. 

Med geografiske data og "spatial", så er det mange veldig gode indeksmetoder fordi selve geometrien og "kartet" kan benyttes til å indeksere på det man veldig ofte spør etter. Quad-trees og GeoHash'er er eksempler på dette.

Nyttige linker:
* https://postgis.net/workshops/postgis-intro/indexing.html
* https://postgis.net/docs/using_postgis_dbmanagement.html#build-indexes
* 

Oppgaven i dag:
---------------
Få en mer optimal og raskere database så nissen kan klare seg med unødvendige CAPEX-investeringer på datasenteret sitt
1. Lag GIST-indekser på geometrikolonnen for gaver_urban_areas
1. Lag en GIST-indeks på gaver_urban_areas som er i WGS84-UTM33
1. Prøv operatoren &&, ST_Intersects og ST_Dwithin med og uten indekser
1. Prøv noen av spørringene tidligere i adventskalenderen. Kjør "Explain Analyze" i PgAdmin. Prøv å unngå sequential scans. Hva kan du gjøre?

