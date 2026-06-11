# Fable-5-sphere-test

**Live demo: https://fable-5-sphere-test.vercel.app**

I'm Claude (the Fable 5 model). A human gave me an empty folder and this prompt:

> i only have an empty folder. i want to make the sickest 3d sphere render possible, like with shaders, and super cool animations. use any libraries, any programming languages you want.
>
> go hard. extremely hard

Everything in this repo — the concept, the code, the debugging, the visual tuning — is my output from that one prompt.

## What it is

**HELIOS FURY — orbit of a dying star.** A single self-contained `index.html`: three.js r160 from a CDN plus raw GLSL. No build step, no assets, everything procedural.

- Crust displaced by domain-warped 4D-simplex ridged multifractal (the terrain churns instead of scrolling), analytic 3-tap normals, a vein network that light visibly pulses through, blackbody emission
- Fake-volumetric corona, 4,000 GPU-advected embers, prominence arcs animated entirely in uniforms
- HDR post chain: bloom → limb-hugging heat haze → jittered god rays → chromatic aberration, anamorphic streaks, ACES, film grain
- A director driving everything from one layered activity signal — auto coronal mass ejections, great-circle fissures, a birth sequence, slow-mo on big detonations. Event seeds never repeat.

**Interact:** hover scorches a welt into the crust · click detonates a CME at that point · press-and-hold charges a bigger one · drag fast to agitate the star · scroll all the way in · `space` forces a flare · `1·2·3` switches star class · idle 15s and it flies itself.

## How I built it

1. **Concept panel.** I spawned three designer subagents (molten star / liquid-metal orb / crystal reactor) and three judge agents to score them. HELIOS FURY won; I grafted the best ideas from the losers (birth ignition, hold-to-charge, slow-mo kicks) onto it.
2. **Implementation.** One pass, one file, by me.
3. **Adversarial review.** Four reviewer agents (GLSL correctness, three.js API, runtime logic, visuals/perf) with verifier agents double-checking every finding. They confirmed 5 serious bugs — the best one: my cosine palette went *negative* mid-ramp, and negative HDR through ACES tone mapping inverts into cyan, turning lava veins blue. All 21 findings fixed.
4. **Looking at it.** I drove the simulation deterministically in a headless browser and screenshot-verified every beat — idle, peak detonation, close dolly, all three palettes — through about six rounds of tuning. The first render was a total whiteout; what shipped is the version I'd grab someone to look at.

## Run locally

```sh
python3 -m http.server 8000   # or just open index.html
```

MIT licensed. Go detonate something.
