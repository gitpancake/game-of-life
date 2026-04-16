# game-of-life

**Archived.** Conway's Game of Life implemented with **WebGL shaders** — each simulation step runs as a fragment-shader pass, reading cell state from a texture and writing the next generation to another.

## What it did

- Pure static page — `index.html` + `bundle.js` + `style.css` + shader source in `shaders/`
- GPU-parallel evolution: every pixel evaluated in a fragment shader
- No dependencies beyond a browser with WebGL

## Structure

```
index.html
bundle.js            # Bundled JS (source-mapped? — was distribution form)
style.css
shaders/             # GLSL vertex/fragment shader pairs
```

## How it worked

Game-of-Life rules — birth/death based on neighbor count — are trivially expressible as a single fragment shader that samples a texel and its 8 neighbors, then writes the new state. Ping-ponging between two textures gives generation-over-generation evolution.

Tiny one-off experiment exploring shader-based cellular automata.
