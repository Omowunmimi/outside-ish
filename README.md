# Outsideish

Outsideish is an illustrated city-discovery companion for people who want to find a reason to go outside, make a small plan and keep discovering Lagos.

## Current direction
Outsideish should feel like a thoughtful illustrated city field guide, not a generic directory or a stack of repeated cards. Its visual identity comes from a connected, locally grounded city illustration; its usability comes from clear hierarchy, generous spacing, consistent components and one custom icon family.

The current UI has reported layout and interaction problems. The documents below define the reset target; they do not claim that the current implementation already passes.

## Product boundaries
- Mobile-first PWA with an intentional phone-first experience.
- Primary destinations: For you, Explore, Plan, Saved and Journal.
- Explore uses an authored illustrated map with pan/zoom and contextual place sheets.
- Map geometry is illustrative, not exact cartography.
- Starter content is not a complete or live Lagos directory.
- Live traffic, turn-by-turn directions, open-now status and live event feeds are not connected.
- Saves and visit history are device-local unless a future backend is implemented.

## Source-of-truth documentation
- [PRD.md](PRD.md): product requirements, information architecture, journeys and screen contracts.
- [DESIGN_SYSTEM.md](DESIGN_SYSTEM.md): palette, typography, spacing, components and responsive rules.
- [ICON_SYSTEM.md](ICON_SYSTEM.md): approved icons, sizing, accessibility and asset rules.
- [MOTION.md](MOTION.md): map gestures, transitions, feedback and reduced motion.
- [ARCHITECTURE.md](ARCHITECTURE.md): runtime, state, content, PWA and deployment.
- [CONTENT_GUIDE.md](CONTENT_GUIDE.md): editorial voice and data trust.
- [QA_PLAN.md](QA_PLAN.md): release-blocking visual, interaction, accessibility and technical checks.

## Project structure
Check the repository before editing. Expected files include index.html, redesign.css, app.js, manifest.webmanifest, sw.js and assets/. styles.css may remain as legacy; audit before reusing it.

## Run locally
Serve the repository root with a static server, for example:

    python3 -m http.server 4173

Then open http://localhost:4173.

## Implementation rule
Do not continue polishing the existing UI until the design system, icon set, component states and screen-by-screen acceptance criteria are implemented and tested. A merged commit is not proof of production deployment. Verify the exact deployed commit and environment before sharing a release URL.
