# Ishanaa — Vendor Intelligence Dashboard

An interactive vendor scoring dashboard built for Ishanaa's kurta production sourcing. Move the priority sliders and the entire ranking recalculates live — no build step, no dependencies, a single HTML file.

## Features
- **Adjustable weighting** — five sliders (Quality, Reliability, Communication, Price, Speed) that normalize automatically and re-score every vendor in real time
- **Ranked shortlist** with a live bar chart, Hyderabad vendors highlighted since that's the production base
- **Location filter chips** to narrow the view to one sourcing hub
- **Sortable comparison table** with the full vendor detail (MOQ, quote, lead time, payment terms, status, notes)
- **Light/dark mode**, responsive down to mobile, no external JS libraries

## Run it
It's a single self-contained file — no install, no server needed.

```bash
open index.html        # macOS
start index.html        # Windows
xdg-open index.html     # Linux
```

## Host it on GitHub Pages
1. Push this repo to GitHub.
2. Repo → **Settings → Pages** → set source to the `main` branch, root folder.
3. Your dashboard will be live at `https://<username>.github.io/<repo-name>/`.

## Use your own data
Open `index.html` and find the `vendors` array near the bottom of the file (inside the `<script>` tag). Each vendor is a plain object:

```js
{
  name: "Vendor Name",
  location: "City",
  category: "What they supply",
  moq: 200,            // minimum order quantity
  quote: 410,           // price per unit
  lead: 12,              // lead time in days
  terms: "50% advance / 50% on dispatch",
  quality: 5,            // 1–5 ratings, entered after a call or sample
  reliability: 4,
  communication: 4,
  price: 3,
  speed: 4,
  status: "Sampled",    // New | Contacted | Sampled | Approved | Rejected
  notes: "Free text notes."
}
```

Edit, add, or remove entries — the dashboard rebuilds all rankings, KPIs, and the chart from this array on load, so no other file needs to change.

## Tech
Vanilla HTML/CSS/JS. Fonts loaded from Google Fonts (Fraunces + IBM Plex Sans/Mono). No build tools, no npm install.
