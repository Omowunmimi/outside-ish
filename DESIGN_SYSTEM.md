# Outsideish Visual Design System

## Intent
Outsideish should feel like an illustrated Lagos field guide with the usability of a polished mobile app. The design is editorial, tactile, locally observant and colourful. It must not default to a generic neutral dashboard, neumorphic surfaces, or repeated rounded cards.

## Art direction
**Keywords:** illustrated field notes, Lagos street life, indie magazine, hand-painted signage, printed ephemera, warm wit, layered city scenes.

### Do
- Build compositions around illustration and editorial hierarchy.
- Mix large imagery, asymmetric panels, map details, typographic moments, annotations and concise factual modules.
- Use expressive but legible display typography and a quieter UI face.
- Use linework, print-like texture, layered shadows sparingly, and purposeful colour blocking.
- Give buildings and streets architectural character: varied rooflines, signs, doors, windows, awnings, balconies, utility poles, roadside trees, kiosks, people and vehicles.
- Make the map a legible composition with a clear hierarchy between roads, blocks, parks/water, neighbourhood names and places.

### Avoid
- Beige-on-beige as the default palette.
- Neumorphism, soft inset controls and generic glassmorphism.
- The same pill/card/button treatment on every screen.
- Empty geometric houses made from only a triangle and rectangle.
- Emoji as a substitute for custom illustration.
- Decorative labels that take more attention than content.
- Tiny all-caps text for core information.
- Artificial “live” labels on static editorial content.

## Colour tokens
The following palette is a starting system, not a requirement to use every colour on every screen.

| Token | Value | Use |
|---|---|---|
| Ink | `#242238` | Main text, outline, high-contrast elements |
| Lagoon | `#75BFC1` | Water, map highlights, calm accents |
| Hibiscus | `#F06B59` | Primary accent, key action moments |
| Mango | `#F5C84C` | Highlight, markers, playful contrast |
| Leaf | `#52785B` | Parks, foliage, success |
| Orchid | `#9B78C8` | Culture, secondary accent |
| Paper | `#FFF7E9` | Reading surfaces |
| Warm white | `#F8F1E7` | Main canvas when needed |
| Brick | `#B94B42` | Warning/error accents |
| Muted ink | `#665E6A` | Secondary text, only when contrast permits |

Use colour with hierarchy. Large surfaces should not all be the same warm neutral. Reserve saturated colours for purposeful moments and illustrations.

## Typography
- **Display:** Fraunces or a comparable expressive serif for editorial headlines and place-story titles.
- **UI:** DM Sans or a highly legible neutral sans for navigation, controls and body copy.
- **Utility:** DM Mono only for occasional coordinates, compact metadata or annotation; never for long reading.
- Use a clear scale: display, page title, section title, card title, body, supporting, metadata.
- Body text should generally be 14–17px on mobile for readable editorial content. Metadata should rarely drop below 11px.
- Keep line lengths comfortable and avoid all-caps as the only differentiation.

## Shape and surfaces
- Use a small set of radii with intent: compact controls, editorial panels, and occasional organic illustration masks.
- Use square or subtly rounded editorial panels where that supports the magazine feel; not every surface needs a pill or 24px radius.
- Borders should feel like ink or print rules, not decorative outlines around every element.
- Layering and shadows are allowed when they establish depth, but avoid a repeated soft-shadow system that makes everything float.

## Illustration language
### Principles
1. **Draw scenes, not symbols.** A venue should feel like a place, not a coloured tile with an emoji.
2. **Layer the world.** Background architecture, mid-ground street activity, foreground plants/people/vehicles and clear place markers.
3. **Add specificity.** Signage, window rhythm, balconies, awnings, shutters, roof details, street lights, market tables, kerbs and road markings create believable places.
4. **Use controlled imperfection.** Slight variation in line, scale and placement gives a human quality without sacrificing legibility.
5. **Respect local context.** Use Nigerian city details thoughtfully; avoid flattening Lagos into generic tropical iconography.
6. **Preserve function.** Pins and labels must remain legible at small sizes and high zoom.

### Illustration categories
- **City map:** broad neighbourhood composition, roads, blocks, water, parks, landmarks and clusters of individually identifiable venues.
- **Place vignette:** bespoke scene showing a storefront, gallery, bookshop, food spot or public space.
- **Editorial cover:** one strong visual metaphor or character scene, not a collage of generic icons.
- **Micro-illustration:** tiny supporting drawings for categories, empty states and action feedback.

### Asset requirements
- Prefer authored SVG for map assets, icons and scalable illustration.
- Keep SVG shapes grouped by semantic object to support future interaction.
- Use meaningful accessible descriptions for informative images; mark purely decorative SVG as hidden from assistive technology.
- Do not create a false claim of map scale or location accuracy through visual precision.

## Map visual hierarchy
1. The city illustration and its spatial relationships.
2. Neighbourhoods, landmarks and architecture.
3. Place markers and discoverable features.
4. Search, filters and essential controls.
5. The selected-place sheet, only after selection.

### Default map state
The map occupies the viewport. Search, filter and essential map controls are the only persistent overlays. Do not show a persistent discovery tray, “Illustrated Lagos” label, city badge or sticker annotations.

### Markers and selection
Markers are part of the illustration system, not emoji inside generic pins. They remain still when idle, have clear hit targets, and use a restrained pressed and selected state. Selection opens a bottom sheet without navigating away.

### Place bottom sheet
The sheet is hidden on initial load. It opens from the bottom only when a place is selected, shows concise editorial and practical details, and closes without changing map position or zoom. Selecting another place updates the sheet in place.

## Responsive rules
### Mobile
- Treat the app as a full-screen native-feeling experience. The map itself leads, with only search, filters and essential controls.
- Bottom navigation remains reachable and respects safe-area insets.
- Keep map controls within thumb reach. The place sheet is hidden until selection and should leave a substantial area of the city visible.
- Avoid dense multi-column card grids for core browsing.
- Keep primary touch targets around 44px or larger.

### Desktop
- Never simply scale the mobile layout up.
- Use a deliberate editorial grid and wider map/content composition if full exploration is supported.
- Ensure map interactions work with mouse, wheel and keyboard-accessible controls.
- If desktop exploration is intentionally deferred, provide a polished mobile-first explanation with a genuine path to open the app on a phone, not a broken desktop UI.

## Content tone
Warm, specific, observant and lightly witty. Nigerian expressions are welcome when they sound natural, not pasted into every sentence. Never let jokes obscure practical caveats, directions, prices or safety information.

## Quality bar
Before a screen is considered ready, review it at 360px, 390px, 768px, 1024px and 1440px widths. Check visual hierarchy, line breaks, touch targets, overflow, contrast, focus states and reduced motion. Review the screen as a composition, not just a list of components.
## 10. Updated visual direction: an illustrated city field guide

The interface should feel like an independent city magazine crossed with a lovingly drawn neighbourhood guide. It is expressive and playful, but still practical. Use print-like colour blocking, considered linework, display typography, small editorial annotations and illustrations that carry meaning.

### Core visual rules
- Avoid neumorphism, inset shadows, frosted panels and a stack of identical soft cards.
- Prefer crisp outlines, subtle offset print-like shadows, paper surfaces, saturated colour blocks and intentional asymmetry.
- Use hard-edged or lightly rounded geometry for the app UI. Reserve pill shapes for tags where they help scanning.
- Do not turn every action into a floating capsule.
- Use large, editorial serif type for selected headlines and a highly legible sans serif for interface text.
- Use hand-drawn details as supporting character, not as noise behind essential text.
- Every screen should have one primary focal point and a clear next action.

### Illustration construction
The illustration system should have three levels:
1. **Hero scenes:** composed street or neighbourhood scenes with foreground, middle ground and background, varied building silhouettes, human activity and a clear narrative.
2. **Map artwork:** repeated but varied architecture, roads, greenery, landmarks, local transport and street-life details. Decorative objects should remain subordinate to roads and place markers.
3. **Small spot illustrations:** bespoke object/scene drawings for empty states, category introductions and collection covers.

Buildings should not be represented only by a triangle roof and rectangle body. Use varied roof forms, parapets, balconies, railings, verandas, shutters, window rhythm, doors, signboards, awnings, utility lines, weathering and different heights. Add perspective cues and overlapping layers. People should have varied silhouettes, clothing shapes and purposeful poses. Trees should have organic silhouettes rather than repeated identical circles. Vehicles need windows, wheels, route/sign detail and a sense of direction.

### Map colour and legibility
- Water: lagoon/mint blues with subtle wave or current texture.
- Parks and planted areas: varied leaf greens with different tree shapes.
- Streets: light, high-contrast routes with a darker or warm edge; keep junctions clear.
- Buildings: a controlled mix of coral, mango, orchid, brick, teal and paper.
- Place markers: use a strong consistent outline and category cues. The selected marker must have a distinct shape, not only a colour change.
- Neighbourhood labels should be legible at the default zoom and should not collide with markers.
- Detail can increase at closer zoom levels, but road and marker hierarchy must remain stable.

### Layout and composition
- Mobile: one clear reading column, deliberate section rhythm, bottom navigation and a map sheet that does not hide essential controls.
- Desktop: use a defined max-width grid for the feed. For the map, use a full-height canvas with anchored controls and a docked discovery panel.
- Vary card aspect ratios and content treatments when the content warrants it. Do not make every item the same component.
- Align related content to shared edges. Avoid arbitrary gaps and isolated elements that feel dropped onto the page.
- Use colour to establish hierarchy and mood rather than decorating every element equally.

### Type hierarchy
- Display: expressive serif for hero headlines, collection titles and selected editorial moments.
- UI: neutral sans serif for body copy, forms, buttons and factual details.
- Metadata: compact but legible; do not reduce essential category, neighbourhood or trust labels to tiny all-caps text.
- Body copy should be comfortable to read on a small phone. Use line-height around 1.45–1.65 for longer descriptions.
- Keep headings concise and specific.

### Surface and shadow
Use a small, consistent set of surface treatments:
- Editorial paper surface with a crisp outline
- Saturated feature panel
- Quiet text-on-canvas section
- Docked map panel
- Bottom sheet for mobile actions
Offset shadows may be used to give selected controls a printed/sticker quality. Do not apply them indiscriminately to every surface.

### Component quality bar
A component is not approved because it is colourful. It must also have:
- A clear interaction affordance
- Hover, pressed, focus-visible, selected, disabled and loading states where relevant
- Adequate contrast
- A predictable spacing relationship to neighbouring elements
- Responsive behaviour that does not cause overflow
- Reduced-motion behaviour where animation is present

### Responsive platform decision
The product remains mobile-first but is not intentionally mobile-only. Desktop must have its own composition. If future research demonstrates that the map experience is substantially worse on desktop, a mobile-first notice can be tested as a product decision, not used as a substitute for responsive design.


## Visual direction update: flat editorial city world

The earlier bordered, offset-shadow, rounded-card treatment is rejected and must not return. Outsideish uses a flat, editorial visual language: warm paper ground, deep botanical green ink, vermilion accents, muted yellow and sage, strong typography, asymmetrical composition and generous open space. Controls are flat and quiet. Do not use drop shadows, offset shadows, elevated/floating buttons, heavy outlines, repeated dashboard cards, or pill controls as the default. Use thin rules, colour fields, type scale, illustration and spacing to establish hierarchy. Use varied editorial layouts rather than repeating identical tiles. No emoji as UI decoration or substitute illustration.

### City illustration

The map is an authored illustrated city environment, not a schematic diagram. Buildings should have varied silhouettes, layered facades, windows, balconies, signs, awnings, doorways and small street-level details. Roads should meander through coherent neighbourhood blocks. Include locally grounded street life, transport, trees, shopfronts and waterfront details. The artwork must feel composed and inhabited, not assembled from primitive rectangles and triangles. Pins sit within this world and remain legible without dominating it.

### Navigation and controls

The main navigation remains available while exploring the map. On mobile it sits above the bottom safe area and must never be hidden by the map view. Search and filter are flat, square-cornered controls. Place details appear in a contextual bottom sheet only after selecting a pin or place; dismissing it returns to the map.

## Full-reset visual direction

**Premise:** an illustrated field guide to going out, with the warmth of a neighbourhood publication and the curiosity of wandering through a real city. Not a dashboard, sticker UI, or toy interface.

**Palette:** warm field `#f2eddf`, paper `#faf7ed`, deep forest `#315b45`, ink `#263b32`, clay `#c75c43`, sun `#e6bd53`, and restrained leafy greens.

**Controls:** flat fills or transparent backgrounds; no elevation, drop shadows, offset shadows, heavy outlines, or neumorphic treatment. Active states use colour, typography, or a fine rule.

**Type and composition:** expressive serif headlines with compact sans-serif supporting text. Use asymmetry, varied image crops, breathing room, thin dividers, and editorial sequencing. Avoid repetitive all-caps labels, repeated cards, oversized marketing hero blocks, and dashboard grids.

**Illustration:** the city is the signature. Use layered streets with storefronts, balconies, plants, people, local transport, waterfront edges and visual discoveries. No emoji art or primitive roof/trees. Different crops are temporary scaffolding until a larger venue-specific illustration library exists.

**Mobile and desktop:** mobile is the full product, with five-item bottom navigation on the map. Desktop visitors receive a bespoke phone hand-off page.
