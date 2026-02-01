# Game UI

3D cinematic character selection screen built with Three.js.

**[&#x1F3AE; Live Demo](https://bjz05.github.io/game-ui/)**

## Characters

| Character | Role | Strengths |
|-----------|------|-----------|
| Iron Knight | Armored Defend | High armor, high health |
| Wind Dancer | Free-Spirit Blade | High mobility |
| Cyber Ronin | Shadow Striker | High mobility, high power |


## Controls

| Input | Action |
|-------|--------|
| Arrow keys / click card | Navigate characters |
| Enter / Select button | Trigger celebration |
| Drag on 3D view | Orbit camera |
| Click anywhere (during celebration) | Dismiss |

## Project Structure

Everything runs from a single file (`index.html`) with no build step.

| File | Purpose |
|------|---------|
| `index.html` | Full app — HTML, CSS, and JS |
| `*.glb` | 3D character models (Three.js GLTFLoader) |
| `*.png` | 1024×1024 character portrait thumbnails |

## Development Notes

- All 3D logic (scene, camera, lights, orbit, celebration keyframes) is in the `<script type="module">` block.
- Bounding boxes in `characters[].bb` must be updated manually if models change — they drive camera framing and celebration shot targets.
- No build step. Only external dependency is Three.js r159 via jsdelivr CDN.
