# weddingguest-v1

A standalone **guest portal** for Aria & Marcus's destination wedding at Nobu Hotel Los Cabos. Spinoff of the All-In Weddings bride-side Wedding Portal — same design DNA, sage-anchored color palette, and an itinerary-first home that surfaces Allie's recommended weekend upsells (spa day, sunrise tee time, dolphin encounter) inline with the locked-in wedding events.

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
- **Stay** — Discounted room block at Nobu Cabos (5 room types, group-code chip, live night recalculation)
- **Spa** — Esencia Spa wedding rates
- **Excursions** — Off-property tours (golf, Cabo Arch, whale watching, dolphin, ATV, etc.)
- **Dining** — On-property dinner reservations
- **Schedule** — Full timeline + logistics

A floating itinerary drawer collects everything and rolls up to a confirm-everything CTA.

## Demo defaults

The login screen pre-fills with `Sofía Vargas` / `sofia@vargas.co` (a bridesmaid from Aria's existing guest list) so the prototype is one click from a fully populated experience.
