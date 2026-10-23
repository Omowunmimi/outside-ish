# Outsideish Product Brief

> This lowercase filename is provided as the requested entry point. The maintained product brief is also available at [PRODUCT.md](PRODUCT.md).

Outsideish helps people discover real places and experiences, turn ideas into outings, explore a city and keep a personal record of places visited. Lagos is the starting city.

## Platform
Outsideish is a mobile-first Progressive Web App (PWA) with a web entry point. Visitors can browse as guests. Installation is supported where the browser/platform allows it, but ordinary browser use must remain available.

## Product jobs
- **Inspire me:** turn a vague urge to go out into possible experiences.
- **Make me a plan:** build an outing using mood, time, budget, interests and starting neighbourhood, or choose “Surprise me”.
- **Help me explore:** discover places through a connected feed and freely explorable illustrated city map.
- **Help me remember:** save places/plans, share discoveries, mark visits and keep a journal.

## Established journey
Enter as a guest → browse/search or start with a mood/“Surprise me” → optionally add time, budget, interests and starting neighbourhood → review adventure ideas → inspect stops → adapt the outing or explore its places on the map → save/share → mark places visited and return to Saved/Journal.

This journey is flexible, not a required linear funnel. Direct search and direct map exploration are valid starting points.

## Core experience
- Discovery feed with varied discoveries rather than a generic directory.
- Search for a place, neighbourhood, interest or experience.
- Mood-led discovery and “Surprise me”.
- Adventures with understandable stops.
- A central, full-screen illustrated city map.
- Contextual place details in a bottom sheet without leaving Explore.
- Saved places/plans and a distinct visited/journal record.
- Meaningful connections between places, collections, neighbourhood stories and adventures.

## Confirmed interface constraints
- Mobile-app UI, not a conventional marketing website.
- Clear hierarchy and comfortable spacing, not cramped layouts.
- No emoji in the UI.
- No neumorphism, piles of elevated/floating buttons, heavy outlines, generic dashboards, repeated identical card layouts or primitive placeholder illustrations.
- Use one consistent icon set.
- Do not present an unapproved palette, font, exact spacing scale, icon drawing style, radius, breakpoint or animation timing as a decision already made.
- Motion may support interactions. Future sound is optional and never required.

## PWA requirements
- Valid `manifest.webmanifest` with appropriate app metadata and existing icon assets.
- Registered service worker with a deliberate app-shell cache and offline/failure experience.
- Cache versioning and update behaviour that avoid incompatible mixtures of HTML, CSS, JavaScript and assets.
- Installability tested on supported browsers.
- Fresh load, repeat load, update and offline checks.
- Cached UI must not be described as current venue data or live map information.
- Mobile browser and installed PWA use are primary. Desktop remains a web entry point and should guide visitors towards phone use for the intended experience.

## Trust and boundaries
Use real places and retain sources where available. Do not invent addresses, hours, prices, events or venue details. Label estimates. Do not imply live GPS, traffic, routing, open-now status, live events, booking, payment, reviews or cross-device sync unless implemented. Describe saved/visited persistence according to the actual storage mechanism.

## Documentation
- [PRD.md](PRD.md): detailed requirements, journeys, user stories, flows and acceptance criteria.
- [USER_FLOWS.md](USER_FLOWS.md): step-by-step functional flows.
- [PWA.md](PWA.md): manifest, service worker, install, cache, update and offline requirements.
- [PRODUCT.md](PRODUCT.md): product brief and established constraints.
