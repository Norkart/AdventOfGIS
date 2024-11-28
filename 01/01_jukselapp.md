### 1. Nordpolen i Leaflet
Du finner ikke Nordpolen på vanlige webkart. Det er fordi de bruker Web Mercator (EPSG:3857) som ikke har dekning så langt nord (og sør). 

### 2. Polarstereografisk
Det finnes spesielle projeksjoner som egner seg godt for nordpolen/nordområdene. Disse heter gjerne polarstereografiske projeksjoner. Du kan endre på projeksjonen i programvare som QGIS. Prøv fks projeksjonen: EPSG:5939. Se linken under for guide til hvordan jobbe med projeksjoner i QGIS. 

https://docs.qgis.org/2.18/en/docs/user_manual/working_with_projections/working_with_projections.html