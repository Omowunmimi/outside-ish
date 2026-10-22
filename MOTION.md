# Outsideish Motion and Interaction Specification

## Purpose
Motion clarifies cause and effect and supports direct manipulation. It must not disguise weak layout or unclear controls.

## Principles
- Respond immediately to input.
- Keep map movement direct and predictable.
- Preserve context when sheets open/close.
- Use quiet personality, not constant animation.
- Respect reduced motion.
- Never fake network loading for local content.

## Motion tokens
| Token | Duration | Use |
|---|---:|---|
| Instant | 80–120ms | Pressed state and icon change |
| Quick | 140–200ms | Filter and selection |
| Standard | 200–280ms | Small transitions and sheets |
| Spatial | 260–380ms | Deliberate map recenter |
| Editorial | 300–440ms | One-time major illustration entrance |

Use restrained easing. Avoid bounce by default, continuous marker bobbing, long tails and layout animations that cause jank.

## Map pan
Pointer/touch on an unoccupied map begins a potential drag. Follow movement directly and constrain bounds. Use a movement threshold to distinguish drag from tap. A drag must not activate a marker. Support pointer and touch without hijacking scrolling outside the map. Markers remain aligned to map coordinates.

## Zoom and recenter
Use pinch where implemented and explicit zoom controls as an alternative. Controls stay fixed outside the transformed map world. Clamp zoom to useful bounds. Recenter returns to the default illustrated extent and must not imply GPS location. Do not derive real distance or directions from illustration coordinates.

## Markers and place sheet
Idle markers remain still. Press feedback is brief. A selected marker opens a bottom sheet without navigating to another primary screen. Selecting another marker updates the same sheet. The sheet is hidden on initial map entry. Closing it preserves pan, zoom and filters. Provide an accessible close action and Escape support where appropriate. Manage focus and announce the selected place. Reduced-motion mode removes non-essential movement.

## Navigation
Bottom navigation remains visible and usable on every mobile destination, including Explore. Navigation must never leave the visitor trapped behind an overlay. Preserve map/list context where practical. Avoid animating the entire app shell for routine navigation.

## Save, visit and feedback
Buttons acknowledge presses immediately. Local save/visit actions update only when the action succeeds; failures must be reported honestly. Use concise state changes and accessible feedback. Avoid confetti for routine actions. Errors must remain readable and actionable.

## Feed and planner
Appending items must not jump scroll position. Preserve existing items. When the local dataset is exhausted, do not claim fresh data was retrieved. Swap/remix preserves unrelated preferences. Explain when no exact match exists.

## Reduced motion
When reduced motion is enabled, remove parallax, non-essential zoom flourishes, large reveals and looping movement. Essential state changes remain visible without animation. Sound is out of scope and must never autoplay.

## Acceptance checks
- No marker activation after a pan.
- Fixed controls do not move with the map.
- Sheet open/close preserves map state.
- Every control has visible feedback and a functional outcome.
- Keyboard, touch and reduced-motion modes work.
