# Life Noodles

A personal timeline PWA for visualising your life's commitments — past, present, and planned.

<img src="icons/icon-512.svg" width="80" alt="Life Noodles icon"/>

## What is it?

Life Noodles lets you map out the meaningful stretches of your life as colour-coded ribbons ("noodles") on a vertical timeline. See your education, career, relationships, hobbies, and health journeys laid out side by side, at a glance.

Your data is stored entirely in your browser — no account, no server, no tracking.

## Features

- **Milestones** — add any life event with a name, category, date range, notes, and sub-events
- **Sub-events** — mark key moments within a milestone; they appear as diamond markers on the ribbon
- **Ongoing & hypothetical** — mark milestones as still active, or as future plans (shown with dashed edges)
- **Categories** — colour-coded tags; show/hide and customise colours
- **Drag to resize** — on desktop, drag the top or bottom edge of a ribbon to adjust its dates
- **Inline rename** — on desktop, double-click a ribbon label to rename it in place
- **Export** — save your timeline as PNG, PDF, JSON, or CSV
- **Import** — load a previously exported JSON or CSV file, with replace or merge options
- **Offline support** — works as an installable PWA with full offline capability

## Tech

Single-file React app (`index.html`) — no build step, no bundler.

| Dependency | Version | How |
|---|---|---|
| React | 18.3.1 | CDN (unpkg) |
| ReactDOM | 18.3.1 | CDN (unpkg) |
| Babel Standalone | 7.26.4 | CDN (unpkg), compiles JSX in-browser |
| Lucide Icons | inline SVG | bundled in `index.html` |
| Google Fonts (Syne) | — | CDN |

All CDN resources use SRI hashes for integrity verification. The service worker caches everything for offline use.

## Running locally

No installation needed — just open the file:

```bash
# Clone
git clone https://github.com/CrispyChickenDude/Life_Noodles.git
cd Life_Noodles

# Serve locally (required for service worker + PWA features)
npx serve .
# or
python -m http.server 8080
```

Then open `http://localhost:8080` in your browser.

> Opening `index.html` directly as a `file://` URL will work for basic use but service worker features (offline, PWA install) require an HTTP server.

## Deploying

The app is hosted on GitHub Pages. Push to `main` and it deploys automatically.

Live: **https://crispychickendude.github.io/Life_Noodles/**

When deploying a new version:
1. Bump `APP_VERSION` in `index.html`
2. Bump the cache name in `sw.js` (e.g. `life-noodles-v3` → `life-noodles-v4`) to force the service worker to refresh cached files on all devices

## Data & privacy

All data is stored in `localStorage` in your browser. Nothing is sent to any server. Exporting to JSON is the recommended way to back up your data.

## License

All rights reserved. This project is for personal use only. You may not copy, distribute, modify, or use any part of this code without explicit permission from the author.
