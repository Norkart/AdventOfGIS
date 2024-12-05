Her er eksempler på hvordan du kan implementere oppgavene i SQL ved hjelp av PostGIS for å hjelpe nissen med KNN-søk for gavesteder:

### 1. Finn 100 nærmeste gavesteder gitt en tilfeldig koordinat

Anta at vi har en tabell `gavesteder` med følgende struktur:
- `id`: unikt ID for gavestedet
- `geom`: geometrien (Point) for gavestedet

Vi vil bruke en tilfeldig koordinat som referanse, for eksempel `POINT(10 60)`.

#### 1.1 Bruk `WHERE ST_Distance`
```sql
WITH referansepunkt AS (
    SELECT ST_GeomFromText('POINT(10 60)', 4326) AS geom
)
SELECT 
    g.id,
    ST_Distance(r.geom, g.geom) AS distance
FROM 
    referansepunkt r, gavesteder g
ORDER BY 
    r.geom <-> g.geom
LIMIT 100;
```

#### 1.2 Bruk `ST_DWithin`
```sql
WITH referansepunkt AS (
    SELECT ST_GeomFromText('POINT(10 60)', 4326) AS geom
)
SELECT 
    g.id,
    ST_Distance(r.geom, g.geom) AS distance
FROM 
    referansepunkt r, gavesteder g
WHERE 
    ST_DWithin(r.geom, g.geom, 10000) -- Velg en radius som omtrentlig dekker de 100 nærmeste
ORDER BY 
    r.geom <-> g.geom
LIMIT 100;
```

#### 1.3 Bruk `<->` direkte i `ORDER BY`
```sql
WITH referansepunkt AS (
    SELECT ST_GeomFromText('POINT(10 60)', 4326) AS geom
)
SELECT 
    g.id,
    ST_Distance(r.geom, g.geom) AS distance
FROM 
    referansepunkt r, gavesteder g
ORDER BY 
    r.geom <-> g.geom
LIMIT 100;
```

---

### 2. Sjekk `EXPLAIN ANALYZE`

Kjør `EXPLAIN ANALYZE` for å sammenligne ytelsen mellom de ulike tilnærmingene:

```sql
EXPLAIN ANALYZE
WITH referansepunkt AS (
    SELECT ST_GeomFromText('POINT(10 60)', 4326) AS geom
)
SELECT 
    g.id,
    ST_Distance(r.geom, g.geom) AS distance
FROM 
    referansepunkt r, gavesteder g
ORDER BY 
    r.geom <-> g.geom
LIMIT 100;
```

---

### Ytelsestips

1. **Opprett en GIST-indeks** på `geom`-kolonnen i `gavesteder`:
   ```sql
   CREATE INDEX gavesteder_geom_idx ON gavesteder USING GIST (geom);
   ```

2. Sørg for at alle geografiske data bruker samme SRID. Hvis de ikke gjør det, konverter geometriene ved hjelp av `ST_Transform`.

3. Bruk `<->`-operatøren for å dra nytte av GIST-indeksen, som er optimalisert for KNN-spørringer.

---

### Eksempelresultat

La oss si vi tester med `EXPLAIN ANALYZE`. Du kan få en utdata som viser planlagt kostnad og kjøretid:

```plaintext
Limit  (cost=0.29..12.35 rows=100 width=48) (actual time=0.023..0.100 rows=100 loops=1)
  ->  Index Scan using gavesteder_geom_idx on gavesteder g  (cost=0.29..12435.87 rows=100 width=48) (actual time=0.023..0.097 rows=100 loops=1)
        Order By: (geom <-> st_geomfromtext('POINT(10 60)'::text, 4326))
Planning Time: 0.135 ms
Execution Time: 0.125 ms
```

Dette viser hvor raskt PostGIS håndterer KNN-operasjoner! 🚀