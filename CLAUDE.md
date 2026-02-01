# Animations — Character Select

## Project Overview
Single-file Three.js character selection UI (`index.html`). Three characters with GLB 3D models, portrait thumbnails (PNG), and a cinematic celebration camera flyby on selection.

## How to Run
```bash
cd ~/Desktop/Animations
python3 -m http.server 8765
# Open http://localhost:8765 in browser
```
ES modules are used, so `file://` won't work — a local HTTP server is required.

## Structure
Everything lives in `index.html`:
- **Characters data** (`characters[]` array, ~line 541): name, role, GLB path, thumbnail PNG, stat values, and a precomputed bounding box (`bb`) used for camera auto-framing.
- **Left panel**: scrollable portrait cards built from the data array. Click or arrow keys to navigate.
- **Right panel**: Three.js WebGL canvas. Loads GLB models via `GLTFLoader`. Orbit camera with mouse/touch drag and auto-rotate.
- **Celebration sequence** (on Select / Enter): white flash → hide UI → 5-shot cinematic camera flyby with lerped lighting → title card overlay → auto-dismiss after 6 s.

## Key Files
| File | Purpose |
|------|---------|
| `index.html` | Entire app (HTML + CSS + JS) |
| `*.glb` | Three.js-compatible 3D character models |
| `*.png` | 1024×1024 character portrait thumbnails |
| `tex_preview/` | Texture preview images |
| `*.fbx` | Source FBX models (not loaded at runtime) |
| `*.mp4` | Reference/recording videos |

## Development Notes
- All 3D logic (scene, camera, lights, orbit, celebration keyframes) is in the `<script type="module">` block.
- Bounding boxes in `characters[].bb` must be updated manually if models change — they drive camera framing and celebration shot targets.
- No build step, no dependencies beyond Three.js r159 loaded from jsdelivr CDN.
