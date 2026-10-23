# Outsideish Quality Assurance Plan

## Release rule
A screen is not ready because it looks acceptable in one screenshot. Verify the main journeys, responsive layout, accessibility, PWA behaviour and the truthfulness of displayed information. Broken primary interactions block release.

## Product journeys
- [ ] Browsing and exploration work without signup.
- [ ] Search supports the implemented place, neighbourhood and interest data.
- [ ] Mood entry and “Surprise me” work.
- [ ] Time, budget, interests and starting area are optional preferences.
- [ ] Results connect to place details, the map and related adventures.
- [ ] Users can save and share supported items.
- [ ] Users can mark visits and access their journal.
- [ ] Swap/shorten actions work if shown and preserve unrelated choices.
- [ ] Empty and no-result states offer a useful next action.

## Map
- [ ] Map opens without a persistent place sheet or discovery tray.
- [ ] Search and filters are accessible.
- [ ] Map pan/zoom work with touch and pointer as implemented.
- [ ] Dragging does not activate a marker.
- [ ] Fixed controls do not move with the map world.
- [ ] Selecting a place opens the correct bottom sheet without navigating away.
- [ ] Closing the sheet preserves map position and zoom.
- [ ] Decorative illustration is distinguishable from interactive places.
- [ ] A list or other accessible alternative exists for place discovery.
- [ ] No unsupported claims of exact geography, live GPS, routing, traffic or travel time.

## Visual and responsive behaviour
- [ ] Interface reads as a mobile app, not a conventional marketing website.
- [ ] No website-style header, oversized section labels or unnecessarily large typography.
- [ ] No cramped, overlapping, clipped or horizontally overflowing content.
- [ ] No emoji, neumorphism, piles of elevated buttons, heavy outlines, generic dashboards or repeated identical card layouts.
- [ ] Icons are consistent and all referenced assets load.
- [ ] Test small mobile widths, common mobile widths, tablet transition and desktop.
- [ ] Desktop points visitors towards the phone experience without breaking access to the web entry point.
- [ ] Bottom navigation and content do not collide with safe areas.

## Accessibility
- [ ] Keyboard navigation and visible focus work.
- [ ] Controls have accessible names and meaningful labels.
- [ ] Touch targets are usable.
- [ ] Contrast and selected/disabled/error states are clear.
- [ ] State changes do not rely on motion, sound or colour alone.
- [ ] Reduced-motion preference is respected.
- [ ] Bottom sheets have sensible focus and dismissal behaviour.

## PWA
- [ ] manifest.webmanifest parses and includes required metadata.
- [ ] All referenced app icons exist and load.
- [ ] Service worker registers successfully.
- [ ] Installability is tested in supported browsers.
- [ ] Fresh install/load, repeat load, update and offline load are tested.
- [ ] Cache version changes when shell assets change.
- [ ] Offline UI does not pretend to provide live venue information.
- [ ] No stale HTML/CSS/JS combination appears after an update.

## Data integrity
- [ ] Place details use real sources where available.
- [ ] Unknown facts are not invented.
- [ ] Estimated prices and durations are labelled.
- [ ] Live status, routing and cross-device sync are only claimed if implemented.

## Technical
- [ ] JavaScript syntax checks pass.
- [ ] Manifest parses correctly.
- [ ] No missing assets or browser errors.
- [ ] Local storage errors do not crash the app.
- [ ] Production URL and deployed commit are verified before release is announced.


## Complete user-journey regression
Run these connected scenarios, not only isolated component checks:
1. Guest entry → discovery → place → related discovery.
2. Search → result → place details → map.
3. Mood or Surprise me → optional constraints skipped → adventure → inspect stops.
4. Adventure → swap/shorten → verify unrelated choices remain.
5. Map → select place → select another place → close sheet → verify map context.
6. Save → Saved → reopen; mark visited → Visited/Journal.
7. Share → successful share or fallback.
8. Fresh PWA load → install where supported → repeat launch → update → offline state.

For every failed test, record the screen, browser/device, viewport, steps, expected outcome and actual outcome. Do not mark a flow as passing because only its opening screen rendered.
