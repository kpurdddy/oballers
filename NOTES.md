# O'Ballers -- Build Notes

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
