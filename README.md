# Trip Planner

A single-page web app that works out what a drive costs in fuel, and compares that cost across your cars.

- Search for places and addresses, or tap saved ones like Home and Work
- Real road distance, drive time and a route map
- Fuel price per fuel type, so a 98-only car is compared fairly with a 91 car
- Everything you enter stays in your browser, with an export/import backup

## Put it online with GitHub Pages

1. Create a new repository on GitHub, for example `trip-planner`.
2. Upload `index.html`, `manifest.webmanifest`, `icon-180.png`, `icon-192.png` and `icon-512.png` to the root of the repository.
3. Go to **Settings**, then **Pages**. Under **Build and deployment**, set **Source** to *Deploy from a branch*, choose branch `main` and folder `/ (root)`, then **Save**.
4. After a minute the site is live at `https://<your-username>.github.io/trip-planner/`. Share that link with anyone.

It's a static page, so it also works from any other host, or opened straight off your computer as a file.

## Add it to an iPhone Home Screen

Open the link in Safari, tap **Share**, then **Add to Home Screen**. It opens full screen with its own icon. On Android, use Chrome's **Install app** option.

Each person's cars, places and prices live in their own browser, so your data and your wife's stay separate.

## Services it uses

No API keys or accounts are needed. The page calls two free OpenStreetMap-based services from the browser:

| What | Service | Notes |
|---|---|---|
| Place and address search | [Photon](https://photon.komoot.io) by Komoot | Demo server, fine for personal use |
| Road distance, time and route | [OSRM](https://router.project-osrm.org) demo server (FOSSGIS) | Non-commercial use, keep under 1 request per second |
| Map tiles | CARTO dark basemap on OpenStreetMap data | Attribution shown on the map |

These are free public servers offered on a best-effort basis, so they can be slow or briefly unavailable, and their terms allow reasonable personal use only. Distances come from OpenStreetMap road data and usually land within a percent or so of Google Maps. Times are free-flow, with no live traffic.

If you ever outgrow the free servers, both can be swapped for a paid provider by changing the `PHOTON` and `OSRM` constants near the top of the script in `index.html`.

## Fixing a distance

If a distance doesn't look right, type the correct one into the distance box. It's saved against that pair of places, in both directions, and used automatically next time.
