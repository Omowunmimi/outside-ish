# Outsideish Product Requirements Document

**Status:** Reset specification and source of truth before further UI implementation  
**Initial city:** Lagos, Nigeria | **Platform:** Mobile-first PWA

## Why this reset exists
The current UI has serious quality problems: cramped composition, inconsistent visual language, missing/inconsistent icons and broken interactions. The previous visual pass is not an approved direction. This is a structural reset, not another polish pass. First align the product architecture, screen contracts, design tokens, icon set and acceptance criteria. Then rebuild and test each screen.

## Product promise
Outsideish helps people find something worth going outside for, build a lightweight outing and keep discovering. It should feel like a curious local's illustrated city field guide, not a generic directory, a dashboard or a map decorated with pins.

## Principles
1. Clarity before decoration. Each screen has one clear purpose and primary action.
2. A connected city. Places lead to relevant collections, neighbourhood stories, map discoveries and outings.
3. A coherent system. Typography, spacing, controls, icons and states follow shared rules.
4. Comfortable density. Do not squeeze everything into one viewport; reveal detail progressively.
5. Mobile-first by design. Do not stretch a phone interface to fill desktop.
6. Locally grounded illustration. Use researched Lagos detail, not generic tropical clichés.
7. Honest information. Label estimates and source-backed details; never invent live functionality.
8. Accessible by default. Semantic controls, contrast, keyboard access, safe touch targets and reduced motion.
9. No false functionality. The current map is illustration-coordinate based, not accurate cartography.

## Audiences and needs
- **Undecided explorer:** discover something matching mood, time, interests and spend.
- **Neighbourhood wanderer:** pan around a lively illustrated city and find places worth opening.
- **Lightweight planner:** assemble an outing, swap a stop or shorten the plan.
- **Memory keeper:** save places/plans and record visits without mandatory signup.

## Goals and non-goals
Goals: distinctive visual identity; clear navigation; useful search and discovery; map exploration; lightweight planning; device-local saves; open-ended browsing; reliable responsive behaviour.
Not in scope without integrations: live routing, traffic, GPS accuracy, open-now status, live events, bookings, payments, public reviews, cross-device sync or mandatory accounts.

## Primary information architecture
- **For you:** editorial welcome, search, mood entry points and varied discoveries.
- **Explore:** unobstructed illustrated map, search, filters, zoom/recenter and contextual place sheet.
- **Plan:** optional preferences and a clear itinerary with honest estimates.
- **Saved:** places and plans saved for later.
- **Journal:** places the visitor has marked as visited.

Persistent bottom navigation must remain visible and usable on every mobile destination, including Explore. Account for safe areas and keep content clear of the navigation.

## Journey contracts
### First visit
Show one clear editorial anchor, a useful first action, easy-to-find search and a limited set of varied discoveries. Each item leads to a meaningful next step.

### Explore
Open directly to the city illustration with only essential controls. No permanent sheet, tray or title banner. Selecting a real marker opens a bottom sheet without changing primary destination. Selecting another marker updates the same sheet. Closing it preserves map position, zoom and filters. The bottom navigation stays visible.

### Plan
Ask only for useful optional constraints. Results must reflect the available dataset, show ordered stops, label spend/time as estimates where appropriate, and support swap/shorten without resetting unrelated choices.

### Save and remember
Actions update visibly. Saved items and visits persist on the same device. Empty states offer a next step and never resemble a broken screen.

## Screen requirements
- **For you:** one dominant introduction, readable search, intentional editorial variety, no long stack of identical cards.
- **Search:** supports known place names, categories and neighbourhood terms; clear no-result state; no unsupported proximity claims.
- **Map:** distinct scenes and landmarks; fixed controls separate from the pannable world; real interactive markers; non-map list alternative.
- **Place detail:** name, category, neighbourhood, useful description, source/address where available, caveats and clear actions.
- **Plan:** grouped choices, clear selected states, readable itinerary, honest estimates and functional remix/swap.
- **Saved/Journal:** distinguish saved from visited; populated and empty states; device-local limitation clear.
- **Desktop:** deliberate phone hand-off page, not a stretched mobile dashboard. No fake QR code; any QR code must resolve to the actual product URL.

## Release-blocking requirements
No overlapping or clipped content, crushed controls, inconsistent icon packs, emoji, heavy outlines, raised/neumorphic buttons, offset shadows, primitive placeholder map scenes, dead controls, trapped navigation, map gesture conflicts, inaccessible focus, or unsupported live-data claims.

## Trust and limitations
The local dataset is a small starter collection, not a complete or live Lagos directory. Map geometry is illustrative. Opening hours and prices can change. Saves and visit history are device-local. See CONTENT_GUIDE.md.

## Delivery order
1. Freeze UI polish and audit every screen against this document.
2. Approve design tokens, typography, spacing, icons and component states.
3. Rebuild the shared shell and navigation.
4. Rebuild each primary screen against its contract.
5. Rework map art and map interaction as separate workstreams.
6. Run QA at all required widths and interaction modes.
7. Verify the exact deployment commit and environment before calling anything released.

See DESIGN_SYSTEM.md, ICON_SYSTEM.md, MOTION.md, ARCHITECTURE.md, CONTENT_GUIDE.md and QA_PLAN.md for implementation rules.
