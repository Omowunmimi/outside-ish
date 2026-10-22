# Outsideish

An illustrated city-discovery companion for people who want to find a reason to go outside, make a small plan, and keep discovering Lagos.

## Product direction

Outsideish should feel like wandering through an illustrated city field guide, not browsing a directory of generic cards. The map is a primary discovery surface; the feed should keep opening paths to more places, stories and outings. Mobile is the primary experience, with desktop treated as a deliberate, usable layout rather than a stretched phone screen.

## Current prototype

- Mobile-first PWA shell.
- Illustrated Lagos street scene and map.
- Map pins for a starter set of eight places, with pan, zoom and recenter controls.
- Search, category filters, place details and source links.
- Mixed discovery feed with a “Keep wandering” continuation action.
- Curated starter outings, a lightweight planner, saved places/plans and a visit journal.
- Device-local saves; no account required.
- The map is an editorial illustration, not exact cartography. Place information, opening details, prices and events should be checked before visiting. Live traffic, turn-by-turn routing and live event data are not connected.

The current place set is a starting collection, not a complete or live Lagos directory. New content should follow the source and freshness rules in [CONTENT_GUIDE.md](CONTENT_GUIDE.md).

## Product and design documentation

- [PRD.md](PRD.md): complete product requirements, audience, goals, journeys, functionality, data quality, accessibility, privacy, metrics and roadmap.
- [DESIGN_SYSTEM.md](DESIGN_SYSTEM.md): visual identity, colour, typography, illustration, component and responsive design rules.
- [MOTION.md](MOTION.md): motion tokens, map gestures, transitions, feedback, reduced-motion and QA requirements.
- [ARCHITECTURE.md](ARCHITECTURE.md): current technical structure, state boundaries, map model, PWA and future modules.
- [CONTENT_GUIDE.md](CONTENT_GUIDE.md): editorial voice, source/freshness labels and place data quality checklist.

## Project structure

- `index.html` — screens, SVG illustrations, map and navigation.
- `styles.css` — visual system, responsive layouts and interaction states.
- `app.js` — local content, UI state, discovery feed, planner, search and map interaction.
- `manifest.webmanifest` — PWA metadata.
- `sw.js` — service worker and shell cache.
- `assets/` — app icon and static assets.

## Run locally

This is a static web app. Serve the repository root with any local static server, then open it in a browser. For example:

```bash
python3 -m http.server 4173
```

Open `http://localhost:4173`.

## Important product boundaries

- “Keep wandering” currently continues through the curated starter dataset and reshuffles it after one round. A genuinely expanding discovery library requires a larger reviewed content collection and, later, a maintainable content source.
- Map geometry is illustrative and should not be used to infer actual distances or walking routes.
- Opening information and spend are not guaranteed current. Check venue sources before departure.
- Saved items and visit history are stored in the browser on this device and do not sync across devices.
