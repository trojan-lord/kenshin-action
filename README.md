# ⚔ Rurouni Kenshin — Battousai's Wrath

A 16-bit Game Boy-style side-scrolling action game inspired by *Rurouni Kenshin*.  
**Play now → [trojan-lord.github.io/kenshin-action](https://trojan-lord.github.io/kenshin-action/)**

## 🎮 Controls

### Keyboard
| Key | Action |
|-----|--------|
| ← → / A D | Move |
| Space / W / ↑ | Jump (2x) |
| Z / J | Attack (Sakabato slash) |
| X / K | Special (Hiten Mitsurugi — costs HP) |
| P | Pause |

### Mobile (Touch)
D-pad on left side + JUMP / ATK / SP buttons on right. Pause button top-right.

## 🏗 Architecture

- **Single HTML file** — zero dependencies, no build step, pure Canvas2D
- **Fixed 60Hz timestep** game loop with `requestAnimationFrame`
- **Game Boy green palette** (`#0f380f` → `#9bbc0f`) + Kenshin character colors
- **Procedural pixel art** — all sprites drawn with `fillRect`/`arc`/`beginPath`
- **4-layer parallax** — moon, mountains, trees, foreground (with scroll speeds)
- **WebAudio** procedural sounds — jump, slash, hit, special, wave fanfare, boss alarm
- **Touch overlay** — separate DOM layer with `pointer-events:auto` buttons (multi-touch safe)
- **State machine** — title → play → pause/win/lose with proper transitions
- **Fixed timestep accumulator** — physics independent of frame rate

## ⚔ Features

- **Combo system** — chain hits for score multipliers (3x+)
- **4 enemy types** — Thug, Samurai, Archer (ranged), Elite (tough + horns)
- **Boss fights** — every 5 waves, "Dragon Head Oni" with enraged phase at 50% HP
- **Health pickups** — dropped by bosses (15% chance from elites)
- **Score pickups** — gold coins for bonus points
- **Hit freeze** — 2-3 frame pause on impact for combat juice
- **Screen shake** — scales with damage dealt
- **Floating damage numbers** — color-coded by type
- **Particle system** — slash sparks, death bursts, jump dust
- **High score** — persisted in localStorage
- **Lives system** — 3 lives, respawn at safe position with full HP
- **Fall recovery** — respawn at last safe platform

## 📁 File Structure

```
kenshin-action/
├── index.html    (game — single file, ~850 lines)
└── README.md     (this file)
```

## 🎨 Credits

Inspired by Nobuhiro Watsuki's *Rurouni Kenshin*.  
Built with ❤ and Canvas2D.
