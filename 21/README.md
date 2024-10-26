# 21. Desember - Solposisjon
Wow! Det er skrekkelig mørkt for tida!!??? 🌛 Heldigvis er det [vintersolverv](https://www.timeanddate.no/astronomi/vintersolverv) i dag! Nissen gleder seg over lysere tider. Men hvor står egentlig solen? Soloppgang, soltimer, twilight-moments varierer fra sted til sted og dato til dato. Dette er avanserte greier og nissen trenger hjelp! 

Selvfølgelig finnes det et Javascript-bibliotek som regner ut alt dette! [Suncalc.js](https://github.com/mourner/suncalc) er et slikt bibliotek. Under er eksempler på bruken av dette biblioteket.


```
// get today's sunlight times for London
var times = SunCalc.getTimes(new Date(), 51.5, -0.1);

// format sunrise time from the Date object
var sunriseStr = times.sunrise.getHours() + ':' + times.sunrise.getMinutes();
```

Nyttige linker:
* https://github.com/mourner/suncalc
* https://leafletjs.com/

Oppgaven i dag:
---------------
Nissen vil gjerne vite soloppgang, solnedgang og nadir når han trykker på punkter i kartet
1. Når nissen trykker i kartet på SleighPadden (Leaflet), så regner suncalc ut soloppgang, nedgang, nadir på posisjonen som er trykket på.
1. Utvid med kalkulere posisjonen basert på GPS-posisjonen