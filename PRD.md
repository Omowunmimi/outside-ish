# Outsideish Product Requirements Document

## Product summary
Outsideish is a mobile-first PWA and web experience for discovering real places, making outings and keeping a personal record of places visited. Lagos is the starting city. The product should work for guests without requiring an account to explore.

## Product jobs
1. **Inspire me:** help turn a vague desire to go out into possible experiences.
2. **Make me a plan:** help build an outing using mood, available time, budget, interests and starting area, with “Surprise me” as an option.
3. **Help me explore:** connect discoveries, places, collections and adventures through a full-screen illustrated city map and browsing feed.
4. **Help me remember:** save places and plans, share discoveries, mark places visited and keep a journal.

## Core journey
1. Open Outsideish and browse or search without signing in.
2. Search for a place, neighbourhood, interest or experience, or choose a mood.
3. Optionally add time, budget, interests and starting neighbourhood. Allow skipped preferences and a Surprise me path.
4. Receive a small set of relevant adventures rather than an undifferentiated directory.
5. Open an adventure to understand its stops and why they belong together.
6. Explore its places on the map, change a stop, shorten a plan, save or share it.
7. Return to saved places, previous plans, visited places and journal entries.

## Product surfaces
- **For you / discovery:** search, mood-led entry points and varied discoveries.
- **Explore:** full-screen illustrated map with search and filters. Selecting a place opens a contextual bottom sheet without navigating away from the map.
- **Plan:** optional preferences and a changeable outing.
- **Saved:** places and plans saved by the visitor.
- **Visited / journal:** places the visitor marks as visited and their personal record.

Names and navigation arrangement can be adjusted during implementation only when supported by the product flow; do not add destinations or steps just to fill the interface.

## Map requirements
- The map is a central experience, not a static illustration behind a few pins.
- It should be freely explorable and geographically grounded, with illustrated streets, buildings, storefronts, people, landmarks and relevant local details.
- Search and filters are available on the map. Do not show a persistent place sheet or discovery tray on initial entry.
- Tapping an interactive place opens a bottom sheet while remaining on the map. Closing it returns to the same map position and zoom.
- The map and discovery feed should lead into one another: a place can lead to a collection, neighbourhood story or outing, and an outing can lead back to map exploration.
- Decorative scenery and interactive places must be distinguishable.
- Do not claim exact geography, live GPS, routing, distance, traffic or travel time unless supported by an actual integrated source.

## PWA and web requirements
Outsideish must be developed and documented as a Progressive Web App, not just a responsive webpage.
- Provide a valid web app manifest with app name, short name, icons, theme/background metadata and appropriate display settings.
- Provide a service worker for the app shell and a defined offline/failure experience.
- Ensure installability requirements are met and test installation where supported.
- Ensure app assets and navigation behave on fresh load, repeat load and offline load.
- Update the service-worker cache when shipped assets change, and prevent stale HTML/CSS/JS combinations.
- Treat offline capability honestly: cached app UI does not mean venue data, hours, events or maps are live or fully available offline.
- Support mobile browsers and installable PWA use. Desktop remains supported as a web entry point, but should guide visitors towards using a phone for the intended app experience rather than stretching the mobile UI into a desktop dashboard.
- Account for safe areas, keyboard input, touch interaction and browser differences.

## Guest access, saves and journal
- Browsing and exploring do not require signup.
- Saved items and visit history must clearly indicate whether they are stored on the current device or synced by an implemented account service.
- Do not imply cloud sync, account recovery or cross-device persistence unless built.
- Signup can be offered later when a user chooses a feature that actually requires it; do not block initial exploration.

## Real-world information and trust
Use real places and sourced information. Keep source links and note uncertainty where details may change or cannot be confirmed. Do not invent addresses, prices, opening hours, events, reviews or venue features. Label spend and duration as estimates when they are estimates. Do not imply real-time availability or routing without an integration.

## Interface requirements
- Mobile-app UI, not a conventional marketing website layout. Do not add website-style headers, oversized section labels or unnecessarily large type.
- Clear hierarchy and comfortable spacing. Do not cram controls, labels and content together.
- No emoji in the interface.
- Do not use neumorphism, piles of elevated/floating buttons, heavy outlines, generic dashboards, repeated identical card layouts or primitive placeholder illustrations.
- Use a consistent icon set. The actual icon family and detailed styling must be approved through the implementation, not guessed from this document.
- Motion can support orientation and interactions. Any future sound is optional and must never be required to use the product.
- Include loading, empty, no-results, offline and error states, as well as keyboard and assistive-technology support.

## Scope boundaries
Do not claim live routing, live traffic, GPS accuracy, open-now status, live event feeds, booking, payment, public reviews, or cross-device sync unless each capability is implemented and its source is documented.

## Acceptance criteria
- Core journeys work without an account.
- Search, mood entry, optional preferences and Surprise me are usable.
- Place details open in a bottom sheet without leaving Explore.
- Map pan/zoom and pin selection do not conflict.
- Saved and visited states persist according to the actual storage model.
- The feed, map, places and adventures connect to one another.
- All visible controls work and have clear accessible names.
- Layout is legible at mobile sizes with no clipping, overlap or horizontal overflow.
- PWA manifest, service worker, installability and offline behaviour are tested.
- All real-world claims are sourced or clearly labelled as estimates/uncertain.
