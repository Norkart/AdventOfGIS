### 1. **Last inn brannhendelser fra `J1_VIIRS_C2_Global_7d.zip`**
Bruk `shp2pgsql` for å laste inn shapefilen til PostGIS.

```bash
shp2pgsql -s 4326 -I J1_VIIRS_C2_Global_7d.shp firedata | psql -U bruker -d database
```

---

### 2. **Hvilken dag var det flest brannhendelser?**

```sql
SELECT acq_date, COUNT(*) AS antall_branner
FROM firedata
GROUP BY acq_date
ORDER BY antall_branner DESC
LIMIT 1;
```

---

### 3. **Hvor langt nord brant det?**

```sql
SELECT MAX(ST_Y(geom)) AS nordligste_breddegrad
FROM firedata;
```

---

### 4. **Hvilket land har flest brannhendelser over hele perioden?**

```sql
SELECT c.name, COUNT(*) AS antall_branner
FROM firedata f
JOIN countries c
ON ST_Intersects(f.geom, c.geom)
GROUP BY c.name
ORDER BY antall_branner DESC
LIMIT 1;
```

---

### 5. **Hvor var det færrest branner?**

```sql
SELECT c.name, COUNT(*) AS antall_branner
FROM firedata f
JOIN countries c
ON ST_Intersects(f.geom, c.geom)
GROUP BY c.name
ORDER BY antall_branner ASC
LIMIT 1;
```

---

### 6. **Hvilke land har færre branner enn gjennomsnittet globalt?**

```sql
WITH global_avg AS (
    SELECT AVG(branner) AS gjennomsnitt
    FROM (
        SELECT COUNT(*) AS branner
        FROM firedata f
        JOIN countries c
        ON ST_Intersects(f.geom, c.geom)
        GROUP BY c.name
    ) subquery
)
SELECT c.name, COUNT(*) AS antall_branner
FROM firedata f
JOIN countries c
ON ST_Intersects(f.geom, c.geom)
GROUP BY c.name
HAVING COUNT(*) < (SELECT gjennomsnitt FROM global_avg)
ORDER BY antall_branner;
```

---

### 7. **Ekstraoppgave: Lag clustere av branner og lag polygoner av clusterne**

Først, bruk `ST_ClusterDBSCAN` til å gruppere punkter i clustere:

```sql
CREATE TABLE fire_clusters AS
SELECT ST_ClusterDBSCAN(geom, eps := 0.1, minpoints := 5) OVER () AS cluster_id, geom
FROM firedata;
```

Lag deretter polygoner for clusterne:

```sql
CREATE TABLE cluster_polygons AS
SELECT cluster_id, ST_ConvexHull(ST_Collect(geom)) AS cluster_geom
FROM fire_clusters
GROUP BY cluster_id;
```

---