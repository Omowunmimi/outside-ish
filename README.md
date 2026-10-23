# Outsideish

Outsideish is a mobile-first PWA and web experience for discovering real places, making outings and keeping a personal record of places visited. Lagos is the starting city.

## Product direction
Outsideish combines a discovery feed with a freely explorable, geographically grounded illustrated city map. People can browse as guests, search, start from a mood or choose “Surprise me”, optionally set outing preferences, explore adventures, save and share places, mark visits and keep a journal.

The current UI has known visual and interaction issues. Documentation describes product requirements and constraints; it does not mean every requirement has already been implemented.

## PWA requirements
- Valid web app manifest and appropriate app metadata/icons.
- Service worker with a defined app-shell and offline/failure experience.
- Installability tested on supported browsers.
- Cache versioning and fresh/repeat/offline load checks.
- Clear separation between cached UI and current real-world venue information.
- Mobile-first installed and browser experiences; desktop is a web entry point that encourages phone use.

## Product boundaries
- Browsing does not require signup.
- Local saves and visit history must not be described as synced unless an account-backed service exists.
- Map illustration is not live navigation or proof of exact geography.
- Do not claim live traffic, GPS accuracy, opening status, events, routing or other live information unless integrated.

## Documentation
- [PRD.md](PRD.md): requirements, user journeys, platform and acceptance criteria.
- [PRODUCT.md](PRODUCT.md): concise product brief.
- [DESIGN_SYSTEM.md](DESIGN_SYSTEM.md): only user-specified interface constraints and implementation consistency requirements.
- [ICON_SYSTEM.md](ICON_SYSTEM.md): icon inventory and accessibility requirements.
- [MOTION.md](MOTION.md): interaction and motion constraints.
- [ARCHITECTURE.md](ARCHITECTURE.md): runtime, PWA, data and storage boundaries.
- [CONTENT_GUIDE.md](CONTENT_GUIDE.md): real-world information and uncertainty.
- [QA_PLAN.md](QA_PLAN.md): release and PWA acceptance checks.

## Run locally
Serve the repository root with a static server, for example:

    python3 -m http.server 4173

Then open http://localhost:4173.

## Implementation rule
Do not treat unapproved design choices as requirements. Do not claim a feature, PWA capability or deployment is complete until it has been implemented and tested.
