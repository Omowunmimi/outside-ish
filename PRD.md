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
- **Explore:** Full-screen illustrated city map with pan, zoom, tappable places, neighbourhoods, filters and a discovery tray.
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
4. Tap a place pin to see a compact preview.
5. Open full detail, save, or continue exploring nearby.
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
- Map fills the available viewport and remains usable with one hand on mobile.
- Pan via pointer/touch drag; zoom via pinch/wheel and explicit +/- controls; provide recenter/reset.
- Place pins are individually tappable and keyboard-focusable where feasible.
- Selected place is visually distinct and opens a preview sheet/tray.
- Map tray can expand/collapse and list places in the current curated area.
- Search and category filters update visible map content and list content together.
- Selecting a list result highlights/centres the corresponding pin.
- Neighbourhood labels, roads, landmarks, water and illustrated details provide orientation.
- Respect safe areas, reduced-motion settings and touch target sizing.
- Current map is editorial/illustrative, not a claim of exact cartography. Do not imply GPS, routing or traffic features unless implemented and disclosed.
- Map content should progressively reveal more places as users browse/zoom or request more, not present only three fixed points.
- If true geographic positioning is added later, map geometry and place coordinates must come from a trustworthy source.

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
An illustrated editorial field guide to Lagos: playful, observant, tactile, colourful and locally specific. It should feel art-directed, not like a generic dashboard assembled from rounded cards.

### Visual principles
- Use an intentional palette with strong contrast, ink-like outlines, paper textures and occasional bright accents.
- Use varied compositions: editorial panels, map fragments, labels, hand-drawn annotations, stacked paper, large illustrations and asymmetric layouts.
- Avoid excessive beige surfaces, repeated pill shapes, repetitive equal-sized cards, excessive borders and neumorphism.
- Avoid house icons made from generic triangle/rectangle combinations as the primary illustration language.
- Illustrations should contain intentional architecture, storefront signs, windows, balconies, awnings, street furniture, foliage, people, vehicles and foreground/background layers.
- Use a consistent illustration system and custom SVG or authored artwork where practical.
- Typography should combine a legible UI sans with a characterful editorial display face; avoid tiny all-caps labels as the main hierarchy.
- Microcopy can be warm and witty with Nigerian context, but must remain clear and not force slang into every line.

## 10. Motion and interaction principles
- Motion communicates cause and effect: pins respond to selection, sheets settle into place, map movement follows the hand, and new content enters without disorienting the user.
- Use restrained easing and spring-like transitions; avoid perpetual animation that distracts.
- Provide pressed, focused, selected, loading, success, empty and error states.
- Respect `prefers-reduced-motion`.
- Do not make essential information available only through animation.
- Full motion specification lives in [MOTION.md](MOTION.md).

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
