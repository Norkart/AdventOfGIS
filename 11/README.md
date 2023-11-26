# 11. Desember
Nok kartgreier - det får da være måte på! Nå er det på tide med noe ordentlig datamengder og da kommer selv det mest julepimpede kartet til kort. Nissen har minst 598000 steder å besøke innenfor urbane områder i verden. Som alle andre er han opptatt av tetthetsfordeling på de urbane områdene. Hvilket område har høyest tetthet av gavebesøk - altså antall piper pr kvadratmeter? Ikke snakk om at målestokken skal frem og begynne å telle og måle fra sledehøyde! Her må vi ha databasehjelp!

Romlige (Spatial) databaser er enten fildatabaser eller databasesystemer som håndterer geometri og geografiske spørringer direkte. Flere layers kan lagres som tabeller og features som rader. I tillegg kan selvfølgelig vanlig databasemodellering kombineres slik at spørringer, views, relasjoner bygger dynamiske layers og features. Dette er både praktisk for å ha kontroll og oversikt over mange datasett, men også svært kraftig analyseverktøy. Det finnes en utvidelse til SQL-språket som er ST_SQL som har veldig mye funksjonalitet knyttet til håndtering av geometri direkte i SQL. I tillegg er det egne indekseringsalgoritmer som er spesialisert på geometri som gjør at avanserte geografiske spørringer kan kjøres ekstremt effektivt på store datamengder. Du kan i mange tilfeller lagre både vektor og raster-data direkte i databasene.

Det er mange ulike databaser som har geografisk støtte (spatial) - både i cloud, Open Source og lisensierte. To kraftige og vanlige er:
* GeoPackage - fildatabase
* PostGIS - utvidelse til PostgreSQL

Nyttige linker:
* http://opengeospatial.github.io/e-learning/geopackage/text/introduction.html
* https://docs.qgis.org/3.22/en/docs/training_manual/basic_map/preparation.html#basic-fa-loading-vector-data-from-a-geopackage-database
* https://postgis.net/workshops/postgis-intro/introduction.html


Oppgaven i dag:
---------------
Nissen vil ha oversikt over alle 593900 pipene i en database sammen med de urbane områdene i verden. Du må klargjøre en database til dette! 
1. Start opp en lokal PostGIS-server ved å bruke fks Docker og Kartoza/PostGIS
1. Installer PgAdmin som databaseklient og koble til databaseserveren din. 
1. Test databaseoppkoblingen i QGIS
1. Last inn datasettene i databasen din ved å bruke ditt favorittverktøy (QGIS, ogr2ogr, FME e.l.): `gaver_urban_areas.geojson`, `gaver_land.geojson`, `ne_10m_urban_areas.zip` (shp-fil)
1. Hva er geometrikolonnene til de ulike tabellene?
1. Ta en kikk på de ulike tabellene og kolonnene. Hvordan ser geometrien ut i klartekst? 
1. Test ut kartvisning i PgAdmin på noen spørringer.



Tips til software:
* QGIS Desktop (https://qgis.org/)
* ogr2ogr/GDAL https://gdal.org/drivers/vector/pg.html (installeres med QGIS i 'osgeo4w shell')
* https://www.rancher.com/
* https://www.docker.com/
* https://hub.docker.com/r/kartoza/postgis/
* https://naysan.ca/2022/01/04/import-geojson-to-postgis-command-line/
* https://www.pgadmin.org/