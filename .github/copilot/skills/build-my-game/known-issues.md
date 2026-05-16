# Known Game Generation Issues

This file is a living record of pitfalls discovered during game generation.
Read this BEFORE generating any new game. When a participant reports a
fundamental issue, add it here so future games avoid the same mistake.

---

## Mobile / Touch

- **Title screen must respond to tap, not just SPACE.** Add both a `click` and
  `touchend` listener on `#title-screen` that calls `startGame()`. Update the
  start-text to say "Press SPACE or Tap to Start".
- **Game-over and win screens** must also have tap-friendly restart buttons
  (large enough for fingers, `min-height: 44px`).
- **On-screen touch controls** (d-pad, action buttons) are required. Use
  `@media (pointer: coarse)` to show them only on touch devices. Hide the
  keyboard-only `#controls-hint` on touch devices.

## Camera & Visibility

- **City / Cyberpunk background buildings must not overlap the play area.**
  Place decorative buildings well outside the gameplay bounds (e.g., |X| > 15
  and/or Z < −10 for a camera at Z ≈ 12). Never scatter buildings randomly
  across the full X range at shallow Z depths — they will block the player's
  view.
- **Camera must frame the entire play area** with margin. After placing all
  gameplay elements, verify that the camera frustum fully contains the play
  zone at all times.
- **Tall decorative geometry** (buildings, trees, mountains) should be pushed
  behind or beside the gameplay area, never in front of or overlapping it.

## Gameplay

- **Side-scrollers and runners on "Platformer" genre.** Do NOT default to
  auto-scrolling runner mechanics when the participant picks Platformer. Use
  full 2D/3D arena movement instead.
- **Unreachable platforms.** When generating platform layouts, ensure every
  platform is reachable from at least one other platform given the player's
  jump height and speed.
- **Instant death on spawn.** Never place hazards or enemies at or near the
  player's spawn point. Leave a safe zone of at least 3 units around spawn.

## Physics

- **Pigs (and other destructible objects) must have gravity applied.** Static mesh positions don't respond to block removal. Give each pig a `velY` field, apply gravity each frame, check support from the ground and from surviving blocks, and let pigs fall and die when unsupported. Without this, hitting a block under a pig has no visible effect.

## Slingshot / Launcher Mechanics

- **Bird drag must be clamped to pull-back direction only.** In a slingshot game the bird rests at the fork position. Dragging RIGHT on screen moves the bird toward the targets (wrong). Fix: clamp `newX` to `≤ SLING_POS.x` so the bird can only be pulled left/back. The launch velocity `(rest - pull)` is then always positive (toward the targets).
- **A rubber-band visual is required.** Without visible bands connecting the fork tips to the bird, users have no feedback that dragging is working. Add two `THREE.Line` objects that update their endpoints to `bird.position` each frame, hidden while the bird is in flight.

## Audio

- **AudioContext must be resumed on first user gesture** (`if (audioCtx.state
  === 'suspended') audioCtx.resume();` inside the `startGame()` handler),
  otherwise browsers silently block all sound.
- **Background music must use midrange notes or a melody loop, not a single
  low-frequency oscillator.** Avoid ambient tracks that sit around sub-bass
  frequencies (for example ~80 Hz sawtooth only), because they read as rumble
  instead of music on laptop speakers.
