# 🏃 Dash Runner

A *Super Mario Run*–style auto-runner platformer in a **single HTML file** — no build step, no dependencies. Pure HTML5 canvas + vanilla JavaScript.

![type: browser game](https://img.shields.io/badge/type-browser%20game-6dc3ff) ![deps: none](https://img.shields.io/badge/dependencies-none-brightgreen)

## Play

Just open `index.html` in any modern browser. Or run a local server:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## How to play

- Your character **runs automatically** to the right.
- **Tap / Click / Space** (or ↑ / W) to **jump** — hold longer to jump higher.
- Tap again in mid-air for a **double jump**.
- Press **M** to mute/unmute.

### Things in the world

| | |
|---|---|
| 🍄 **Mushroom** | grow bigger — you can now survive one hit |
| ⭐ **Star** | temporary invincibility; smash anything you touch |
| ❓ **Question block** | bump it from below for a coin or power-up |
| 🟫 **Brick** | a big player smashes it from below |
| 🌀 **Spring** | launches you sky-high |
| 🪙 **Coins / 💎 Gems** | gems are worth 5× and 50 points |
| 👾 **Goomba / 🦅 Flyer** | stomp from above to defeat (chain stomps for a **combo** multiplier) |
| 🦔 **Spiky** | can't be stomped — jump over it |
| 🟢 **Pipes & gaps** | jump or die |

The world scrolls faster the further you go, and the sky runs a continuous **day → sunset → night → dawn** cycle. Your best distance is saved locally.

## Features

- Auto-running endless platformer with procedurally generated, difficulty-scaling terrain
- Variable-height jump + double jump, spring launches
- Power-ups (mushroom growth, star invincibility), question/brick blocks
- Multiple enemy types (walker, flyer, non-stompable spiky) with stomp **combos**
- Coins, gems, score system, persistent best distance (`localStorage`)
- **Living backdrop:** continuous day/night color cycle, sun & moon, twinkling stars, night vignette
- **Multi-layer parallax:** snow-capped mountains, rolling hills, trees & bushes
- Detailed animated player sprite, particle effects, screen shake
- Procedural **sound effects** via the Web Audio API (mutable with `M`)
- Responsive: scales to any screen; works with touch, mouse, and keyboard

## Tech

Single `index.html` (~700 lines). Game loop on `requestAnimationFrame` with a clamped fixed timestep; AABB collision with separate top-landing and head-bump resolution for blocks; a chunked terrain streamer that generates scenery ahead of the camera and culls behind it; palette interpolation for the day/night cycle; and a tiny oscillator-based sound synth.

## License

MIT
