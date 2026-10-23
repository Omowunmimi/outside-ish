# Outsideish Motion and Interaction Requirements

## Principles
Motion may support orientation and explain the result of an action. It must not interfere with usability or disguise a broken interaction. Future sound is optional and must never be necessary to use the product.

## Map interaction
- Map movement should respond directly to the user's drag/pan input.
- A map drag must not accidentally activate a place marker.
- Fixed controls should not move with the illustrated map world.
- Zoom controls, where present, must operate predictably.
- Tapping a place opens its bottom sheet without navigating away from Explore.
- Closing the sheet preserves map position and zoom.
- Selecting a different place should update the contextual details without creating an unnecessary navigation stack.

## Navigation and controls
- Every visible control must provide feedback and perform its stated action.
- Opening or closing a sheet must not trap the user or block primary navigation.
- Saving and marking a visit should update the visible state only when the action succeeds.
- Do not add decorative animation that delays or obscures an action.

## Accessibility
- Respect reduced-motion preferences.
- Provide a non-motion cue for every meaningful state change.
- Ensure keyboard access and appropriate focus behaviour for sheets and controls.
- Sound must not autoplay and is not a requirement for core interaction.

## Validation
- [ ] Dragging the map does not activate a marker.
- [ ] Fixed map controls remain fixed while the map moves.
- [ ] Opening and closing a place sheet preserves map position and zoom.
- [ ] All actions work without relying on animation or sound.
- [ ] Reduced-motion and keyboard interactions are tested.


## Cross-screen behaviour
Test interactions as complete journeys, not only in isolation. Navigation must remain available when a map sheet is open; returning to the map should preserve its context where specified; saving and visited actions must reflect successful state changes; and failed/offline operations must not animate into a false success state. Motion timings and easing remain unspecified until explicitly approved.
