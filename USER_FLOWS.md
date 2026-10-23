# Outsideish User Flows

This document records established flows and expected behaviour. It does not add unapproved visual styling or assume every flow is already implemented.

## 1. First visit and guest browsing
**Entry:** visitor opens Outsideish in a mobile browser or installed PWA.

1. Load the app entry point.
2. Show discovery and access to search/Explore without an account gate.
3. Visitor chooses browsing, search, a mood-led entry or Explore.
4. Keep navigation clear so the visitor can return to discovery.

**Success:** visitor can begin exploring immediately.

**Failure:** if discovery data is unavailable, explain the state and offer working alternatives. Do not show a blank screen or fabricate content.

## 2. Search
1. Visitor searches for a place, neighbourhood, interest or experience.
2. Match against the supported available data.
3. Show matching results.
4. Visitor opens a result and can continue to connected content or actions where implemented.
5. Visitor can clear/revise the query or use a no-results suggestion.

**Success:** the visitor reaches relevant content without being forced through planning preferences. Search must not imply unsupported live web search or geographic proximity.

## 3. Mood-led discovery and “Surprise me”
1. Visitor chooses a mood or “Surprise me”.
2. Optionally provide time, budget, interests and starting neighbourhood.
3. Show adventure ideas based on the data and logic actually implemented.
4. Visitor opens an idea to inspect its stops.
5. Visitor adapts it or explores its places on the map.

**Alternatives:** skip all preferences, change a preference, or open a single place rather than a full adventure.

**Success:** a useful starting point is available without a mandatory questionnaire.

## 4. Inspect and adapt an adventure
1. Visitor reviews an adventure and its ordered stops.
2. Visitor can understand why the stops are grouped using available content.
3. Visitor swaps a stop, shortens/remixes, saves/shares or opens its places on the map where those actions are implemented.
4. A changed stop preserves unrelated preferences and keeps the plan understandable.

If no exact match is available, show the closest honest alternative or explain the limitation.

## 5. Explore the map
1. Visitor opens Explore.
2. The illustrated map appears without a persistent place sheet or discovery tray.
3. Visitor pans/zooms, searches, filters or selects an interactive place.
4. Selecting a place opens a contextual bottom sheet while remaining in Explore.
5. Selecting another place updates the same sheet.
6. Closing the sheet preserves map position and zoom.
7. Visitor continues exploring or uses primary navigation to leave.

**Alternatives:** search from the map, use filters, access an accessible list alternative, or follow a related collection/story/adventure.

**Success:** the map supports open-ended exploration and never traps the visitor. Illustration coordinates must not be used to imply real distances or routes.

## 6. Save a place or plan
1. Visitor chooses Save.
2. App performs the save using its actual persistence mechanism.
3. App confirms success only after state is saved.
4. Item becomes available in Saved.
5. Visitor reopens it.

If persistence fails, show an error rather than a false saved state. Communicate local-only storage where applicable.

## 7. Mark visited and use Journal
1. Visitor marks a place as visited.
2. The app updates the state after success.
3. The item appears in Visited/Journal.
4. The record remains available according to the actual persistence model.

Visited and saved are different intentions and must remain distinct.

## 8. Share a discovery
1. Visitor chooses Share.
2. App invokes an implemented native/browser share mechanism or copy-link fallback.
3. Confirm the action only if supported and successful.
4. If unavailable, provide the fallback or explain the limitation.

No dead controls and no false success states.

## 9. Install and use as a PWA
1. Visitor opens the web app in a supported browser.
2. Manifest metadata and referenced icons load.
3. The browser-supported install flow is available where supported; ordinary browser use remains available.
4. Visitor launches the installed app and uses primary navigation.
5. Repeat launch reuses cached app-shell resources according to the service-worker strategy.
6. Offline use shows only content actually available locally and explains unavailable features.
7. After an update, the app does not mix incompatible HTML/CSS/JavaScript/assets.

**Success:** installability, repeat launch, update and offline behaviour are tested on target browsers.

## Flow invariants
- Initial exploration does not require signup.
- Optional planning preferences remain optional.
- Search, feed, map, places and adventures connect where relevant.
- Map place details do not push the visitor to a new primary destination.
- Closing the map sheet preserves map position and zoom.
- Save/visited actions do not report false success.
- Local data is not described as cloud-synced.
- Cached UI is not described as live venue data.
