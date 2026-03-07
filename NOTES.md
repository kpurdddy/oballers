# O'Ballers -- Build Notes

## Alpha 1.1.2 (2026-03-07)
- Fix: True landscape on portrait phones via CSS rotate(90deg) on game container.
- Fix: Pointer coordinate transform -- raw clientX/clientY swapped and remapped when rotated.
- Fix: Letterboxing/pillarboxing -- court constrained to 1.6:1 aspect ratio on all screen shapes. Circles stay circular.
- Fix: calcDims uses physical screen dimensions when portrait, not CSS-swapped container rect.
- Fix: Layout values (offsets, game dimensions) cached in ref for pointer handler performance.
- Fix: Orientation detection via matchMedia (physical rotation only, immune to URL bar jitter).
- Taps in black bars outside the court are rejected (no phantom inputs).
- Version updated to Alpha 1.1.2.

## Alpha 1.1.0 (2026-03-04)
- Fix: Landscape orientation. calcDims now targets 1.6:1 width:height ratio. Court fills landscape viewport correctly.
- Fix: Visible OOB border. 5-unit border around the court canvas. Sidelines, baseline, and half-court line are no longer flush against screen edges. Throw-in and baseline OOB events have visible space.
- Fix: Basket now visible. Landscape + OOB border above Y=0 ensures basket at BASKET_Y=14 is fully on screen.
- Fix: Shoot tap detection. Was gating on tap distance < 20 from basket. Now correctly uses carrier distance <= SHOOT_RANGE. Mid-range shots work.
- Fix: HUD score and version text now visible. Removed media query hiding version below 600px. HUD divs anchored inside court container div. Pill background opacity increased.
- Version updated to Alpha 1.1.0

## Alpha 1.0.0 (2026-03-04)
- Foundation build -- 3v3 half court basketball forked from Soccer Mamas Alpha 2.3.0
- Half court with single basket, three-point arc, key/paint, backboard rendering
- 3v3 formations: PG/SG/SF per team
- Drag to move players (waypoint route system inherited)
- Tap teammate to pass (interception check inherited)
- Tap basket area to shoot (distance/angle probability, 2pt vs 3pt detection)
- Miss = loose ball near basket (rebound scramble)
- Tap CPU carrier to commit defender (check system inherited)
- Score display, first to 11 wins, game over screen
- Solo mode: CPU controls away team (basic pass/shoot AI)
- Two-player local WiFi via PeerJS, host authority model, "ob-" room code prefix
- Seeded PRNG (gameRNG, mulberry32) -- zero Math.random() calls
- Known missing rules: no clearing rule after defensive stop, no shot clock, no fouls, no traveling
- Known issues: CPU has no offensive positioning, no rebound positioning AI
