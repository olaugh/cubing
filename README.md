# cubing-trainer

A single-file web app for practicing 2×2 (Pocket Cube) solves with the **Ortega method**.

## Features

- **3D stickerless cube** (Three.js) you turn from the keyboard, with the hidden
  faces projected as tight 2×2 clusters around the cube — the ≤3 faces pointing
  away from the camera are cast just outside the silhouette, sheared by the
  viewing angle, so you can always read all six sides while freely orbiting.
- **Random-state scrambles**, an inspection + from-first-move timer, and automatic
  **FLL / OLL / PBL** phase splits in the solve history.
- **OLL & PBL case recognition** with optional on-demand hints — the algorithm
  name and/or its full move sequence (named cases: H, Pi, Sune, Anti-Sune, U, T, L;
  PBL: Adjacent, Diagonal, and their combinations). OLL algorithms start with the
  cube rotation that orients the solved layer canonically.
- **Optimal first-layer (FLL) solver** (fastest face / fastest face on top /
  fastest white) and an **N-move FLL drill** mode.
- **Session & per-day stats** persisted to `localStorage`, bucketed by which hint
  information was used (none / name / moves / name + moves).

## Run

It's a single static file — open `index.html` directly, or serve it:

```sh
python3 -m http.server 8124
# then open http://localhost:8124/index.html
```

## Controls

| Action | Keys |
| --- | --- |
| Face turns | `R` `L` `U` `D` `F` `B` (hold **Shift** for primes) |
| Prime hotkeys (key adjacent to each face) | `E` `I` `G` `S` `K` `N` → `R'` `U'` `F'` `D'` `L'` `B'` |
| Cube rotations | `x` `y` `z` |
| Seamless double turn | double-tap a face |
| Orbit / zoom | drag / scroll |

## Color scheme

White U · Yellow D · Green F · Blue B · Red R · Orange L. The 2D net uses the
standard cube-state layout (Front at the center of the cross, equatorial band
L-F-R-B, U above and D below F).
