# Outsideish Interface Requirements

This document records the interface constraints explicitly established for Outsideish. It does not invent a colour palette, font family, icon aesthetic, exact component geometry or animation timings. Those details should not be treated as approved until separately decided.

## Overall experience
- Mobile-first PWA with a web entry point.
- The mobile experience should feel like an app, not a conventional marketing website.
- Do not use website-style headers, oversized section labels or unnecessarily large typography.
- Keep layouts clean, legible and comfortably spaced. Do not cram unrelated controls or content together.
- Desktop is supported, but should encourage phone use for the intended experience rather than stretch the mobile interface into a dashboard.

## Explicitly rejected UI patterns
- No emoji in the interface.
- No neumorphism.
- No piles of elevated or floating buttons.
- No heavy outlines.
- No generic dashboard layouts.
- No repeated identical card layouts.
- No primitive placeholder illustrations used in place of considered city scenes.
- Do not add unrequested visual flourishes or impose an unapproved visual direction.

## Map and discovery
- The map is a central, full-screen, freely explorable illustrated city.
- It should be geographically grounded and include considered city details, buildings, streets, people and places.
- Search and filters are available on the map.
- No persistent place sheet or discovery tray on initial map entry.
- Tapping a place opens a bottom sheet without navigating away from the map.
- Closing the sheet preserves map position and zoom.
- The feed and map should connect places, collections, neighbourhood stories and adventures.

## Consistency requirements
- Use one consistent icon set. Do not substitute emoji or arbitrary text characters.
- Reuse shared components for repeated interface patterns.
- Keep typography, spacing, control behaviour and states consistent across screens.
- Design loading, empty, no-result, offline and error states as part of the interface.
- Use accessible names, keyboard support, readable contrast and touch-friendly controls.
- Motion may support orientation and interaction. Future sound is optional and never required.

## Details not yet specified
The product documentation does not set a final palette, exact fonts, exact spacing scale, corner radii, icon drawing style, breakpoint values or motion durations. Do not present assistant-selected values for these as user-approved design decisions. Propose them for review or derive them from a subsequently approved design reference.
