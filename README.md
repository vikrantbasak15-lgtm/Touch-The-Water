# 🌊 Pond

**Touch the water.**

An interactive, photorealistic pond that runs entirely in your browser. Click, tap or drag to make ripples, stir the surface, and watch koi, frogs, dragonflies and lily pads react in real time. It is a single HTML file with no dependencies, no build step and no assets, powered by WebGL.

---

## ✨ Features

- **Real-time water simulation**: a wave-equation height field drives ripples, interference and reflections.
- **Photorealistic rendering**: a custom fragment shader draws a pebble bed with bump lighting, caustics, refraction, depth variation and a sky reflection.
- **Living pond**:
  - 🐟 Koi fish swimming and reacting to the water
  - 🐸 A frog that hops between lily pads, belly-flops when it misses, and gets knocked off when the leaf is pushed
  - 🪰 Dragonflies that fly, hover and skim the surface
  - 🍃 Floating leaves that drift and respond to your ripples
- **Time of day**: Day, Sunset and Night, with smooth transitions between them.
- **Weather**: toggleable rain plus an adjustable wind slider.
- **Stone skipping**: flick and release to skip a stone across the pond before it sinks.
- **Procedural sound**: soft water "bloops" synthesised with the Web Audio API.
- **Performance aware**: quality presets (Auto / High / Medium / Low), plus Auto mode, which adapts the render scale to your frame rate. Your choice is remembered in `localStorage`.
- **Fixed 120 Hz physics**: the simulation feels the same on any refresh rate.
- **Touch friendly**: pointer events, safe-area insets and a responsive UI for phones and tablets.

---

## 🎮 Controls

| Action | Result |
| --- | --- |
| Click / tap | Drop a splash |
| Click and drag | Stir a trench with raised banks, and push leaves |
| Drag and release fast (with Stone skipping on) | Skip a stone |
| `M` | Toggle sound |
| `Esc` | Close the settings panel |

### Settings panel

| Setting | Description |
| --- | --- |
| Quality | Cycle Auto, High, Medium or Low |
| Rain | Toggle rainfall |
| Time of day | Cycle Day, Sunset or Night |
| Stone skipping | Enable flick-to-skip |
| Sound | Toggle audio |
| Koi fish | Show or hide the fish |
| Frogs & dragonflies | Show or hide the critters |
| Wind | Adjust surface chop and drift |
| Wave strength | Scale how strong your ripples are (0.4x to 2x) |
| Calm the water | Instantly flatten the surface |

---

## 🚀 Getting started

No installation needed.

**Option 1: just open it**

```bash
git clone https://github.com/<your-username>/pond.git
cd pond
```

Then open `Pond.html` in any modern browser.

**Option 2: serve it locally**

```bash
python3 -m http.server 8000
# visit http://localhost:8000/Pond.html
```

**Option 3: GitHub Pages**

Rename `Pond.html` to `index.html`, push to GitHub, then enable **Settings → Pages** and select your branch.

---

## 🧰 Tech stack

- **WebGL 1**: a single full-screen triangle with a heavy fragment shader
- **Vanilla JavaScript**: simulation, physics for the leaves, fish, frog and dragonflies, and input handling
- **Web Audio API**: procedural sound effects
- **CSS**: glassmorphism UI, with the [Syne](https://fonts.google.com/specimen/Syne) font loaded from Google Fonts (system fallback included)

### How it works

1. A 2D height field is stepped at a fixed 120 Hz, and its gradient gives the surface slope.
2. Layered fractal noise adds natural chop, scaled by the wind setting.
3. The fragment shader combines the slope with a Voronoi pebble bed, animated caustics, depth tinting and a sky gradient to produce the final image.
4. Leaves, fish, the frog and dragonflies are simulated on the CPU and passed to the shader as uniforms, where they are drawn procedurally with signed distance functions.

---

## 🌐 Browser support

Any modern browser with WebGL support (Chrome, Edge, Firefox, Safari, and mobile browsers). If WebGL is unavailable, the page shows a friendly notice. The page also reads `prefers-reduced-motion`.

---

## 🛠️ Tips

- If it feels slow on an older device, set **Quality → Low** in Settings.
- Turn **Wind** up and **Rain** on for a stormy pond.
- Switch to **Night** and drag slowly across the surface for the calmest look.

---

## 📄 License

Add your preferred license here (for example [MIT](https://choosealicense.com/licenses/mit/)).

---

## 👤 Author

Built by **Vikrant Basak**.
