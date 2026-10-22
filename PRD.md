# Outsideish: Product Requirements Document

**Document status:** Product direction and implementation specification  
**Product:** Outsideish  
**Initial market:** Lagos, Nigeria  
**Primary platform:** Mobile-first progressive web app (PWA)  
**Product promise:** Find something worth going outside for, then keep discovering.

## 1. Product summary

Outsideish is an illustrated city-discovery companion for people who want to do something with their free time but do not necessarily have a plan. It helps people browse places, follow neighbourhood stories, build small outings around their mood, time and budget, and keep a personal record of what they discover.

Outsideish should feel less like a directory and more like wandering through a city with a curious local friend. The experience is visual, editorial, playful and open-ended. A discovery should lead naturally to another discovery.

The first city experience is Lagos. The product should be designed so additional cities can be introduced later without rebuilding the core experience.

## 2. Problem and opportunity

People often want to go out but face one or more frictions: they cannot think of somewhere to go, search results are too transactional, planning takes too much effort, useful local context is scattered, and recommendations rarely account for their mood, available time or spend.

Generic maps show where things are. Generic lists make people compare options. Outsideish should help people imagine a day, explore the city and decide what feels right.

## 3. Vision and principles

### Vision
Make it easier to have a good day outside, one small discovery at a time.

### Product principles
1. **Wander, do not dead-end.** Every place, collection and story should create a next step.
2. **The city is the interface.** The illustrated map is a primary browsing surface, not a decorative asset.
3. **Editorial, not generic.** Use authored point of view, specific local detail, wit and visual storytelling.
4. **Useful before clever.** Address, hours, price caveats and source links matter as much as the illustration.
5. **Low commitment.** No account or lengthy onboarding is required to browse, plan or save locally.
6. **Honest about certainty.** Distinguish verified source information, editorial suggestions, estimates and information that needs checking.
7. **Mobile-first, not mobile-only by accident.** Make a deliberate platform decision rather than stretching a phone UI across desktop.
8. **Accessible by default.** Motion, colour and touch interactions must not exclude users.

## 4. Target users and jobs to be done

### Primary: The undecided explorer
Has free time and wants an interesting outing without doing an hour of research.
- Job: “Help me find something that fits the kind of day I want.”
- Needs: Surprise me, mood filters, time and budget controls, clear next steps.

### Secondary: The neighbourhood wanderer
Likes exploring places nearby and following interesting streets, cafés, galleries, bookstores and small cultural stops.
- Job: “Show me what I might have missed around here.”
- Needs: Pan-and-zoom map, neighbourhood context, layered place details, nearby discovery.

### Secondary: The thoughtful planner
Wants a simple outing with a friend, date, visiting relative or solo afternoon.
- Job: “Help me make a plan without overplanning.”
- Needs: Multi-stop itineraries, time/spend estimates, swap and shorten actions, shareable plans.

### Secondary: The memory keeper
Wants to remember places visited and ideas saved for later.
- Job: “Keep my little city story in one place.”
- Needs: Saved places, saved plans, visit log and optional name personalisation.

## 5. Goals and non-goals

### Goals
- Build a visually distinctive and memorable city-discovery experience.
- Make browsing feel effectively continuous, with useful routes to more content.
- Make the map interactive, explorable and legible on mobile.
- Generate useful starter itineraries from a few lightweight preferences.
- Allow guest browsing and device-local saves.
- Establish a trustworthy content model for places, collections and stories.
- Support an installable PWA with offline shell behaviour.
- Provide a coherent mobile experience and an intentional desktop decision.

### Non-goals for the current prototype
- Live turn-by-turn navigation or traffic-aware routing.
- Claims about real-time crowd levels, open-now status or live event feeds without a connected source.
- User-generated public reviews, social feeds or moderation systems.
- Mandatory authentication, subscriptions or payments.
- A full booking or ticketing transaction.
- Pretending illustrative map geometry is geographically exact.

## 6. Experience architecture

Primary navigation:
- **For you:** A welcoming editorial feed, search, mood shortcuts and continue-discovering modules.
- **Explore:** Full-screen illustrated city map with pan, zoom, tappable places, neighbourhoods, filters and a contextual bottom sheet that appears only after selection.
- **Make a plan:** Optional preferences for time, mood, budget, starting neighbourhood and interests.
- **Saved:** Places and plans saved on the device.
- **My log:** Visited places and the user's personal city story.

Supporting destinations:
- Place detail
- Adventure / itinerary detail
- Collection detail
- Neighbourhood story
- Search results
- Optional guest profile/preferences
- Helpful empty, loading and error states

## 7. Core journeys

### Journey A: Start exploring immediately
1. Open Outsideish.
2. See a strong illustrated welcome and clear search.
3. Tap “Surprise me” or a mood shortcut.
4. Receive a varied set of places, stories or plans.
5. Open a result to see context, useful visit information and related discoveries.
6. Continue to a related place, collection, map location or plan.
7. Save or share if useful.

### Journey B: Make a little plan
1. Open “Make a plan”.
2. Choose time available.
3. Choose a mood.
4. Choose a spend preference.
5. Choose a starting neighbourhood or “Anywhere”.
6. Optionally select interests.
7. Submit and receive three meaningfully different outings.
8. Open one outing to see stops, why they fit, estimated time/spend, practical caveats and source links.
9. Swap a stop, shorten the outing, save, share or open the map.

### Journey C: Explore the map
1. Open Explore.
2. See the city as an illustrated, movable surface with visible neighbourhoods and distinct points of interest.
3. Pan by touch/mouse drag and zoom with pinch, wheel or controls.
4. Tap a place pin to open its contextual bottom sheet without leaving the map.
5. Save, mark visited, check its source, follow a related discovery, or dismiss the sheet and continue exploring.
6. Move to another neighbourhood and discover additional content.
7. Filters adjust visible categories without making the rest of the map unusable.
8. A “recenter” action returns the map to its initial city extent.

### Journey D: Remember a place
1. Open a place or plan.
2. Save it without signing in.
3. Find it under Saved.
4. Mark a place visited or add it to My log.
5. Return later to browse saved and visited discoveries.

### Journey E: Search
1. Enter a place, category, neighbourhood, mood or activity.
2. See relevant results with category and neighbourhood context.
3. Open a result, clear/refine the query, or continue browsing related content.
4. Empty results offer useful alternatives rather than a dead end.

## 8. Functional requirements

### 8.1 Home / For you
- Search supports place names, categories, neighbourhoods and editorial keywords.
- Mood shortcuts include at minimum Surprise me, Soft life, Chop life and Curious.
- Time and spend preferences are accessible without entering a full form.
- Discovery feed mixes places, curated collections, neighbourhood stories and outings.
- Feed supports “show me more” or progressive loading; it must not stop after the initial few cards.
- Content cards communicate a distinct editorial hook, category and place context.
- Repeated browsing should vary order or content where possible without randomising away relevance.
- A user can enter Explore or the planner from the home screen.

### 8.2 Explore map
- The map is the leading surface. On entry it shows the city itself with search, filters and essential map controls only.
- No persistent place tray, introductory map title, location badge or decorative sticker annotations.
- Use a geographically grounded map composition with rich, layered illustration: varied architecture, streets, storefronts, signage, plants, transport, people and neighbourhood details.
- Pan with touch/pointer drag, zoom with pinch/wheel and explicit controls, and provide recenter.
- Pins and map features stay at stable map-space positions.
- Selecting a place opens a contextual bottom sheet while remaining on the map. It must not navigate to the full detail screen.
- The sheet is hidden on initial map load, shows the selected place and useful factual/source caveats, and closes without resetting map position or zoom.
- Selecting another pin updates the existing sheet in place.
- Search submitted from the map opens the matching place in the same sheet. Search from the feed may still open the full place page.
- Filters update marker visibility and selected state without turning into a permanent drawer.
- Map geometry is illustrative until a reliable geographic data source is connected. Never imply exact distances, GPS, live traffic or route guidance unless implemented and supported.
- No emoji placeholders or primitive-shape city art.
### 8.3 Search and discovery
- Search is available from home and map.
- Support clear query, loading, no-results and error states.
- Results should include a next step: related category, neighbourhood, collection, or plan.
- Support discovery continuation: “near this”, “more like this”, “keep wandering”, and relevant collection links.
- Do not present fabricated live activity or opening statuses.

### 8.4 Planner and outings
- Preferences are optional and skippable.
- Inputs: available time, mood, spend band, starting neighbourhood, interests.
- Return three distinct outings when enough matching content exists; if data is limited, explain this and offer the closest alternatives.
- Each plan includes rationale, suggested stops, estimated time, spend caveat, neighbourhood and practical notes.
- “Surprise me” works in one tap.
- Users can remix, swap a stop, shorten the plan, save, share and open map.
- Spend figures are estimates only until sourced pricing is available.
- Travel times are not presented as live or precise without a routing integration.

### 8.5 Place details
- Include place name, type, neighbourhood, descriptive editorial copy, address, opening information when sourced, price caveat, source link and related content.
- Label data with an appropriate freshness/verification state.
- Give users useful actions: open source/maps, save, mark visited, share, explore nearby, add to plan where supported.
- Unknown information is stated plainly rather than filled with invented specifics.

### 8.6 Collections and neighbourhood stories
- Curated collections group places by a meaningful theme, not only a category.
- Neighbourhood stories give a sense of place and connect to specific discoverable places.
- Both surfaces include onward paths to related collections, places and plans.
- Content should be expandable over time through a consistent content schema.

### 8.7 Saved and personal log
- Guests can save/unsave places and plans on the current device.
- Saved view has useful tabs and empty states with routes back to Explore and discovery.
- Users can mark a place visited or add a visit manually.
- Personal log shows visited count and chronology.
- Local data is device/browser-specific in this phase; communicate this clearly.
- No authentication is required in the current prototype.

### 8.8 PWA and resilience
- App has a valid manifest, app icon and installable display mode.
- Cache the app shell and required static assets.
- If offline, make clear which parts are available and which require a connection.
- Do not silently present stale live information as current.
- Service-worker cache version must be bumped when shell assets change.

### 8.9 Desktop policy
- Desktop is a deliberate product decision, not an accidental stretched layout.
- Preferred approach: preserve useful desktop access where it can be made coherent, with a spacious map/content composition.
- If the illustrated map cannot be made genuinely usable on desktop within the implementation scope, show a designed mobile-first interstitial with a QR/deep link only if that link can be generated reliably, a concise explanation, and useful preview content. Never show a blank or broken layout.
- “Best experienced on mobile” is a recommendation, not a misleading claim that the app is unavailable on web unless web access is intentionally disabled.
- No separate Vercel project is to be created for this redesign.

## 9. Visual direction

### Desired character
An immersive, richly illustrated and geographically grounded city, expressed through a contemporary editorial interface. The city is the main character, not a background behind generic app cards.

### Visual principles
- Illustrate architecture, storefronts, streets, plants, public space, transport and everyday city life with authored detail, varied silhouettes, foreground/midground/background and consistent perspective.
- Avoid primitive-shape scenes, emoji placeholders, neumorphism, neubrutalism, heavy outlines around every control, offset-shadow buttons, pervasive floating controls, generic dashboards and repeated identical cards.
- Use varied editorial compositions for feed content.
- Keep map search and filters quiet, compact and readable.
- The map opens unobstructed. No persistent place sheet or introductory map label.
- Use expressive display typography and readable UI text; avoid tiny all-caps labels as the main hierarchy.
- No emojis in app UI or illustration.
- Mobile is primary; desktop remains intentional and should encourage phone use for the fullest map experience.
## 10. Motion and interaction principles
- Map drag follows the hand directly; do not animate against pointer movement.
- Use short, purposeful transitions for zoom, recenter, selection and sheet motion.
- Pins do not bounce continuously.
- Selecting a map pin opens a bottom sheet in place. Dismissing it preserves map position and zoom.
- Selecting another pin updates the open sheet without screen navigation.
- Provide pressed, selected, focus, loading, success, empty and error states.
- Respect `prefers-reduced-motion`; never convey essential information only through motion.
- Environmental motion may be added sparingly to non-interactive artwork after performance and accessibility testing.
- Sound is a future, opt-in enhancement only. No autoplay; default off; explicit mute control; no essential information delivered only through sound.
- Full specification lives in [MOTION.md](MOTION.md).
## 11. Content model

### Place
- id, name, slug
- category and tags
- neighbourhood and city
- address and optional coordinates
- short hook and long description
- cover/illustration asset
- source URL and source label
- opening information and source/checked date where known
- price band, price note and confidence
- mood tags, interest tags
- related place IDs, collection IDs and plan IDs
- data status: verified, needs-checking, editorial, placeholder
- last reviewed timestamp

### Adventure / plan
- id, title, editorial hook, mood
- time range and spend band (with estimate disclaimer)
- starting neighbourhood and area coverage
- ordered stops with rationale
- practical notes and limitations
- related collections and alternate stops
- source links for factual venue details

### Collection
- id, title, editorial intro, theme, cover asset
- ordered place/story/plan references
- neighbourhood and mood tags
- related collections

### Neighbourhood story
- id, name, editorial description, illustrated map extent
- places, landmarks and collections
- local context reviewed for accuracy

## 12. Data quality and trust
- Real-world venue details can change. Every factual field should have a source or be marked as unverified.
- Use official venue sources when possible, then trustworthy map/listing sources.
- “Open now”, current events, prices, crowd levels, transport estimates and live route data require appropriate live integrations before being presented as live.
- Show “check before you go” where the data can become stale.
- Keep editorial recommendations separate from verified venue facts.
- Do not use a map illustration to imply exact distance or directions unless calibrated to real coordinates.

## 13. Accessibility
- Meet WCAG 2.2 AA as a target for contrast, keyboard access, labels and focus visibility.
- Provide semantic landmarks, button names and form labels.
- Interactive map controls must have text/accessible labels and non-map alternatives.
- Aim for at least 44 × 44 CSS px touch targets on primary mobile actions.
- Avoid colour-only status indication.
- Honour reduced motion and browser zoom.
- Use descriptive alt text for meaningful illustrations; decorative art should be hidden from assistive technology.

## 14. Privacy and security
- Browsing should not require an account.
- Saved and visited information is stored locally in the current prototype.
- Explain that local saves do not sync between devices and may be lost if browser data is cleared.
- Request location permission only when a real location-dependent feature exists and the benefit is clear.
- Never imply the app is tracking GPS when it is not.
- External source links open safely in a new context.
- Avoid collecting unnecessary personal information.

## 15. Success metrics

### North-star signal
**Meaningful discoveries per active explorer session**, measured as place/detail opens followed by a useful action (save, map continuation, related item, plan open, share or visit log).

### Supporting measures
- Search-to-detail open rate.
- Map pin interaction rate.
- Percentage of sessions that continue to a second discovery.
- Planner completion and plan-open rates.
- Save rate and return-to-saved rate.
- Map interactions per session, with attention to usability rather than raw gesture count.
- PWA installation and repeat visit rate.
- Data freshness and source coverage.
- Accessibility defects, runtime errors and layout overflow incidents.

Metrics should be added only with an appropriate privacy-respecting analytics approach; do not invent current numbers.

## 16. Release stages

### Phase 1: Interaction foundation
- Refine art direction and typography.
- Improve map movement, zoom, selection, filters and recenter.
- Improve navigation, responsive composition and mobile ergonomics.
- Establish place/plan/collection/story schemas and accurate labels.
- Write product and design documentation.

### Phase 2: Continuous discovery
- Expand curated place content and introduce collections/neighbourhood stories.
- Add related discovery modules and progressive loading.
- Improve planner matching, stop swapping and plan shortening.
- Add search empty/loading/error states.

### Phase 3: Trustworthy real-world data
- Review place data and sources.
- Add geographic coordinates and a proper map layer/provider if desired.
- Add explicit source/freshness labels.
- Integrate live opening data, event listings or routing only after provider evaluation.

### Phase 4: Personal continuity
- Improve visited log and local saved experience.
- Evaluate optional account/sync only if it solves a real user need.
- Expand to another city only after the Lagos experience has adequate quality and coverage.

## 17. Acceptance criteria for the next design iteration
- [ ] Home, map and detail screens feel like one intentionally art-directed product.
- [ ] Map can be dragged, zoomed and reset on touch and desktop.
- [ ] Selecting a map pin opens the correct place; map list selection stays in sync.
- [ ] There are clear ways to keep discovering after opening a place or finishing a plan.
- [ ] Feed and map are not limited to three fixed discovery items as a product pattern.
- [ ] Map and place information clearly distinguish editorial art from geographic precision.
- [ ] Map opens without a permanent place tray or map-title badge.
- [ ] Pin tap opens an in-place bottom sheet; close preserves map pan and zoom.
- [ ] No emoji placeholder art; no continuous pin bobbing; no autoplay sound.
- [ ] Desktop either works as a coherent app or has a deliberate mobile-first interstitial.
- [ ] No accidental horizontal overflow at common mobile widths.
- [ ] All controls have usable focus, selected and pressed states.
- [ ] Reduced-motion preference is honoured.
- [ ] No false claims about live traffic, open-now, event or routing information.
- [ ] The PWA shell cache is updated and checked.
- [ ] Product, visual system, motion and technical notes are maintained in Markdown.

## 18. Open questions
- Which Lagos neighbourhoods should receive full editorial coverage first?
- What reliable sources or APIs can support venue updates and coordinates?
- Should desktop retain full exploration or move to a mobile-first companion page after usability testing?
- Which illustration production approach best balances bespoke quality, map readability and content expansion?
- What privacy-respecting analytics, if any, should be used after the prototype?
## 19. Continuous discovery specification

### Product requirement
Discovery is a continuing activity, not a one-time recommendation result. A person should be able to move between the home feed, map, place details, collections and outing plans without encountering a dead end or being forced to restart.

### Discovery surfaces
1. **For you feed:** A mixed, editorial stream of places, outing ideas, collections, neighbourhood notes and seasonal/editorial features. Use a deliberate rhythm of formats instead of repeating an identical card grid.
2. **Explore map:** A spatial way to browse neighbourhoods and places. Map movement, place selection and the list of visible discoveries should remain connected.
3. **Search:** Search place names, neighbourhoods, categories, moods and editorial collections. Search results should offer close alternatives when there is no exact match.
4. **Outing planner:** Produces a small set of useful starting plans from time, spend, mood, interests and starting area. It is an entry point into discovery, not a separate dead-end tool.
5. **Related discoveries:** Every place and outing should lead to related places, relevant collections, a neighbourhood story or a nearby next idea.

### Feed behaviour
- The feed starts with a useful first batch and adds more content as the visitor approaches the end of the current batch.
- A visible “Keep wandering” action remains available as a manual fallback.
- If the current local content set is exhausted, the feed may revisit existing editorial items in a newly mixed order. Repeated items must not appear back-to-back, and the interface must not imply that new places were fetched when they were not.
- As the content library grows, the feed should request the next page from the content source rather than reshuffling the entire catalogue.
- Preserve the visitor's position when opening a detail view and returning to the feed.
- Feed state should not jump to the top when the user opens a place and returns.
- Include a clear loading state when new content is being fetched. If loading fails, keep already-rendered content available and offer retry.
- Do not use random ordering as the sole recommendation strategy. Apply relevance, constraints, editorial priority, diversity and freshness.
- A limited starter dataset is a prototype limitation. It must not be represented as a complete or live Lagos directory.

### Content variety and cadence
The long-term feed should support:
- Place spotlights
- Curated collections
- Neighbourhood field notes
- Outing plans
- Short local guides
- “If you liked this…” recommendations
- Budget-conscious and low-commitment ideas
- Art, food, books, music, public space, culture, learning and unexpected discoveries
- Timely events only when a trustworthy, current source is integrated

## 20. Map interaction and cartography requirements

### Map model
The initial map is an illustrated, editorial city map. It communicates neighbourhood atmosphere and helps visitors discover content. It is not a scale-accurate street map and must not imply turn-by-turn directions, exact distances or live location.

### Required interactions
- Drag/pan the map with touch and mouse.
- Zoom in and out with visible controls; support wheel zoom on desktop.
- Recenter to the default map view.
- Select a place marker and open its detail view.
- Filter visible places by supported categories.
- Search from the map.
- Select a map feature to open an in-place contextual bottom sheet. No persistent discovery list covers the map.
- Keep map controls anchored to the viewport while the map artwork moves.
- Prevent a drag gesture from accidentally activating a place marker.
- Provide accessible controls in addition to gestures.
- Preserve selected place and filter state when moving between map and detail.
- At useful zoom levels, keep markers identifiable and tappable. Do not let illustration detail obscure essential place markers.

### Map visual hierarchy
1. Water, parks and land masses
2. Major streets and connectors
3. Neighbourhood names
4. Distinctive blocks, buildings and street details
5. Place markers and selected-place state
6. Essential controls and selection-triggered place sheet

The city illustration should use recognizable architectural variation: mixed rooflines, balconies, shop fronts, signs, awnings, doors, window groupings, trees with varied silhouettes, people, street vendors and vehicles. Avoid relying on isolated triangles, circles or emoji to communicate a whole building or street scene. Keep decorative detail subordinate to map legibility.

### Geographic truth and future migration
- Current map coordinates are illustration coordinates, not latitude/longitude.
- Do not calculate real walking distance, nearby status or travel duration from illustration coordinates.
- A future geographically accurate map should use a dedicated map/data adapter with real coordinates and a suitable mapping provider.
- Map provider, tiles, geocoding, route calculations, attribution and cost limits require a separate technical decision before implementation.
- If a place has not been geocoded, it can still appear in an editorial collection but must not be represented as precisely located.

## 21. Platform strategy

### Mobile
Mobile is the primary product surface. The design should support one-handed browsing, safe-area insets, bottom navigation, clear tap targets, map gestures, compact but legible text and bottom sheets that respect the keyboard and device height.

### Desktop and wider screens
Desktop remains supported through a deliberately composed companion layout, not a stretched mobile canvas. It should have:
- A restrained content width and a consistent grid
- Clear hierarchy between the discovery feed and supporting controls
- A map canvas that uses the available viewport intentionally
- A pinned or docked discovery panel that does not scatter content around the screen
- Fixed map controls and a clear selected-place panel
- Comfortable text sizes and keyboard navigation

Do not show a generic “not available on web” screen solely because the map is illustrated. The illustrated map can work on desktop when its layout, pan/zoom controls and discovery panel are designed for that viewport. Reconsider mobile-only access only if usability testing shows desktop creates more confusion than value.

## 22. Personalisation and outing planning

### Inputs
- Mood or energy: soft/slow, food-focused, curious/cultural, outdoors, social, unexpected
- Available time
- Spend preference
- Starting neighbourhood or preferred area
- Interests
- Optional mobility/access needs when reliable content data supports them

### Recommendation rules
- Return a small, scannable set of distinct suggestions.
- Explain why each suggestion fits the selected constraints.
- Respect selected time and spend constraints where the underlying data supports a reasonable estimate.
- Mark uncertain spend and duration as estimates.
- Do not imply that a plan has checked live traffic, opening status, event schedules or route conditions unless it has.
- Offer “swap this stop”, “shorten this plan”, “show another idea”, “save” and “open on map” actions.
- If no result matches all constraints, state the trade-off and offer the nearest alternatives rather than silently ignoring the constraints.

## 23. Content and data operations

Every production place record should support, where applicable:
- Stable ID, public name, category and descriptive editorial copy
- Address and neighbourhood
- Latitude/longitude only when sourced and geocoded
- Official website and source references
- Source type, source URL, date checked and confidence/status
- Opening hours with day-specific exceptions where known
- Price information with currency and whether it is exact, a range or an estimate
- Tags for mood, interest, access and outing suitability
- Image/illustration rights and attribution requirements
- Last updated timestamp and editorial review status

A source link alone is not proof that every displayed fact is current. Data should be reviewed periodically. Stale hours, prices or event listings should be labelled, suppressed or rechecked according to a documented freshness policy.

## 24. States and resilience

Each major surface must define:
- Initial loading state
- Populated state
- Empty state
- Recoverable error state
- Offline or stale-data state where applicable
- Selected, saved and visited states
- Keyboard-focus and pressed states
- Reduced-motion state

The app shell should remain usable when the network is unavailable after installation. Do not imply that all place content is fresh merely because the PWA shell loads offline. Local saves and visit history should remain available on the device that created them.

## 25. Analytics and evaluation

Potential privacy-conscious events:
- Feed batch viewed
- Discovery opened
- Related discovery opened
- Map panned/zoomed/filtered
- Search submitted and result selected
- Planner completed and plan selected
- Place saved or marked visited
- Source link opened
- Return visit

Do not collect precise location, names or sensitive personal details by default. Analytics must be disclosed appropriately and should avoid storing raw search text if it could contain personal information.

### Evaluation questions
- Can a first-time visitor find a plausible activity without creating an account?
- Do people continue from one discovery to another?
- Can a person tell whether a map is illustrative or geographically accurate?
- Can visitors understand price and opening-hour uncertainty?
- Does the desktop experience feel intentionally composed?
- Can a person return from a place detail without losing their browsing position?

## 26. Updated release priorities

### P0: Product and interaction foundation
- Replace generic/neumorphic presentation with the Outsideish editorial illustration system.
- Make mobile and desktop layouts deliberate and consistent.
- Improve map illustration detail and hierarchy.
- Verify pan, zoom, recenter, marker selection, filters, search and return navigation.
- Ensure continuous feed browsing without a dead-end state.
- Keep copy honest about data coverage, map precision and live integrations.
- Finalise PRD, design system, motion and QA documentation.

### P1: Content depth
- Expand the reviewed Lagos place library and add collections and neighbourhood stories.
- Introduce related discovery links and a richer editorial feed cadence.
- Improve search with categories, neighbourhoods, synonyms and useful fallback results.
- Add a content freshness and review workflow.

### P2: Real-world utility
- Evaluate a coordinate-aware map provider and geocoding.
- Add reliable route links and real directions via an external maps app or approved provider.
- Add current events only after source coverage, update frequency and attribution are agreed.
- Add opening-hour and price verification workflows.

### P3: Personal continuity
- Optional account and cross-device sync.
- Preference management and more useful recommendations based on explicit choices.
- Shareable outing plans and collaborative planning, if validated.

## 27. Definition of done for the visual refresh
- The design does not use neumorphism as its primary visual language.
- Screens use purposeful composition, hierarchy and varied content formats.
- The map contains architectural and street-life detail beyond primitive geometric silhouettes.
- Desktop layouts are aligned to a deliberate grid and do not overflow or scatter.
- Mobile layouts have no horizontal overflow and preserve safe-area spacing.
- The feed continues to append content and retains manual continuation.
- Map controls remain reachable while panning and zooming.
- Reduced-motion preferences are respected.
- Search, detail, save, visit, planner and navigation flows continue to work after the styling changes.
- Automated browser checks cover narrow mobile, standard mobile and desktop widths.
- Any remaining limitations are documented honestly.


## Visual and navigation acceptance criteria

- The UI uses a flat editorial system. No drop shadows, offset shadows, elevated buttons, heavy outlines, generic dashboards or repetitive identical cards.
- No emoji are used as interface decoration or as a substitute for authored illustration.
- The city map is the leading discovery surface and uses layered, varied, locally grounded illustration rather than primitive-shape diagrams.
- Main navigation remains visible and usable while the map is open on mobile and desktop.
- Search and filters remain available above the map. No discovery tray or place panel is shown by default.
- Selecting a pin opens an in-place bottom sheet. Closing it preserves the map state and location. Navigation remains accessible even while the sheet is open.
- Controls provide clear touch targets and visible keyboard focus without shadows or raised styling.
