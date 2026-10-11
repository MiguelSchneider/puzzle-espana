# España, pieza a pieza

A drag-and-drop jigsaw for learning the provinces and autonomous communities of Spain. Every piece has the real shape of its territory; drop it close to the right place and it snaps in, locks and shows its name. Built for a secondary-school student practising on an iPad, but it works in any modern browser.

**Play it:** https://YOUR-USER.github.io/puzzle-espana/

## Why a jigsaw

Most map-quiz sites shout a name and ask you to click it. If you have no idea where the place is, you learn nothing. Here the piece tells you its name and its community while you hold it, so the task is "find where this goes", with the shape, the colour and the coastline all helping. Wrong drops are not punished, just nudged.

## Features

- 52 province pieces (50 provinces plus Ceuta and Melilla) or 19 community pieces, from official IGN geometry.
- Pieces are coloured by autonomous community, so building the province map also teaches the communities.
- Feedback by distance: snap when correct, "Casi" with a shake when a little off, "Ahí no" when dropped elsewhere.
- Four hint levels, cycled with one button, from hardest to easiest:
  1. Silhouette of Spain only
  2. Community borders
  3. Community and province borders
  4. Communities tinted with the colours of their pieces
- Ceuta and Melilla get an enlarged grab handle, a wider snap tolerance and a guide ring that lights up when the piece is near its target.
- Timer, miss counter and best time per mode (stored in the browser, nothing leaves the device).
- Touch, mouse and pen. Landscape layout puts the tray on both sides of the map; portrait puts it below.
- Light and dark theme, fullscreen button, and iOS web-app tags so it runs without browser chrome when added to the home screen.

## Running it

It is a single self-contained `index.html`. No build step, no dependencies at runtime.

- **GitHub Pages:** Settings → Pages → Deploy from branch `main`, folder `/ (root)`.
- **Local:** `python3 -m http.server 8000` in this folder, then open `http://localhost:8000/`.
- **iPad full screen:** open the Pages URL in Safari → Share → *Add to Home Screen*. Launching from the icon hides the address bar and tabs. Guided Access (Settings → Accessibility) prevents accidental exits.

The only external request is Google Fonts (Fredoka); offline it falls back to the system font.

## Interface language

The interface is in Spanish, as its audience is Spanish schoolchildren. Province names use the official bilingual forms from the IGN dataset, shown with the first form on the piece (e.g. *Alacant/Alicante* → *Alacant*).

## Data

Geometry comes from [es-atlas](https://github.com/martgnz/es-atlas) (TopoJSON from the Instituto Geográfico Nacional, MIT licence), projected once at build time with `geoConicConformalSpain` from [d3-composite-projections](https://github.com/rveciana/d3-composite-projections), which places the Canary Islands in an inset near the mainland. The projected SVG paths are inlined in the HTML, which is why no map library is loaded in the browser. Gibraltar is excluded.

## Licence

Code: MIT. Map geometry: © Instituto Geográfico Nacional, via es-atlas (MIT).
