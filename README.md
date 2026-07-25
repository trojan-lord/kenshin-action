# 剣心 — Rurouni Kenshin: Battousai's Wrath

A 16-bit style side-scrolling action game featuring Kenshin Himura from Rurouni Kenshin.

**🎮 [PLAY NOW](https://trojan-lord.github.io/kenshin-action/)**

## Screenshots

> 16-bit Game Boy green palette · Procedural pixel art · Multi-layer parallax backgrounds

## Features

- **Pure HTML5 Canvas** — single `index.html`, zero dependencies, no build step
- **Fixed 60Hz timestep** game loop (not frame-rate dependent)
- **Procedural WebAudio** sound effects — no external audio files
- **Multi-layer parallax scrolling** — moon, mountains, trees, ground, details
- **Procedural pixel art** characters drawn with Canvas primitives
- **Camera system** with smooth lerp tracking + screen shake
- **Combo system** with score multipliers
- **Special move** (Hiten Mitsurugi) — costs HP, hits all nearby enemies
- **4 enemy types** — Thugs, Samurai, Archers, Elites
- **Endless wave system** with increasing difficulty
- **Mobile touch controls** — auto-detected on touch devices
- **Tappable start button** — works on desktop and mobile

## Controls

### Desktop
| Input | Action |
|-------|--------|
| ← → / A D | Move |
| Space / W | Jump (double jump) |
| Z / J | Attack (sakabato slash) |
| X / K | Special (Hiten Mitsurugi — costs 5 HP) |
| Enter | Start / Restart |

### Mobile
On-screen touch controls appear automatically:
- **◀ ▶** — Move left/right
- **JUMP** — Jump (double tap for double jump)
- **ATK** — Sakabato slash
- **SP** — Hiten Mitsurugi special
- **TAP canvas** — Start game

## Architecture

```
index.html (single file, ~850 lines)
├── Utilities      — AABB collision, lerp, clamp, random
├── Palette        — 16-bit Game Boy green + character accent colors
├── Sound          — WebAudio procedural (square, sawtooth, noise)
├── Input          — Keyboard + touch multi-touch support
├── Player         — State machine (idle/run/jump/attack/special/hurt)
├── Enemies        — 4 types with AI (patrol, chase, shoot)
├── Waves          — Endless spawning with scaling difficulty
├── Platforms      — Ground + floating stone platforms
├── Background     — 4-layer parallax (moon/torii/mountains/trees/ground)
├── Particles      — Slash sparks, hit effects, floating damage numbers
├── HUD            — HP bar, wave counter, score, combo display
├── Camera         — Smooth lerp tracking + dampened screen shake
└── Game Loop      — Fixed 60Hz timestep + requestAnimationFrame
```

### Key Patterns
- **Fixed timestep accumulator** — game logic at 60Hz regardless of display refresh
- **Separated X/Y collision** — prevents corner-snagging on tile edges
- **State machine** — clean transitions between player/enemy states
- **Object pooling** — particles and floaters reuse memory
- **Procedural audio** — all sounds generated via WebAudio oscillators + noise

## Run Locally

```bash
# Option 1: Direct file open (works on desktop)
open index.html

# Option 2: HTTP server (required for mobile/touch)
python3 -m http.server 8080
# Then visit http://localhost:8080
```

## Credits

- Character: Himura Kenshin from **Rurouni Kenshin** by Nobuhiro Watsuki
- Built with pure HTML5 Canvas + JavaScript
- Architecture inspired by [grand-line-quest](https://github.com/solankianandwork-zorro/grand-line-quest), [legacy-games](https://github.com/humancto/legacy-games), and [gothicvania-codex-demo](https://github.com/acatovic/gothicvania-codex-demo)

## License

MIT
