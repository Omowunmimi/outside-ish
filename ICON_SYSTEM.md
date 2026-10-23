# Outsideish Icon System

**Status:** Required foundation for the UI reset. Missing or inconsistent icons block screen sign-off.

## Purpose and visual language
Use a single family of authored SVG interface icons. Icons should be clear, restrained and consistent, with shared geometry, stroke weight, cap/join treatment and optical alignment. Use a simple rounded stroke style and the documented Ink/Forest palette. Icons are interface assets, not mini illustrations.

Never use emoji, arbitrary Unicode symbols, text glyphs or unrelated icon packs as substitutes.

## Required inventory
### Primary navigation
- nav-for-you
- nav-explore
- nav-plan
- nav-saved
- nav-journal

### Common actions
- search
- filter
- zoom-in
- zoom-out
- recenter
- close
- back
- chevron-right
- chevron-down
- external-link
- share
- copy-link
- bookmark
- visited
- plus
- minus
- remix
- swap
- clock
- spend
- location-pin
- info
- check
- alert
- offline

Add category-specific icons only when they improve recognition and are used consistently. Category illustrations may be richer, but no emoji category labels.

## Sizing and alignment
- Bottom navigation: 22–24px.
- Standard controls: 20–22px inside a minimum 44×44px target where practical.
- Inline action: 16–18px only when still legible.
- Editorial/category symbol: 24–32px, used sparingly.
- Normalise SVG viewBoxes to a shared 24×24 coordinate system.
- Align by optical centre, not only mathematical bounds.
- Keep the click target separate from the visible icon size.

## States
- Default: Ink or documented foreground token.
- Selected navigation: Forest plus visible label and another state cue.
- Pressed: brief tonal change, no raised effect.
- Disabled: subdued but readable.
- Error/destructive: Error token plus accessible text/label.
- Saved/visited: icon and text/state communicate the outcome.
Never use colour as the only state indicator.

## Accessibility
Decorative icons are hidden from assistive technology. Icon-only controls require useful accessible names such as “Close place details”, not “X”. Focus belongs to the control, not the SVG path. Check contrast on actual backgrounds.

## Implementation contract
Centralise SVG assets in a sprite or shared icon component. Use stable names matching this inventory. Avoid copying separate path markup into every screen. Verify every asset exists and loads. Never silently fall back to emoji or arbitrary characters if an icon fails.

## Acceptance checklist
- [ ] Every primary navigation destination has its approved icon and visible label.
- [ ] All map actions have the correct icons.
- [ ] Icons share a consistent visual language and optical weight.
- [ ] No emoji or mixed-pack substitutes remain.
- [ ] Icon-only controls have accessible names.
- [ ] All SVGs load without errors.
- [ ] Icons remain legible at their documented sizes.
- [ ] Selected, pressed, disabled and error states are intentional.
