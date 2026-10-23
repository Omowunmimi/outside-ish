# Outsideish Product Brief

## Product idea
Outsideish is a city-discovery companion that helps people find places and experiences, turn them into outings, explore a city and remember where they have been. Lagos is the starting city.

## Product jobs
- **Inspire me:** turn a vague urge to go out into possible experiences.
- **Make me a plan:** build an outing based on mood, time, budget, interests and starting area, or choose “Surprise me”.
- **Help me explore:** discover real places through a connected feed and a full-screen illustrated city map.
- **Help me remember:** save places and plans, share discoveries, mark visits and keep a journal.

## Core journey
1. Enter and browse as a guest.
2. Search for a place, neighbourhood, interest or type of experience, or start with a mood.
3. Optionally select time, budget, interests and starting neighbourhood. All preferences can be skipped.
4. Get a small set of relevant adventures.
5. Open an adventure to understand its stops and why they fit together.
6. Swap a stop, shorten the outing, save or share it, or explore the map.
7. Return to saved places, previous plans, visited places and journal entries.

## Map
The map is a primary part of the product. It should be freely explorable, geographically grounded and richly illustrated with city details, buildings, streets, people, landmarks and interactive places. It is not a static image with a few decorative pins.

The initial map view has search and filters, without a persistent place sheet or discovery tray. Selecting a place opens a bottom sheet without navigating away from the map. Closing the sheet preserves the current map position and zoom. Map exploration and feed browsing should connect, so a place can lead to an adventure, collection or neighbourhood story and vice versa.

The map must not imply exact cartography, live GPS, live traffic, turn-by-turn navigation or real travel times unless those are supported by integrated data.

## Platform: PWA and web
Outsideish is a mobile-first Progressive Web App with a web entry point.
- The app should be installable where supported and have a valid manifest and service worker.
- The service worker should provide a deliberate app-shell/offline experience and update its cache when assets change.
- Test fresh load, repeat load, install flow and offline behaviour. Cached UI must not be presented as live venue data.
- Mobile browsers and installed PWA use are primary. Desktop should point visitors towards using a phone for the intended experience rather than expanding the mobile interface into a conventional desktop dashboard.

## Guest use and personal history
Exploration does not require an account. Save and visited history can work locally on the device. Clearly distinguish local storage from any future account-backed sync. Only ask for signup when a feature actually requires it.

## Real places and trustworthy information
Use real places and cite or retain sources for information. Make uncertainty visible where information is missing or may change. Do not invent addresses, opening hours, prices, events or venue details. Mark estimates as estimates.

## Interface constraints already specified
- Mobile-app UI, not a conventional marketing website layout.
- No website-style headers, oversized section labels or unnecessarily large typography.
- Keep the interface clean and readable rather than cramped.
- No emoji in the UI.
- No neumorphism, stacks of elevated/floating buttons, heavy outlines, generic dashboards, repeated identical card layouts or primitive placeholder illustrations.
- Use a consistent icon set. This brief does not prescribe an unapproved icon style, colour palette, font family or exact token values.
- Motion may support the experience. Future sound is optional, never required.
- Include useful loading, empty, no-result, offline and error states, and support accessibility.

## Out of scope unless implemented
Live GPS accuracy, traffic, turn-by-turn directions, real-time opening status, live event feeds, bookings, payments, reviews and cross-device sync must not be implied without a working integration.
