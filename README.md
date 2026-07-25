# 剣心 — Rurouni Kenshin: Battousai's Wrath

A 16-bit style side-scrolling action game featuring Kenshin Himura from Rurouni Kenshin.

## Features
- Pure HTML5 Canvas — single file, no dependencies
- Fixed 60Hz timestep game loop
- Procedural WebAudio sound effects
- Multi-layer parallax scrolling backgrounds
- Procedural pixel art characters
- Combo system with score multipliers
- Special move (Hiten Mitsurugi) that costs HP
- 4 enemy types: Thugs, Samurai, Archers, Elites
- Endless wave system with increasing difficulty
- Mobile touch controls (auto-detected)

## Controls
| Input | Action |
|-------|--------|
| ← → / A D | Move |
| Space / W | Jump (double jump) |
| Z / J | Attack (sakabato slash) |
| X / K | Special (Hiten Mitsurugi — costs 5 HP) |

## Architecture
- Fixed timestep game loop (60Hz logic + requestAnimationFrame render)
- Pure Canvas2D rendering (no p5.js)
- Procedural WebAudio for all sounds
- AABB collision detection
- Camera system with smooth lerp tracking
- Particle system for visual effects
- Floating damage/score numbers

## Play
Open `index.html` in any browser. Serve via HTTP for mobile access:
```bash
cd kenshin-action && python3 -m http.server 8080
```
