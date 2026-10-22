# Outsideish Motion & Interaction Specification

## Purpose
Motion should make Outsideish feel responsive and inhabited. It explains selection, orientation and transitions. It should never be required to understand information, should not delay an action, and must respect reduced-motion preferences.

## Motion principles
- **Direct manipulation first:** the map follows the user's drag without lag or overshoot.
- **Cause and effect:** selected pins, filters, sheets and saved states visibly respond.
- **Quiet personality:** small expressive moments are welcome; continuous decorative movement is not.
- **Fast enough to feel immediate:** short UI transitions; longer movement only when it communicates spatial continuity.
- **Reduced motion is a first-class mode:** remove parallax, bounce, large-scale zoom and looping animation when requested.

## Motion tokens
| Token | Duration | Easing | Use |
|---|---:|---|---|
| Instant | 80–120ms | linear/ease-out | pressed states, icon swaps |
| Quick | 140–200ms | cubic-bezier(.2,.7,.2,1) | filters, selection, small reveals |
| Standard | 220–320ms | cubic-bezier(.22,1,.36,1) | screen transitions, sheets |
| Spatial | 280–420ms | cubic-bezier(.2,.8,.2,1) | deliberate map recenter or selected-place focus |
| Editorial | 320–480ms | cubic-bezier(.16,1,.3,1) | entering a major illustration or story cover |

Avoid long animations for routine navigation. Do not delay touch response to complete a flourish.

## Interaction specifications

### Map pan
- Pointer/touch down on an unoccupied map surface begins a drag.
- Map follows pointer movement one-to-one, bounded so the map does not disappear entirely from view.
- A drag must not activate a pin accidentally. Use a movement threshold to distinguish drag from tap.
- Pins retain stable positions within map coordinates.
- Drag is available with mouse and touch; preserve browser scroll behaviour outside the full-screen map.
- Map controls remain fixed to the viewport and do not move with the map.

### Map zoom
- Support pinch zoom on touch and wheel zoom on desktop where feasible.
- Provide explicit zoom-in, zoom-out and recenter controls as an accessible alternative.
- Zoom is centred on the gesture focal point when feasible; otherwise zoom around viewport centre.
- Clamp scale to a useful range; initial scale should show meaningful city context.
- Pin and label size should remain usable across zoom levels. If all content is SVG, consider a screen-space marker layer or scale-aware marker sizing.
- Recenter animates to the default city extent only when motion is permitted.

### Map feature / pin interaction
- Idle markers remain still. No continuous bobbing.
- Press: subtle scale or fill change in 90–140 ms.
- Selected: clear, restrained treatment that remains legible over the illustration.
- Selecting a pin opens a contextual bottom sheet without navigating away.
- Selecting another pin updates the same sheet and preserves map context.

### Bottom sheet
- Default state is hidden; the map opens unobstructed.
- Enter from the bottom over 240–320 ms with a short ease-out.
- Dismiss through a clear close action; Escape works on desktop. Swipe-down is optional only if it does not conflict with map gestures.
- Opening or dismissing the sheet never resets map pan, zoom or filters.
- Sheet content changes in place when another pin is selected.
- Keep the map visible above the sheet; do not cover it on initial load.
- Manage focus and announce the sheet title accessibly.

### Screen transitions
- Small opacity/vertical shifts may signal a change of destination.
- Preserve scroll position when returning to a list if practical.
- Avoid animating the whole page when the user expects an immediate map response.
- Shared-element transitions are optional; never block navigation if unavailable.

### Save and visit feedback
- Save button changes state immediately.
- Use a brief icon/label change and a concise toast.
- Avoid confetti for routine actions. A small celebratory flourish may be used for a meaningful first saved or visited moment, if not distracting.
- Feedback must also be available to screen readers through an aria-live region.

### Feed continuation
- Newly appended content should appear without moving the user's current focus unexpectedly.
- Loading indicators should appear only when more content is actually being retrieved or prepared.
- Provide a manual “Keep wandering” action in addition to scroll-based continuation.
- Do not fake network loading for static local content; progressive local batches can transition immediately or use a brief non-blocking reveal.

### Planner
- Selected choices have clear selected states.
- Submit gives immediate feedback and then presents the result list.
- Remix changes the order/selection but preserves the user's chosen constraints.
- Swapping a stop updates the plan in context; announce the change accessibly.

## Future sound direction
Sound is not in the current release scope. Keep room for future optional ambient city texture or small interaction sounds, with these rules: off by default, never autoplay, user-initiated, persistent mute/stop control, low volume, no sound-only information, and no suggestion that a real venue is currently active. Test sensory accessibility and performance before shipping.

## Reduced motion
When `prefers-reduced-motion: reduce` is enabled:
- Remove large scale/slide screen transitions.
- Disable decorative looping movement.
- Do not animate map recenter beyond an immediate state change.
- Preserve state changes, focus indicators and clear selection feedback.
- Do not remove necessary visual affordances.

## Performance
- Prefer transform and opacity animations over layout-triggering properties.
- Avoid animating complex SVG filters across the whole map.
- Keep map panning synchronous with pointer movement.
- Do not attach duplicate global listeners when switching screens.
- Ensure animations do not block scroll or touch.
- Test on mid-range mobile hardware and under reduced CPU/network conditions.

## QA checklist
- [ ] Map drag feels attached to the pointer.
- [ ] A short tap selects a pin; a drag does not open a place accidentally.
- [ ] Zoom controls work and are labelled.
- [ ] Map cannot be dragged entirely off-screen.
- [ ] Sheet controls and map gestures do not fight each other.
- [ ] Selection and save feedback are clear without motion.
- [ ] Reduced motion is respected.
- [ ] Keyboard users can reach and operate controls.
- [ ] No long decorative animation competes with place content.
## 9. Motion detail for the visual refresh

### Screen transitions
- Use a short opacity and 6–10px vertical shift for ordinary screen changes.
- Preserve the previous screen's scroll position when opening a detail view.
- Avoid animating every card individually on every render. If stagger is used, limit it to the first visible group and keep the total reveal brief.
- Do not use animation to hide a layout jump or a slow response.

### Feed continuation
- Append new items below existing items without replacing the feed.
- A newly appended batch may use a subtle 120–180ms opacity reveal.
- Do not auto-scroll the visitor when new content appears.
- If loading fails, retain existing items and expose a retry action.
- Respect the reduced-motion media query and show new content immediately in reduced-motion mode.

### Map marker behaviour
- Marker selection should be immediately visible through shape, outline, scale or a selected label.
- Avoid continuous bobbing on every marker. Reserve motion for a selected or newly discovered place, and stop decorative animation when the map is being dragged.
- A marker tap should not trigger if the pointer has crossed the pan threshold.
- If marker labels are introduced, avoid overlapping labels and provide a non-map list alternative.

### Gesture feedback
- During pan, remove the map's easing transition so the artwork follows the pointer directly.
- On release, the map may settle only if the settling behaviour is intentional and does not make it feel slippery.
- Zoom should be predictable and bounded. Keep controls anchored to the viewport.
- Pinch-to-zoom should be implemented only with a tested pointer/touch gesture handler. If not supported, the explicit zoom controls must remain visible and usable.
- Avoid blocking page scroll outside the map surface.

### Press and selection feedback
- Buttons respond immediately with a pressed state.
- Save actions switch state immediately, then announce success through a polite status message.
- Filter changes should update the visible result set without an unnecessary full-screen transition.
- Focus indication must remain visible even when hover/pressed styling is active.

### Performance and accessibility
- Animate only transform and opacity where practical.
- Avoid large blur filters or expensive continuous effects on low-powered phones.
- All essential information and interaction must remain available when animation is disabled.
- Do not flash, pulse or loop attention-grabbing effects indefinitely.


## Motion direction update

Motion should make the city feel quietly alive without turning the interface into a toy. Keep controls flat at rest and during interaction: no lift, shadow growth, or pseudo-3D press effect. Use a quick colour change or subtle opacity shift for button feedback. Map pans and zooms should feel continuous and user-directed. Pins may have a very restrained staggered arrival when the map first opens, but avoid constant bobbing that makes place selection difficult. The place sheet enters from below with a short, calm transition; closing it should reveal the exact map position beneath it. Future optional sound must be user-controlled, off by default, respectful of device settings, and never required to understand map feedback. Honor prefers-reduced-motion.
