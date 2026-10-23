# Outsideish Technical Architecture

## Platform
Outsideish is intended to be a mobile-first Progressive Web App with a web entry point. The repository currently uses HTML, CSS and JavaScript. Treat each capability as implemented only after verifying the code and testing it.

Expected core files include:
- index.html: app structure and screens.
- app.js: navigation, discovery, planning, saving, visits and map interactions.
- redesign.css and/or styles.css: stylesheets; audit load order and remove conflicting rules rather than layering patches.
- manifest.webmanifest: PWA metadata.
- sw.js: service worker and app-shell/offline behaviour.
- assets/: icons and illustrations.

## PWA requirements
- Keep manifest fields valid and ensure referenced icons exist.
- Register and test the service worker.
- Define which app-shell assets are cached and what happens when a request fails offline.
- Version caches when relevant assets change and remove obsolete caches when appropriate.
- Test first load, repeat load, update and offline load.
- Do not imply that cached app-shell files provide current venue details or live map information.
- Verify installability in supported browsers rather than assuming the manifest alone makes the app installable.

## State and persistence
Browsing should work without signup. If saves and visit history use local storage, label them as device-local and handle missing, malformed or outdated data without crashing. Do not claim account-backed sync or cross-device persistence unless a backend is implemented.

Keep selected place, sheet visibility and map position/zoom as explicit UI state. Map movement should not change the primary destination. Dismissing a place sheet should preserve the map position and zoom.

## Real-world data
Use stable identifiers for places and preserve available sources. Do not fabricate missing details. Mark estimates and uncertainty. Any live information, geographic accuracy or routing claim requires a real source and implementation.

## Responsive and accessible behaviour
Support mobile browser and installed PWA use. Desktop remains accessible as a web entry point and should direct users to the phone experience. Test keyboard, touch, safe-area spacing, focus behaviour and reduced motion.

## Release discipline
Run syntax checks, asset checks, browser interaction checks, responsive tests and PWA install/offline tests before release. Verify the exact deployed commit and environment. A merged change or preview URL is not proof that production is updated.


## PWA lifecycle checklist
Document the cache strategy used by the actual service worker, including cached shell assets, runtime requests, failed requests, version changes, activation and obsolete-cache cleanup. When the HTML entry point, CSS, JavaScript or icons change, test a clean load and an already-cached client. Do not assume the service worker is correct simply because it exists in the repository.

## Feature status discipline
Separate intended behaviour from verified behaviour in code reviews and release notes. A requirement in PRD.md is a target, not evidence that the current app implements it. Record actual test results for map interactions, local persistence, sharing, installability, offline behaviour and production deployment.
