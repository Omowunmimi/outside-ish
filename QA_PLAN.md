# Outsideish Quality Assurance Plan

## Release rule
A screenshot at one width is not a pass. Every primary screen must pass visual, interaction, responsive, accessibility and technical checks. Reported crowding, broken interactions and missing icons are release blockers.

## Viewports
360×800, 390×844, 430×932, 759px wide, 760px wide, 1024×768, 1280×800 and 1440×900.

## Visual system
- [ ] Shared palette and typography tokens are used consistently.
- [ ] Spacing and hierarchy make each screen easy to scan.
- [ ] No overlapping, clipped or crushed content.
- [ ] Content groups have breathing room; not every section is the same card.
- [ ] No raised/neumorphic buttons, offset shadows or heavy outlines.
- [ ] No emoji, arbitrary Unicode substitutes or mixed icon packs.
- [ ] Custom SVG icons load and have consistent sizing, weight and alignment.
- [ ] Empty, selected, disabled, loading, error and success states are designed.

## For you and search
- [ ] Purpose and first action are obvious.
- [ ] Search works for supported place/category/neighbourhood terms.
- [ ] Feed has editorial variety and no immediate duplicate items where avoidable.
- [ ] Continue discovery preserves scroll and does not claim new data was fetched when cycling local content.
- [ ] No-result state offers a useful next action.

## Map
- [ ] Opens unobstructed, with essential controls only.
- [ ] No persistent tray, title banner or place sheet on initial load.
- [ ] Distinct illustrated scenes; no repeated crop pretending to be a full city.
- [ ] Pan works on touch and pointer; dragging does not activate a pin.
- [ ] Zoom/recenter work and controls stay fixed.
- [ ] Markers map to actual content records; decorative scenery is not interactive.
- [ ] Pin tap opens the correct sheet without leaving Explore.
- [ ] Selecting another pin updates the same sheet.
- [ ] Closing sheet preserves pan, zoom and filters.
- [ ] Search and filters work.
- [ ] Bottom navigation remains visible and functional.
- [ ] A non-map list alternative exists.
- [ ] No implied live GPS, routing, distance or exact cartography.

## Place, plan, saved and journal
- [ ] Details do not fabricate missing facts.
- [ ] Prices/duration are labelled estimates when appropriate; hours include freshness caveats.
- [ ] Save and visit update state and persist on the same device.
- [ ] Share works or has a graceful fallback.
- [ ] Planner results reflect supported preferences and ordered stops.
- [ ] Swap/shorten/remix change the plan and preserve unrelated constraints.
- [ ] Empty states offer a clear action.
- [ ] UI does not claim cross-device sync.

## Responsive and accessibility
- [ ] No horizontal overflow at any target width.
- [ ] At 759px mobile remains coherent; at 760px+ desktop hand-off appears.
- [ ] Safe areas and bottom navigation do not cover content.
- [ ] Controls have visible focus and accessible names.
- [ ] Touch targets are comfortable, ideally 44×44px.
- [ ] Contrast passes and state is not communicated by colour alone.
- [ ] Reduced-motion preference is respected.
- [ ] Place sheet focus/announcement behaviour is accessible.

## Technical
- [ ] node --check app.js passes.
- [ ] manifest.webmanifest parses as JSON.
- [ ] Referenced assets load; no console/page errors.
- [ ] Service worker and cache version are correct.
- [ ] Clean and repeat loads are tested.
- [ ] README links and referenced filenames are valid.
- [ ] Current limitations are stated accurately.
- [ ] Deployment commit and target are verified before sharing a release URL.

## Known prototype boundaries
Starter data is not a complete or live Lagos directory. The map is illustrative. Live routing, traffic, open-now and events are not connected. Saves and visits are device-local.

## Sign-off
Any broken primary navigation, wrong place selection, lost map state, missing icon, overlapping layout, horizontal overflow, uncaught browser error or unsupported live-data claim blocks release. Record lesser defects with screen, viewport, reproduction steps and severity.
