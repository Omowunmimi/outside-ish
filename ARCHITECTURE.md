# Outsideish Technical Architecture

**Status:** Current runtime notes and reset constraints. Documentation is not proof that a feature currently works.

## Runtime
Outsideish is a static client-rendered PWA using HTML, CSS and vanilla JavaScript in the Omowunmimi/outside-ish repository. The current UI has reported visual and interaction defects; the documents describe target behaviour, not verified completion.

Expected core files:
- index.html: screen structure, map SVG, navigation and desktop hand-off.
- redesign.css: replacement stylesheet intended to be loaded by the HTML entry point; verify the actual link.
- styles.css: legacy stylesheet may remain; do not re-enable without auditing conflicts.
- app.js: local content, navigation, search, planning, save/visit and map interactions.
- manifest.webmanifest: install metadata.
- sw.js: app-shell cache and offline fallback.
- assets/: icons and illustrations.

## Data and state boundaries
Content is locally bundled unless an integration is explicitly implemented. Local storage may contain saved places/plans and visit history. Ephemeral state includes current screen, search, filters, planner selections, selected place, sheet visibility and map transform. Use stable IDs and handle malformed/old local storage without crashing.

A place record should support stable ID, name, category, neighbourhood, description, tags, source URL/type, last-checked date, estimate flags and related items where known. Never invent missing facts to fill a layout.

## Design system and icons
CSS custom properties are the source of truth for colour, spacing, typography, radii, controls and motion. Repeated components share rules and documented variants. Use the central custom SVG icon family defined in ICON_SYSTEM.md. Remove or isolate legacy styles instead of allowing two competing systems to style the same component. No emoji or arbitrary Unicode fallback icons.

## Navigation contract
Primary destinations have stable IDs and one navigation/state contract. Bottom navigation stays visible on all mobile screens, including Explore. Navigating away closes the place sheet without corrupting map state. Returning to Explore preserves map context where practical.

## Map contract
Keep map-world transform separate from fixed controls and sheet state. Pointer Events plus a drag threshold distinguish movement from pin taps. Markers use stable place IDs; decorative scenery is not interactive. Selecting a marker opens the contextual sheet. Dismissal preserves pan, zoom and filters. Illustration coordinates do not support real distance, directions or geographic precision.

## Error and empty states
Handle no search results, missing details, empty Saved/Journal, unsupported share, invalid storage, offline shell and unavailable source links. Empty states need a concise explanation and one relevant next action. Do not add artificial spinners to synchronous local actions.

## PWA and privacy
Increment the service-worker cache version when shell assets change. Verify fresh and repeat loads to avoid stale HTML/CSS combinations. A cached shell does not make venue facts current. Browsing should not require an account. Keep local storage minimal and namespaced. Device-local saves do not sync or constitute a backup.

## Release discipline
Run syntax, responsive, accessibility and browser interaction checks before merging. Confirm the exact deployed commit and environment before calling a URL current. A preview is not production, and a merged commit is not proof of deployment. Report deployment blockers honestly.
