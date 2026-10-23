# Outsideish PWA Requirements

## Purpose and status
Outsideish is a mobile-first Progressive Web App (PWA) with a web entry point. It must be treated as an installable web application where supported, not only a responsive page. This document defines required behaviour and tests; it does not claim that every requirement is already satisfied.

## Manifest
Maintain a valid `manifest.webmanifest` with appropriate:
- application name and short name;
- start URL and scope suitable for the deployment;
- display mode suited to the app experience;
- theme and background metadata;
- icon entries with correct paths and supported sizes/purposes.

Every referenced icon must exist and load successfully. Validate the manifest in supported browsers. A manifest alone does not guarantee installability.

## Service worker
The service worker must define a deliberate strategy for app-shell resources and request failures.
- Confirm registration succeeds on the deployed HTTPS origin or supported local environment.
- Define which HTML, CSS, JavaScript, manifest and local assets are cached.
- Choose caching behaviour intentionally and define how changed resources are refreshed.
- Version/invalidate caches when app-shell assets change.
- Remove obsolete caches where appropriate.
- Ensure update/activation does not leave a visitor using incompatible HTML, CSS, JavaScript and assets together.
- Handle failed/offline requests deliberately and avoid presenting failure as success.

## Offline expectations
Document what remains available offline based on what is actually cached or stored locally. A cached app shell does not mean venue details, hours, prices or events are current; remote images or map resources are available; search has a live index; or routing, traffic and GPS work.

Show a useful offline/failure state when a requested capability is unavailable. Do not promise full offline discovery unless its data and interactions are available locally and tested.

## Install and return
- Normal browser use remains available without installation.
- Allow installation through browser-supported flows where available.
- Do not show a fake install success state or an install prompt disconnected from the platform's actual install mechanism.
- Test launch from the installed app, repeat launch and navigation.
- Keep app identity and icon assets coherent between manifest and interface.

## Responsive PWA behaviour
- Mobile browser and installed PWA use are primary.
- Respect device safe areas, touch interaction, software keyboard behaviour and browser differences.
- Desktop remains a web entry point and should direct visitors towards phone use for the intended experience rather than stretch the mobile UI into a dashboard.
- Primary navigation and key interactions work in browser and installed modes.

## Required verification
1. Validate manifest syntax and required fields.
2. Confirm every referenced icon exists and loads.
3. Confirm service-worker registration and active state.
4. Test a first visit with no prior cache.
5. Test a repeat visit with cache.
6. Test an update after app-shell resources change.
7. Test offline load and a failed network request.
8. Confirm offline UI does not misrepresent current venue information.
9. Test installation and launch on supported browsers/platforms.
10. Verify the deployed commit and origin before reporting results.

## Release reporting
Report which browsers/platforms were tested, what worked, what remains unavailable, and the exact deployment commit. Do not report PWA readiness based only on a valid manifest or a successful local test.
