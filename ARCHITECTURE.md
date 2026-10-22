# Outsideish Technical Architecture

## Current implementation
Outsideish is currently a static, client-rendered PWA built with HTML, CSS and vanilla JavaScript. It is hosted by the existing Vercel project and sourced from the `rebuild/outsideish-v1` branch in the `Omowunmimi/outside-ish` repository.

Core files:
- `index.html`: screen structure, illustrated SVG map and navigation.
- `styles.css`: visual tokens, component styles, responsive layouts and motion.
- `app.js`: local content, UI state, search, planning, save/visit behaviour and event handlers.
- `manifest.webmanifest`: install metadata.
- `sw.js`: app-shell caching and offline fallback.
- `assets/`: icon and other static artwork.

## Runtime model
- Screens are toggled in the client using a single page shell.
- Place and adventure content is currently bundled in JavaScript.
- Saves, visits and optional name are stored in localStorage with an Outsideish namespace.
- The service worker caches the shell for repeat/offline entry.
- The map is authored SVG and should be treated as an illustrated discovery surface, not a geographically accurate routing engine.
- There is no backend, authentication, live place API, event feed, traffic service or route provider wired in the current prototype.

## State boundaries
### Persistent local state
- saved items
- visited place log
- optional display name

### Ephemeral state
- current screen and previous screen
- selected place or adventure
- mood, interests, time, budget and area preferences
- search query and current map filters
- map pan and zoom transform

Persistent state should be versioned or migrated if the content schema changes. Never persist sensitive information unnecessarily.

## Recommended future modules
1. **Content repository:** structured place, collection, neighbourhood and adventure data, separate from rendering.
2. **Source/freshness metadata:** source URL, source type, checked date and confidence for factual details.
3. **Discovery engine:** deterministic relevance ranking based on user constraints, location/area and content tags; avoid purely random output.
4. **Map adapter:** separates map interactions from data source and visual map renderer. Can support the illustrated map now and a coordinate-aware provider later.
5. **Local storage service:** centralises versioned saves, visited entries and preferences.
6. **Analytics adapter:** optional privacy-conscious events with no unnecessary personal data.
7. **Error/empty-state utilities:** consistent handling for unavailable content, offline state and no search matches.

## Map interaction model
Map view state includes translation x/y, scale, active category filter, selected place ID and sheet visibility. Map transform and sheet state are separate.

1. Enter Explore and render the map without a tray or title overlay.
2. Pan/zoom/search/filter while remaining on the map.
3. Selecting a place sets selected place ID and opens the contextual sheet.
4. The sheet renders the same place record used by feed/search.
5. Selecting another place updates the sheet in place.
6. Dismissal clears selection and sheet visibility but preserves pan, zoom and filters.
7. Save/source/visit actions operate on the selected place without forcing full-page navigation.

Pointer Events should support mouse and touch. A movement threshold differentiates dragging from clicking. Bounds prevent the map disappearing entirely. Controls remain fixed outside the transformed SVG world. Decorative features are not interactive destinations. Map geometry is not exact lat/long until a real geographic source is integrated.

## Data trust boundaries
Content currently bundled into JavaScript is a prototype seed dataset. It must not be represented as a live or complete directory. Opening hours and prices require source and review metadata. Map illustration geometry is not a source of real distance or travel time. Future integrations should be evaluated for coverage, licensing, update cadence, privacy and cost before implementation.

## PWA/offline notes
- Update the service worker cache version whenever shell assets change.
- Cache the core shell and local assets.
- External fonts or remote sources may not be available offline.
- Do not cache dynamic responses indefinitely without freshness rules.
- Clearly distinguish locally available saved content from information that requires a connection.

## Motion and future sound
Keep map drag direct and sheet motion independent of the map transform. Respect reduced motion and avoid continuous marker animation. Future sound must be optional, default off, never autoplay and never carry essential information.

## Quality gates
Before merging:
- Parse/check JavaScript syntax.
- Validate manifest JSON.
- Exercise primary flows: home → plan → detail; home → map → pin → bottom sheet → close; save → saved; search → detail; visit → journal.
- Test at 360, 390, 768, 1024 and 1440px widths.
- Check horizontal overflow, keyboard focus, reduced motion, touch target sizes and console errors.
- Verify the preview deployment points to the intended branch and commit.
## 9. Discovery feed evolution

The current prototype bundles a small set of places and outings in app.js. The feed may append another mixed batch from that local set so browsing does not stop abruptly, but cycling a small set is not equivalent to having a genuinely large catalogue.

Recommended evolution:
- Extract content into structured data files or a content service.
- Use stable IDs, categories, tags, source metadata, freshness timestamps and editorial status.
- Implement cursor-based pagination and a loading/retry state.
- Keep feed rendering independent from data retrieval.
- Add ranking inputs for mood, time, budget, interests, area, diversity and editorial priority.
- Preserve feed cursor and scroll position across detail navigation.
- Add deduplication within a session and avoid immediate repeats when a new batch begins.
- Introduce analytics through a privacy-conscious adapter only after defining the data policy.

## 10. Map renderer boundaries

The current SVG uses illustration-space coordinates. Those coordinates are only for artwork layout and marker placement. They must never be used for geographic distance, routing or live proximity calculations.

Keep the following responsibilities separate:
- **Map renderer:** draws the illustrated map and its interactive markers.
- **Map interaction controller:** pan, zoom, recenter, marker selection and filters.
- **Discovery content:** place details and editorial metadata.
- **Future geographic adapter:** real coordinates, tile/provider attribution, geocoding and routing integration.

When the product needs real navigation, prefer opening a trusted external maps destination or integrate a suitable provider only after evaluating terms, pricing, attribution, coverage and accessibility. Do not present illustrative paths as actual walking routes.
