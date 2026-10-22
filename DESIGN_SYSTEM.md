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
1. Neighbourhood name and broad orientation.
2. Primary roads and water/green spaces.
3. Distinct landmarks and illustrated building blocks.
4. Place markers.
5. Selected place and map controls.
6. Editorial annotation.

Place pins should have category shape/colour distinctions, a selected state, and sufficient touch area. A selected place should be unmistakable without covering its context.

## Component guidance
- **Primary action:** high contrast and clear verb, used sparingly.
- **Secondary action:** quiet outline or text action.
- **Discovery item:** may be a horizontal editorial row, full-bleed illustrated panel, list item, map preview or image-led card depending on content.
- **Filter:** accessible toggle/chip with selected state, not decorative pill-only UI.
- **Bottom sheet:** map companion panel that can collapse, expand and preserve access to map gestures.
- **Place detail:** strong title and illustration first, then location facts, editorial context, practical notes, source and onward discovery.
- **Empty state:** explains why it is empty and offers a meaningful next action.
- **Loading state:** use a small skeleton or map shimmer only when a real asynchronous operation is pending.

## Responsive rules
### Mobile
- Treat the app as a full-screen native-feeling experience.
- Bottom navigation remains reachable and respects safe-area insets.
- Keep map controls within thumb reach, avoid covering important pins, and make the detail tray collapsible.
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
