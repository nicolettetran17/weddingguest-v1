# weddingguest-v1

A standalone **guest portal** for Aria & Marcus's destination wedding at AVA Resort Cancún. Spinoff of the All-In Weddings bride-side Wedding Portal — re-skinned to AVA's brand language (magenta primary, sunset coral, sandy-cream neutrals, Cormorant + Montserrat typography) and an itinerary-first home that surfaces Allie's recommended weekend upsells (pre-wedding spa morning, sunrise tee time at Riviera Maya Golf, dolphin encounter at Isla Mujeres) inline with the locked-in wedding events.

## What's in here

```
weddingguest-v1/
├── index.html      # the entire guest portal (self-contained, no build step)
├── vercel.json     # cleanUrls + no trailing slash
└── README.md
```

`index.html` is a single static HTML file with embedded CSS and vanilla JS. State persists to `localStorage` so guests can plan a trip across sessions without an account.

## Run locally

```bash
# any static server works
python3 -m http.server 8080
# then open http://localhost:8080
```

Or open `index.html` directly in a browser — it has no external dependencies beyond Google Fonts and a few Unsplash photos.

## Deployment

The repo is configured for Vercel out of the box. Connect on [vercel.com/new](https://vercel.com/new), import this repo, and it deploys as-is — `vercel.json` keeps URLs clean.

## Routes / surfaces

- `/` — Login (or, if a guest is already signed in via `localStorage`, the home timeline)
- **Home** — Hero countdown + the wedding-weekend timeline as the page anchor, with three Allie-recommended upsell cards spliced in chronologically
- **Stay** — Discounted room block at AVA Resort Cancún (5 room types, every room oceanfront per AVA's Oceanfront Promise™, group-code chip, live night recalculation)
- **Spa** — The Spa at AVA wedding rates
- **Excursions** — Off-property tours (Riviera Maya golf, Isla Mujeres catamaran, whale-shark snorkel, Tulum ruins, MUSA underwater museum, ATV + zipline, etc.)
- **Dining** — On-property dinner reservations (Cocina del Mar, Brava Steakhouse, Coral Garden brunch, Atrium Counter late tasting, Sand Bar)
- **Schedule** — Full timeline + logistics

A floating itinerary drawer collects everything and rolls up to a confirm-everything CTA.

## Demo defaults

The login screen pre-fills with `Sofía Vargas` / `sofia@vargas.co` (a bridesmaid from Aria's existing guest list) so the prototype is one click from a fully populated experience.
