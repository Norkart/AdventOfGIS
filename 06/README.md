# 6. Desember
Julenissen er ikke like rettferdig som du skulle tro. Alt innenfor 100-metersbelte hater han som en innbarket byggesaksbehandler. Dessverre. Derfor trenger han å vite hvor 100-metersbelte i Norge faktisk går. Kystlinjen er jo større enn nissens skjegglengde. Vi trenger WMS!

WMS er en OGC-standard som definerer et slags "Web-API for kart". Standarden er god og gammel. Du spør om et kartutsnitt på ett eller flere layers. Du får tilbake et ferdig rendret bilde som kan vises direkte på toppen av bakgrunnskartet ditt - eller som selve bakgrunnskartet. WMS er veldig fleksibelt og rendrer (ofte) on-the-fly direkte fra kartdata.

Nyttige linker:
* https://en.wikipedia.org/wiki/Web_Map_Service
* https://leafletjs.com/examples/wms/wms.html

Oppgaven i dag:
---------------
Hjelp julenissen med sin 100-meters-fobi. 
1. Legg til 100-metersbelte som WMS-lag på toppen av kartet til SleigMap. Test ut de ulike parameterne på WMS-laget.
1. Finn andre relevante WMS-tema og legg til. Kan du kombinere ulike layers?

Datasett:
```
BaseURL: https://openwms.statkart.no/skwms1/wms.spr_strandsoner?

Layer: spr_strandsoner_wms
```



Tips til software:
* https://codepen.io/alexanno/pen/ZEGWaZp
* https://qgis.org/