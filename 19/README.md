# 19. Desember
SleighPaden må få nytte av all den deilige vektordata-julemagien! [Heldigvis har nissens alver](https://github.com/bjornharrtell) kommet opp med noe sinnsykt fett! [FlatGeoBuf](https://flatgeobuf.org/) er vektordata som cloud native dataformat(!!!1). Den kuleste innovasjonen siden gløgg og rødvin 🤔 

Flatgeobuf er ett layer med vektordata som er strukturert i en felles fil. Magien ligger i starten av filen og består av en geografisk index. Da kan frontend-koden bruke HTTP Range Requests for å hente indexen - og spørre direkte på akkurat den delen av filen som inneholder riktig data. Er filen 12gb stor - ikke noe problem. Smart? (nei er feil svar). 

Nyttige linker:
* https://github.com/flatgeobuf/flatgeobuf
* https://flatgeobuf.org/
* https://flatgeobuf.org/examples/leaflet/large.html
* https://colorbrewer2.org/

Oppgaven i dag:
---------------
Hjelp nissen å utnytte FlatGeoBufs direkte på SleighPadden
1. Hent inn XXXX som Flatgeobuf i Leaflet eller MapLibre
1. Hent ut kun det som skal vises i en bbox på SleighPadden
1. Vis datafeltene når nissen klomser (klikker) på objekter
1. Fargelegg basert på datafelt - bruk kartografisk fargeskala fra fks ColorBrewer