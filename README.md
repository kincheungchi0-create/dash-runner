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
- You get a **double jump** — tap again in mid-air.
- **Stomp** enemies from above to defeat them (and bounce!).
- **Collect coins** for score.
- **Don't fall** into the gaps.

The world scrolls faster the further you go. Your best distance is saved locally.

## Features

- Auto-running endless platformer with procedurally generated terrain
- Variable-height jumps + double jump
- Coins, floating platforms, stompable enemies, and pits
- Parallax hills & clouds, particle effects, run animation
- Distance + coin HUD, persistent best score (`localStorage`)
- Responsive: scales to any screen, works with touch, mouse, and keyboard

## Tech

Single `index.html` (~500 lines). Game loop on `requestAnimationFrame` with a clamped fixed timestep, axis-aligned bounding-box collision, and a chunked terrain generator that streams scenery ahead of the camera and culls what's behind.

## License

MIT
