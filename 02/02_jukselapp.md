### QGIS - save as

<video src="qgis_save_as.mp4" width="640" height="320" controls></video>


### ogr2ogr
Du kan bruke kommandolinjeverktøyet ogr2ogr for å transformere. Det er også et kraftig verktøy for å konvertere til ulike formater. https://gdal.org/en/latest/programs/ogr2ogr.html
```sh
ogr2ogr -f "GeoJSON" -t_srs EPSG:4326 transformed_populated_places.geojson populated_places.geojson
```

### Forklaring
- `-f "GeoJSON"`: Angir utdataformatet som GeoJSON.
- `-t_srs EPSG:4326`: Angir det målte romlige referansesystemet som EPSG:4326.
- `transformed_populated_places.geojson`: Navnet på utdatafilen.
- `populated_places.geojson`: Navnet på inndatafilen.
```