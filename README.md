# Browser technologies
<!--
- Schrijf een Readme met:
  - een beschrijving van alle features die je hebt getest
  - een beschrijving van de Device lab test en screenreader test.
  - beschrijf hoe je de problemen hebt opgelost, of hoe je dit zou oplossen (met todo’s) als je genoeg tijd en budget zou hebben
  -->

## Inhoud
* [Testen](#testen)
  * [Geen afbeeldingen](#geen-afbeeldingen)
  * [Geen custom fonts](#geen-custom-fonts)
  * [Geen kleur/kleurenblind](#geen-kleur/kleurenblind)
  * [Geen muis/trackpad](#geen-muis/trackpad)
  * [Langzaam internet](#langzaam-internet)
  * [Geen JS](#geen-js)
  * [Geen cookies](#geen-cookies)
  * [Geen localStorage](#geen-localstorage)

## Testen
Hier de resultaten van het testen van mijn OBA app.

### Geen afbeeldingen
Alle afbeeldingen gingen stuk (duh). Ik had nog geen alt-attributten toegevoegd. Dat heb ik inmiddels wel gedaan. Om dit verder te verbeteren zou ik het logo (een svg) in de html kunnen zetten.  
Helaas ging ook de kaart op de detailpagina stuk. Dit komt doordat [leaflet](https://leafletjs.com/) afbeeldingen gebruikt om de kaart op te bouwen. Hierdoor werkt de kaart niet zonder afbeeldingen.

### Geen custom fonts
Ik gebruik als font `Avenir`. Deze staat standaard op een Mac. Wanneer je de website op een windows pc zou bekijken valt de CSS terug op `system-ui`, en als dat nog niet ondersteund wordt door de browser wordt `sans-serif` gebruikt.  
Hierdoor gaat er niks stuk als je custom fonts uitschakelt.

### Geen kleur/kleurenblind

### Geen muis/trackpad
Dit is geen probleem. Er kan zonder problemen door de website worden genavigeerd. Alleen het kaartje op de detailpagina

### Langzaam internet
Bij een verbinding van 200kb up en down doet de home pagina er 8.82 seconden over om de DOM content te laden. Het duurt 9.11 seconden voordat de pagina helemaal klaar is. Dit komt vooral doordat [leaflet](https://leafletjs.com/) op de home-pagina wordt geladen. Het JS bestand duurt 6.84 seconden en het CSS bestand 1.8 seconden. Het niet of later laden vermindert de laadtijd dus aanzienelijk. Het later laden van leaflet is dus een goed idee voor mensen met langzaam internet.

### Geen JS
De hele app werkte niet.  
Ik heb de home pagina weer als HTML in [index.html](index.html) gezet zodat de home-pagina in ieder geval wordt getoond als de gebruiker javascript uit heeft staan. Verder werkt de app helaas niet.

### Geen cookies
De app maakt geen gebruik van cookies en werkt dus ook zonder.

### Geen localStorage
De app werkt niet zonder localStorage omdat er data uit opgehaald wordt zonder te controleren of localStorage überhaupt beschikbaar is, waardoor JavaScript errors toont.
