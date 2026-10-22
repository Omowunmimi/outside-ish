# Outsideish Design System

**Status:** Reset specification. These rules replace inconsistent one-off styling.

## Design objective
Expressive, locally grounded and illustrated, but never cramped or chaotic. Illustration creates personality; disciplined hierarchy and spacing make the product usable. Do not treat the current UI as an approved reference or layer more styling onto broken structure.

## Principles
- One dominant visual anchor and clear hierarchy per screen.
- Generous spacing and deliberate grouping; do not fill every gap with decoration.
- Variety in editorial content, consistency in repeated controls.
- Flat controls. No neumorphism, raised-button stacks, offset shadows or heavy outlines.
- Illustration supports content rather than obscuring it.
- One custom SVG icon family. No emoji, arbitrary Unicode symbols or mixed icon packs.
- Mobile-first composition; design at 390px before adapting to other widths.

## Colour tokens
| Token | Hex | Purpose |
|---|---|---|
| Ink | #24312B | Primary text |
| Forest | #315B45 | Primary action and selected navigation |
| Clay | #C75C43 | Secondary emphasis |
| Sun | #E6BD53 | Small highlights |
| Lagoon | #7BB8B3 | Water and calm accent |
| Leaf | #71866A | Parks and foliage |
| Orchid | #9277A8 | Occasional category accent |
| Paper | #FAF7ED | Reading surface |
| Field | #F2EDE1 | Main canvas |
| White | #FFFFFF | High-clarity surface |
| Muted ink | #626A63 | Secondary text if contrast passes |
| Rule | #D9D4C8 | Subtle divider |
| Error | #A83E36 | Error/destructive state |

Do not invent one-off colours without a reason. Do not use colour as the only state indicator. Avoid making every surface the same beige or using rainbow category chips.

## Typography
Use two families only: Fraunces or similar expressive serif for editorial display, and DM Sans or a highly legible sans for UI/body. Include fallbacks.
- Display: 34–42px.
- Screen title: 26–32px.
- Section title: 19–23px.
- Item title: 17–20px.
- Body: 15–17px.
- Supporting: 13–14px.
- Metadata: 11–12px, never for essential instructions alone.

## Spacing and layout
Use a 4px rhythm: 4, 8, 12, 16, 20, 24, 32, 40 and 48px. Phone gutters are usually 16–20px. Keep at least 12px between unrelated groups. Do not shrink text or gutters to force more into a row. Use layout gaps rather than arbitrary margin patches or negative transforms. Respect safe areas and persistent navigation.

## Surfaces and controls
Use a restrained radius scale: 8px compact, 12px standard, 18px large editorial. Pills are only for compact filters/tags. Dividers use a subtle one-pixel rule. Buttons are flat, with no drop shadows or raised/inset effects. Avoid outlining every component.

## Screen composition
- **For you:** one editorial anchor, obvious starting action, easy-to-find search, varied formats rather than repeated identical cards. First viewport stays focused.
- **Explore:** map fills available area above persistent bottom navigation. Essential controls sit in a fixed layer. No initial title banner, tray or place sheet.
- **Plan:** group choices by purpose and make selected states obvious.
- **Saved/Journal:** prioritise names and meaningful state; distinguish saved from visited.
- **Desktop:** intentional phone-use hand-off, not a stretched phone layout.

## Component inventory
Shared components are required for app shell/navigation, button variants, icon button, search, filters, selectors, place result, editorial feature, collection and outing preview, place sheet, plan stop/summary, saved/visited states, empty/loading/offline/error/no-result states and feedback toast. Define default, pressed, selected, disabled, focus-visible, loading and error states as applicable. State styling must correspond to real application state.

## Illustration quality
Draw scenes, not symbols. Use researched architecture, varied storefronts, signage, windows, awnings, balconies, street furniture, plants, people and locally appropriate transport. Avoid triangle-roof houses, repeated tree circles, generic grids or reusing the same scene crop to imply city coverage. Separate semantic SVG groups for geography, landmarks, decorative art and interactive places. The map is illustrative, not geographic.

## Accessibility and implementation
Use semantic controls, accessible names, visible focus, contrast checks, reduced-motion support and touch targets ideally at least 44×44px. Test 360, 390, 430, 759 and 760px plus desktop hand-off. CSS custom properties are the source of truth. Remove conflicting legacy rules and obsolete variants instead of adding specificity patches. No screen is complete until visual, interaction and responsive checks pass.
