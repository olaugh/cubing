# cubing

A single-file web app for practicing speedsolving. Pick a puzzle from the top
chooser:

- **2×2 (Pocket Cube)** — the **Ortega** method (FLL → OLL → PBL).
- **Pyraminx** — a layer-by-layer method (first face → L3E, the last three edges).

## Features

- **3D stickerless puzzle** (Three.js) you turn from the keyboard, with the
  faces that point away from the camera **projected** just outside the
  silhouette so you can read every side while orbiting.
- A **2D net** of the whole puzzle (cube cross / folded Pyraminx triangle) that
  tracks the live state.
- **Random-state scrambles**, an inspection + from-first-move timer, and
  automatic **phase splits** in the solve history (FLL/OLL/PBL · first-face/L3E).
- **Last-layer case recognition** with optional name/move hints —
  OLL & PBL for the 2×2; the 6 **L3E** cases (Sledgehammer, Hedgeslammer,
  the two 3-cycles, two-flip, skip) for the Pyraminx. Pyraminx algs are shown
  in the screen-relative letters the keys use, so they read off as you hold the
  puzzle.
- An **optimal first-layer / first-face solver** and an **N-move drill** mode
  (the `1`–`4` keys) for both puzzles.
- **Session & per-day stats** persisted to `localStorage`, kept **separate per
  puzzle** and bucketed by which hint information was used.

## Run

It's a single static file — open `index.html` directly, or serve it:

```sh
python3 -m http.server 8124
# then open http://localhost:8124/index.html
```

It's also deployed via GitHub Pages: <https://olaugh.github.io/cubing/>.

## Controls

| Action | 2×2 | Pyraminx |
| --- | --- | --- |
| Turns | `R` `L` `U` `D` `F` `B` | `u` `l` `r` `b` → U L R B |
| Prime (`'`) | hold **Shift** (or `E I G S K N`) | hold **Shift** |
| Tips / rotations | `x` `y` `z` rotate the cube | **⌥ Option** + key turns a tip |
| Seamless double | double-tap a face | — (Pyraminx has no doubles) |
| Pause / hide | `Space` | `Space` |
| (Re)start drill | `1`–`4` | `1`–`4` |
| Orbit / zoom | drag / scroll | drag / scroll (snaps to a canonical view) |

Pyraminx move keys follow the view — `R` always turns the tip on the right,
like holding a real puzzle.

## Color scheme

- **2×2:** White U · Yellow D · Green F · Blue B · Red R · Orange L.
- **Pyraminx:** Green · Blue · Red · Yellow on the four faces.
