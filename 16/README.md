# 16. Desember
Hva er de nærmeste gavestedene? Hvor langt unna er de 100 nærmeste droppstedene? Nissen trenger funksjonalitet i SleigPaden som sorterer ut mens han flyr avgårde!

Spatial analyse er kraftig på nærhetsanalyser. Vanlige operasjoner er "buffer-analyser" som legger en geografisk "buffer" rundt geometrien - for eksempel 200 meter - for deretter sjekke hva som er innenfor/utenfor (intersection). I PostGIS er relevante funksjoner innenfor "Spatial Relationships": ST_Dwithin, ST_Intersects, ST_Intersection m.fl. 

Men ofte vet du ikke avstanden du skal søke etter. Du er ute etter de N nærmeste - uavhengig om de er 1 meter eller 1000 kilometer unna. Dette kalles K-nearest neighbour. I PostGIS er det superkult implementert direkte i GIST-indeksen. Dette betyr at du får _millisekund_ respons på "100 nærmeste" i tabeller som har millioner av rader!! Dette er ekstremt kraftig for nær-sanntids-spørringer, som fks en GPS-applikasjon, geografisk spill eller tilsvarende. 

Nyttige linker:
* https://postgis.net/workshops/postgis-intro/knn.html
* https://postgis.net/docs/reference.html

Oppgaven i dag:
---------------
Hjelp nissen å få raskt nærhetssøk med KNN:
1. Finn 100 nærmeste gavesteder gitt en tilfeldig koordinat som du lager med ST_GeomFromText. 
    1. Bruk where st_distance 
    1. Bruk st_dwithin
    1. Bruk order by <-> og limit
1. Sjekk Explain Analyze på de ulike

**Legg inn svar som comments her**: https://gist.github.com/alexanno/dc6e306bef856d3b60eca0a59378c29e