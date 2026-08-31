# Habitat Pulse

Read the pulse of any place on Earth. Habitat Pulse is a single-page web app that takes a place name (or raw coordinates) and computes a live **Habitat Health Score** from three real, public data sources:

- **Air quality** — current US AQI and PM2.5 from [Open-Meteo](https://open-meteo.com)
- **Climate trend** — a linear regression fitted over the last 14 days of daily max temperature, also from Open-Meteo. A steep slope (fast warming/cooling) scores lower than a stable trend.
- **Biodiversity** — distinct species recorded within ~50km over the last 10 years, pulled live from [GBIF](https://www.gbif.org) (Global Biodiversity Information Facility), with a flag for any IUCN-threatened species in the sample.

No API keys, no backend, no build step — it's one static HTML file that calls free, CORS-enabled public APIs directly from the browser.

## Run it

Just open `index.html` in a browser, or serve the folder with any static host (GitHub Pages, Netlify, Vercel).

## Why

Environmental data is out there — free and public — but it's scattered across a dozen different tools and dashboards, and it's abstract. Habitat Pulse pulls three real signals into one honest, explainable number for a place, so anyone (not just scientists) can get a fast read on how a location is doing right now, and see exactly which underlying data drove that read.

## Tech

Vanilla HTML/CSS/JS, Open-Meteo Geocoding/Forecast/Air Quality APIs, GBIF Occurrence API. No frameworks, no dependencies beyond Google Fonts.

## Limitations & what's next

- Biodiversity sampling is capped at 300 GBIF records per lookup for speed — a production version would paginate.
- The climate "trend" is a short 14-day window, not a true multi-decade climate anomaly — a next step is to compare against historical seasonal norms via GBIF's archive API.
- Next: save/compare multiple locations over time, and let conservation orgs embed a live badge for their site.
