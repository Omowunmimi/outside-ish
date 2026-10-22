# Outsideish product brief

## Product idea
Outsideish is a playful city-discovery companion. It helps someone discover a version of Lagos they would not find by following the usual recommendations. It starts with the person's situation and curiosity, not a directory of 100 places.

**Product promise:** open the app, find a plan that fits your day, make it yours, and go have a life.

## Core jobs
1. **Inspire me:** turn a vague urge to leave home into a few appealing possibilities.
2. **Make me a plan:** suggest a small outing that respects time, spend, mood, interests and starting area.
3. **Help me explore:** reveal neighbourhood stories and specific places through a full-screen illustrated map.
4. **Help me remember:** save places, revisit plans, mark visits and build a personal city journal.

## Primary journey
1. Arrive on a warm, illustrated welcome screen with useful search and quick mood choices.
2. Search for a place, neighbourhood, interest or kind of experience, or start with a mood.
3. Optionally choose time, spend, interests and a starting neighbourhood. All questions are skippable; “Surprise me” is a first-class path.
4. Get three curated mini-adventures rather than a long list.
5. Open an adventure to understand why the stops work together, how long to allow, likely spend, neighbourhood and transport considerations.
6. Swap a stop, shorten the plan, save it, share it or explore the map.
7. On return, see saved places, visited discoveries, collections and thoughtful follow-up ideas.
8. No account is required for browsing. Guest saves stay on the device. Ask for a name only if the person wants a more personal hello. Do not introduce username/password until account-backed sync is actually needed.

## Map experience
- Explore is a full-screen, layered illustrated map, not a list with clustered pins.
- Drawn streets, buildings, storefronts, tropical plants, danfos, people and small observational details should make the city feel inhabited.
- Pins and illustrated objects reveal a place's story, useful details and why it is worth a detour.
- Keep the illustrated map visibly distinct from live navigation. Do not imply GPS accuracy, live traffic or exact travel time unless a real routing source supplies it.
- Map details should feel like a story unfolding, with gentle movement and a reduced-motion alternative.

## Visual direction
- Warm, playful, editorial, locally observant and witty, with Nigerian phrasing used naturally rather than as decoration.
- Original illustrations carry narrative details and humour. Mix illustration with verified real venue imagery when it adds value.
- Palette: plum, coral, lilac, warm yellow, cream and olive. Avoid a generic green/blue/yellow primary palette.
- Rounded controls, soft custom icons, compact app-scale typography, lively but restrained motion, no sharp generic icon set, no unnecessary shadows.
- Mobile should feel like a real app with persistent navigation and a full-bleed map. Desktop should reorganize into a coherent web-app layout, not stretch a phone canvas into empty space.

## Content model
- **Places:** verified name, category, address, neighbourhood, description, source URL, current opening information with last-checked timestamp, price range with confidence/estimate labels, accessibility and contact details when available.
- **Adventures:** a clear idea for the outing, two to four compatible stops, estimated duration/spend, neighbourhood, transport guidance, why the combination works, swap/shorten actions and uncertainty notes.
- **Collections:** editorial groupings such as a slower side of Lagos, bookish corners, low-budget dates, art without the fuss and rainy-day plans.
- **Neighbourhood stories:** a small narrative about the area, local details and a few worthwhile stops.
- **What's happening:** events with event date/time, venue, source, ticket details and a last-checked timestamp. Never show stale events as happening now.
- **Personal collections/journal:** locally saved plans and visits first; sync only after an account system exists.

## Recommendation principles
Do not sort only by distance or popularity. Prefer combinations that work together for the person's available time, budget, mood, interests, starting neighbourhood, opening hours and reliable travel estimates. Be clear when a value is estimated or unavailable. A smaller, trustworthy collection beats hundreds of unverified listings.

## States and edge cases
- Empty saved list and empty journal
- No search results and spelling/area suggestions
- No network, stale cache, API rate limit, upstream failure and retry
- Location permission denied or unsupported; manual starting-area selection remains available
- Missing/uncertain hours, price, route, event details or venue photos
- Venue closed, event cancelled, plan no longer feasible and inaccessible stop
- Save/share unsupported; clipboard fallback where possible
- Storage unavailable or cleared; explain that guest data is device-local
- Reduced motion, keyboard navigation, screen readers, focus visibility and small screens
- Desktop/tablet layout, orientation changes and safe-area insets

## Data and integrations
The current repo contains a first front-end prototype and a small, source-linked starter set. It does **not** yet have live place search, live event ingestion, routing/traffic estimates, real GPS positioning, user accounts or cloud sync. The current map is a custom illustrated experience, not a geographically accurate navigation map.

Before describing those capabilities as live, connect and test:
- A places source for current venue details, opening hours and place search (for example, Google Places or Foursquare; API key and billing/terms need review).
- A geocoding/routing source for route distance and traffic-aware travel estimates (for example, Mapbox Directions with the relevant traffic product, or another verified provider).
- Event feeds from official venues and reputable local calendars, with source URLs, freshness checks and a stale-data policy.
- A small editorial verification workflow so venue descriptions, budgets, transport notes and pairings remain useful.

Do not request credentials in chat. If a paid or key-protected service is selected, have the owner configure secrets directly in the project settings. Keep keys server-side; never ship private API keys in client JavaScript.

## Current implementation status
Implemented in the prototype: mobile-first app shell, illustrated arrival scene, full-bleed schematic Lagos map, interactive discovery pins, mood/time/budget/interest/starting-area inputs, three starter adventure concepts, place details with source links, local saved items, local visit journal, share action, responsive desktop layout, PWA manifest and offline app-shell cache.

Still to build before calling it a complete product: provider-backed live place data, real geospatial map placement, traffic-aware routing, live events, robust search over a larger verified collection, swap/shorten itinerary logic, loading/error/offline freshness states, accessibility and end-to-end interaction tests, and final visual QA on mobile and desktop.
