# 9. Desember
Julenissen har fått blod på tann og glitrer i skjegget. Kartet på SleighPaden er skikkelig nyttig. Men kan det pimpes litt? Han har hørt om vector-tiles - det skal være rimelig sexy greier <3 Kanskje kartet kan roteres og tippes? Dette MÅ testes ut! Blås i kostnader, blås i oppgradering av SleighPaden - kjør MVT MVP!

Vector tiles er små data-fliser som er optimalisert for å rendres innenfor et gitt zoomnivå/utstrekning. Til forskjell fra raster-tiles/tilecacher, så må vector tiles rendres client-side. Altså må klienten vite om all styling/kartografi. Dette kan gi mer "smooth" opplevelse og mer dynamikk i kartografien. I tillegg så får klienten de faktiske vectordataene tilgjengelig som gjør det enklere med interaksjon på kartobjekter.

Nyttige linker:
* [Vector vs raster tiles - MapTiler](https://documentation.maptiler.com/hc/en-us/articles/4411234458385-Raster-vs-Vector-Map-Tiles-What-Is-the-Difference-Between-the-Two-Data-Types)

Oppgaven i dag:
---------------
Nissen vil pimpe SleighPad-kartet med Vector Tiles og du er sjefspimperen!
1. Lag et webkart (Leaflet, MapLibre, Mapbox, OpenLayers) som bruker vector tiles fra en freemium-tjeneste (Mapbox, Maptiler e.l.)



Tips til software:
* https://docs.maptiler.com/leaflet/vector-tiles-in-leaflet-js/
* https://docs.mapbox.com/mapbox-gl-js/guides/install/#quickstart
