# red sector

a first-person tactical shooter with ai bots, built with raw webgl2 — no libraries, one html file.

**play:** https://hokwaichan.github.io/red-sector/

## controls
- WASD move · SHIFT walk quietly · SPACE jump (you can climb crates)
- mouse aim · click fire · R reload · ESC pause

## ai bots
- **patrol** the map with grid pathfinding (BFS)
- **spot** you with a field-of-view cone + line-of-sight raycast (crates are short, you can see over them)
- **engage** after a reaction delay: 3-round bursts while strafing, keep fighting distance, retreat when hurt
- **hear** gunshots and running footsteps, then **hunt** your last known position and **search** before giving up
- every round adds bots and makes them faster and more accurate

## webgl2 bits
- shadow mapping with a depth texture + hardware comparison (`sampler2DShadow`, 3x3 PCF)
- instanced rendering for the whole world, bots, tracers and particles
- procedural sandstone, crate and floor textures in glsl 300 es
- separate viewmodel pass for the rifle
