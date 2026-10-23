# Outsideish Icon Requirements

## Confirmed requirement
Outsideish needs a consistent icon set across navigation and actions. Emoji and arbitrary Unicode/text symbols are not acceptable substitutes.

## Icon use
- Navigation and repeated actions should use the same coherent icon family.
- Keep icon sizing and alignment consistent for the same role.
- Icon-only controls must have accessible names.
- Decorative icons should not be announced to assistive technology.
- Selected, disabled, pressed and error states must be understandable without relying on colour alone.
- Icons must not replace necessary text labels where the action would otherwise be unclear.

## Inventory to cover
Map/search: search, filters, zoom in/out, close, place/location marker and any implemented recenter action.
Navigation: an icon for each actual primary destination.
Place and outing actions: save/bookmark, share, mark visited, swap a stop, shorten/remix a plan and close/back where these actions exist.
System feedback: loading, offline, no results, error and success where an icon adds clarity.

Do not add icons for features that do not exist. Names above describe semantic needs, not a prescribed drawing style.

## Asset and accessibility checks
- [ ] One icon family is used consistently.
- [ ] No emoji or arbitrary Unicode substitutes remain.
- [ ] Every icon asset referenced by the UI exists and loads.
- [ ] Icon-only controls have descriptive accessible names.
- [ ] Decorative icons are hidden from assistive technology.
- [ ] Icons remain legible at actual rendered sizes.
- [ ] Icon state matches the real action state.


## Screen coverage audit
Before sign-off, inspect every primary destination and every action surface, including search, map controls, place sheets, adventure/plan actions, Saved, Visited/Journal, share fallbacks, offline states and errors. Compare the rendered icons to the central asset set; do not allow one-off substitutes in individual screens. The inventory should follow actual implemented destinations and actions rather than adding icons for hypothetical features.
