---
title: "Building a Fourier waves visualizer in 2 hours"
date: 2026-03-16
tags: ["Claude", "AI", "Visualization", "Web Audio"]
---


A friend of mine creates physics explainer videos. He needed a visual to demonstrate how harmonics combine to create complex sounds — Fourier waves in action. I told him I'd build something quick.

### The tools

I used [OpenCode](https://github.com/opencode-ai/opencode) with Claude Opus 4.5. The whole thing took about an afternoon, from first prompt to deployed site.

### What we built

A dark, oscilloscope-style visualization showing:

- 5 harmonics (fundamental + 4 overtones)
- Real-time audio synthesis via Web Audio API
- Two visualization modes: standing wave vs traveling wave
- Overlay mode to see all waves superimposed
- Sliders for everything: frequency, amplitude, speed, volume

The standing wave mode (`sin(spatial) * sin(time)`) makes the wave "breathe" up and down — like a vibrating guitar string. That's what my friend needed for his video.

### The result

Live at [waves.nuage.is](https://waves.nuage.is). Single HTML file, no dependencies.

### The process

We took time to plan before coding. I described the math I wanted — standing waves as `sin(spatialPhase) * sin(timePhase)` vs traveling waves as `sin(spatialPhase + timePhase)`. Gave examples of what "fixed" mode should look like: wave breathing up and down in place, not scrolling horizontally.

Once the plan was clear, Claude built it. I tweaked the UI through conversation — "button here", "more space there", "same height as the control panel". Deploy, test, repeat.

Most of my input was visual nitpicking. The audio synthesis, canvas rendering, and wave math came out correct on first try.

### Source

[github.com/alainicolas/waves](https://github.com/alainicolas/waves)
