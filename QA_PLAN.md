# Outsideish QA Plan

## Purpose
Protect the mobile-first discovery experience as the visual system, map and feed evolve. This plan is for the current static PWA prototype and should expand alongside real content services.

## Viewports
- Small phone: 360 × 800
- Typical phone: 390 × 844
- Large phone: 430 × 932
- Tablet portrait: 768 × 1024
- Laptop: 1280 × 800
- Desktop: 1440 × 900

## Core journeys

### First visit and feed
- Arrival screen renders without layout shift or clipped art.
- Search, mood, time and spend controls are visible and usable.
- Primary planning action opens the planner.
- Discovery cards have a clear title, context and action.
- “Keep wandering” appends another batch rather than clearing the feed.
- Approaching the feed end can append more items without jumping scroll position.
- When the starter set cycles, the UI does not claim new data was fetched.
- No consecutive identical cards are added at a cycle boundary where practical.

### Search
- Exact place-name search opens the matching detail.
- Search supports relevant category and neighbourhood terms.
- No-match search gives a useful fallback and does not break navigation.
- Empty search gives an actionable prompt.

### Map
- Map opens as the primary, unobstructed city surface.
- Search, filters and essential controls are visible; no persistent tray, title badge or sticker annotations.
- Pan/drag works with mouse and touch.
- A drag does not activate a marker.
- Zoom and recenter work and keep map features aligned.
- Pins remain still when idle and have clear selected states.
- Pin tap opens the place bottom sheet without changing the active screen.
- The sheet is hidden on initial map load.
- Selecting another pin updates the open sheet.
- Closing the sheet preserves pan, zoom and filters.
- Search from map opens a matching place in the sheet.
- Filter updates markers and does not leave the filter panel open.
- No emoji placeholder art or primitive-shape map scenes.
- Map art does not claim exact cartography, GPS or live navigation.

### Place details
- Name, category, neighbourhood, description and practical details render.
- Opening hours and prices have appropriate caveats.
- External source links open safely in a new tab.
- Save toggles the saved state.
- Visit action updates the journal and counts.
- Share uses a supported share mechanism or a graceful fallback.

### Planner and outings
- Inputs can be changed and submitted.
- Result plans reflect the selected preferences as far as the dataset permits.
- A plan opens a detailed view.
- Plan stops open their related place details when available.
- Remix provides another ordering without implying live availability.

### Saved items and journal
- Saved places/plans persist across reloads on the same device.
- Empty states provide a clear next action.
- Visit entries show a date and can be opened.
- No account is required for local saves.

### PWA and resilience
- Manifest is valid JSON.
- Service worker registers without unhandled errors.
- Cached app shell loads on repeat visit.
- Offline state does not imply that place information is current.
- Cache version changes when shell assets change.

## Visual and accessibility checks
- No horizontal overflow at target widths.
- No critical content is hidden behind bottom navigation or device safe areas.
- Text remains readable and controls meet comfortable touch target sizes.
- Keyboard focus is visible.
- Interactive elements use semantic controls and have accessible names.
- Reduced-motion preference disables non-essential animation.
- Colour is not the only indicator of selection.
- Map discovery has a non-map list alternative.

## Technical checks
- Run node --check app.js.
- Parse manifest.webmanifest as JSON.
- Load the app in a browser at small mobile, typical mobile and desktop widths.
- Capture page errors and failed requests.
- Exercise the map, search, planner, detail, save and visit flows.
- Confirm all docs linked from README exist.
- Verify the Vercel deployment is ready before sharing the preview.

## Current prototype limitations
- The place and outing catalogue is small and locally bundled.
- Feed cycling provides continuous interaction but does not create new venue data.
- The map is an illustration-coordinate canvas, not a live geographic map.
- There is no live routing, traffic, open-now status or event feed.
- Saves and visit history are device-local and do not sync across devices.
- Place facts must be checked against the linked source before a visit.

## Release gate
A release is acceptable when the core journeys pass, there are no uncaught browser errors, no horizontal overflow at target widths, the map can be panned and zoomed, the feed does not dead-end, and remaining data limitations are visible and documented.
