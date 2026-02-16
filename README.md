# 🥽 A-Frame VR Workshop — AR/VR with Meta Quest 3s

<p align="center">
  <img src="https://cloud.githubusercontent.com/assets/674727/25392020/6f011d10-298c-11e7-845e-c3c5baebd14d.jpg" alt="A-Frame VR Banner" width="100%">
</p>

<p align="center">
  <strong>Build immersive VR experiences using only HTML — no downloads, no installs, no coding degree.</strong><br>
  A beginner-friendly workshop by <a href="https://github.com/alluringxstalwart">Young Innovators STEM Lab</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/A--Frame-1.7.1-ef2d5e?style=for-the-badge&logo=aframe" alt="A-Frame">
  <img src="https://img.shields.io/badge/Device-Meta%20Quest%203s-0078D7?style=for-the-badge" alt="Meta Quest 3s">
  <img src="https://img.shields.io/badge/Level-Beginner-brightgreen?style=for-the-badge" alt="Beginner Friendly">
  <img src="https://img.shields.io/badge/Hosting-GitHub%20Pages-181717?style=for-the-badge&logo=github" alt="GitHub Pages">
</p>

---

## 📸 What You'll Build

<p align="center">
  <img src="https://cloud.githubusercontent.com/assets/674727/25377018/27be9cce-295b-11e7-9098-3e85ac1fe172.gif" alt="A-Frame Inspector Demo" width="70%">
</p>

> A full 3D interactive VR scene with shapes, textures, animations, lighting, and click interactions — viewable on desktop **and** inside a Meta Quest 3s headset!

---

## 🚀 Quick Start (2 Minutes)

### The Simplest Starter Example

This is the bare-minimum VR scene. Just **3 shapes, a floor, and a sky** — nothing else.

> 📂 **Source:** [`StarterExample.html`](https://github.com/alluringxstalwart/SourceYISL/blob/main/StarterExample.html) from the [SourceYISL](https://github.com/alluringxstalwart/SourceYISL) repo

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8" />
  <title>Young Innovators STEM Lab</title>
  <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
</head>
<body>
  <a-scene>

    <a-sky color="purple"></a-sky>
    <a-box position="-1 -0.5 -3" rotation="0 45 0" color="#4CC3D9"></a-box>
    <a-sphere position="0 0.25 -5" radius="1.25" color="#EF2D5E"></a-sphere>
    <a-cylinder position="1 -0.25 -3" radius="0.5" height="1.5" color="#FFC65D"></a-cylinder>
    <a-plane position="0 -1 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4"></a-plane>

    <a-image
      src="https://raw.githubusercontent.com/alluringxstalwart/SourceYISL/main/Landscape.png"
      position="0 5 -10"
      width="25" height="7.5">
    </a-image>

    <a-text value="Young Innovators STEM Lab"
      position="0 9.5 -10" align="center" color="white"
      font="mozillavr" width="10" height="5" anchor="center">
    </a-text>

  </a-scene>
</body>
</html>
```

**What you get:**

| Element | What It Does |
|---|---|
| `<a-sky color="purple">` | A solid purple sky wrapping the whole scene |
| `<a-box>` | A blue cube, rotated 45° |
| `<a-sphere>` | A pink ball |
| `<a-cylinder>` | A yellow pillar |
| `<a-plane>` | A green floor |
| `<a-image>` | The YISL landscape banner in the sky |
| `<a-text>` | "Young Innovators STEM Lab" title |

<p align="center">
  <img src="https://raw.githubusercontent.com/alluringxstalwart/SourceYISL/main/Landscape.png" alt="YISL Landscape Banner" width="60%">
  <br><em>☝️ This banner appears floating in the sky of the starter scene</em>
</p>

> ✅ **Try it:** Copy the code above into a file called `index.html`, open it in Chrome, and you're in VR!

---

## 🎮 Full Interactive Scene (The Default)

Once you're comfortable with the starter, level up to the **full workshop scene** with textures, animations, lighting, VR controllers, desktop controls, and click interactions.

> 📂 **Source:** [`index.html`](index.html) in this repo

### What's Included

| Feature | Details |
|---|---|
| 🖱️ **Desktop Controls** | WASD to move, mouse to look, click to interact |
| 🎮 **Meta Quest 3s Controllers** | Laser pointers on both hands, trigger to click |
| 💡 **Lighting** | Ambient + directional lights for realistic shading |
| 🧊 **Textured Objects** | Wood-textured box, floor texture, 360° city sky |
| ✨ **Animations** | Spinning box, bouncing sphere, pulsing cylinder |
| 🎯 **Click Interaction** | Click any object → random color change |
| 🏙️ **360° Sky** | Panoramic city skybox |
| 🖼️ **YISL Branding** | Landscape banner + title text |

### How to Use It

```
1. Clone this repo        → git clone https://github.com/YOUR-USERNAME/AR-VRWorkshop.git
2. Open index.html        → Double-click to open in browser
3. Explore on desktop     → WASD + mouse
4. Explore in VR          → Deploy to GitHub Pages → open on Quest browser
```

### Desktop Controls

| Input | Action |
|---|---|
| `W` `A` `S` `D` | Move forward / left / back / right |
| Mouse drag | Look around |
| Mouse click | Click on objects (aim with the white dot cursor) |

### VR Controls (Meta Quest 3s)

| Input | Action |
|---|---|
| Left joystick | Move |
| Point controller | Laser pointer appears |
| Trigger button | Click/interact with objects |

---

## 📁 Repo Structure

```
AR-VRWorkshop/
├── index.html               ← Full interactive VR scene (open this!)
├── Code Chunks.md           ← 🧱 Copy-paste code chunks for students
├── COMPLETE-WORKSHOP-GUIDE.md ← 📖 Full step-by-step workshop guide
└── README.md                ← 📄 You are here
```

| File | Who It's For | What It Does |
|---|---|---|
| **`index.html`** | Everyone | The main VR scene — open in browser or Quest |
| **`Code Chunks.md`** | Students | 20 numbered, copyable code blocks with comments |
| **`COMPLETE-WORKSHOP-GUIDE.md`** | Instructors & Students | Full workshop from zero to hero (17 parts) |

---

## 🧱 Code Chunks Reference

The [`Code Chunks.md`](Code%20Chunks.md) file contains **20 ready-to-copy chunks** that students paste directly into their `index.html`:

| # | Chunk | Difficulty |
|---|---|---|
| 1 | Starter HTML Template | 🟢 |
| 2 | Assets (Textures & Images) | 🟢 |
| 3 | Camera + Desktop Controls | 🟢 |
| 4 | Meta Quest VR Controllers | 🟢 |
| 5 | Lights (Ambient, Directional, Point, Spot) | 🟢 |
| 6 | Basic Shapes (Box, Sphere, Cylinder, Cone, Torus, Ring) | 🟢 |
| 7 | Textured Objects | 🟢 |
| 8 | Floor + Sky (Environment) | 🟢 |
| 9 | Text Labels | 🟢 |
| 10 | Images & Posters | 🟢 |
| 11 | Animations (Spin, Bounce, Pulse, Fade) | 🟡 |
| 12 | 3D Models from Tinkercad (GLB/OBJ) | 🟡 |
| 13 | Click-to-Change-Color Script | 🔴 |
| 14 | Click-to-Play-Sound | 🔴 |
| 15 | Video in VR | 🟡 |
| 16 | Teleportation | 🔴 |
| 17 | Particle Effects | 🟡 |
| 18 | Multiple Animations | 🟡 |
| 19 | Curved Images | 🟡 |
| 20 | VR Link Portals | 🟢 |

---

## 🌐 How to Deploy (GitHub Pages)

```
Step 1 → Push your code to a GitHub repository (make it Public)
Step 2 → Go to repo Settings → Pages → Source: main → / (root) → Save
Step 3 → Wait ~60 seconds — your site is live at:
         https://YOUR-USERNAME.github.io/AR-VRWorkshop/
Step 4 → (Optional) Shorten with TinyURL for easy typing on Quest
```

<p align="center">
  <img src="https://docs.github.com/assets/cb-26strqr/mw-1440/images/help/pages/publishing-source-drop-down.webp" alt="GitHub Pages Settings" width="50%">
</p>

### Opening on Meta Quest 3s

1. Put on your Quest headset
2. Open the **Meta Quest Browser**
3. Type your GitHub Pages URL (or TinyURL short link)
4. The VR scene loads — grab your controllers and explore!

---

## 🧰 Tech Stack

| Technology | Purpose |
|---|---|
| [A-Frame 1.7.1](https://aframe.io/) | Web VR framework (HTML-based) |
| HTML | Scene structure |
| JavaScript | Click interactions |
| [GitHub Pages](https://pages.github.com/) | Free HTTPS hosting |
| [Meta Quest 3s](https://www.meta.com/quest/) | VR headset |

---

## 📚 Resources

| Resource | Link |
|---|---|
| A-Frame Documentation | [aframe.io/docs](https://aframe.io/docs/1.7.0/introduction/) |
| A-Frame School (Tutorial) | [aframe.io/aframe-school](https://aframe.io/aframe-school/) |
| A-Frame Inspector | Press `Ctrl + Alt + I` in any A-Frame scene |
| Starter Assets | [SourceYISL Repo](https://github.com/alluringxstalwart/SourceYISL) |
| Tinkercad (3D Models) | [tinkercad.com](https://www.tinkercad.com/) |
| Sketchfab (Free Models) | [sketchfab.com](https://sketchfab.com/) |
| 360° Sky Images | [Flickr Equirectangular](https://www.flickr.com/groups/equirectangular/) |

---

## 🤝 Workshop Flow (For Instructors)

```
 ┌─────────────────────────────────────────────────────────────┐
 │  1. SHOW the Starter Example (5 min)                        │
 │     → Open StarterExample.html from SourceYISL repo         │
 │     → "Look — 6 lines of HTML = a VR world!"               │
 │                                                             │
 │  2. EXPLAIN the building blocks (10 min)                    │
 │     → Shapes, position, color, sky                          │
 │     → Use the Code Chunks guide                             │
 │                                                             │
 │  3. BUILD together — the full scene (30 min)                │
 │     → Follow index.html step by step                        │
 │     → Add textures, lights, animations, controllers         │
 │     → Students copy chunks from Code Chunks.md              │
 │                                                             │
 │  4. CUSTOMIZE (15 min)                                      │
 │     → Students change colors, positions, add new objects    │
 │     → Import Tinkercad models                               │
 │                                                             │
 │  5. DEPLOY & EXPLORE (10 min)                               │
 │     → Push to GitHub → Enable Pages → Open on Quest 3s     │
 └─────────────────────────────────────────────────────────────┘
```

---

## ⭐ Quick Tips

- 💡 Press **`Ctrl + Alt + I`** in any A-Frame scene to open the **visual inspector** — drag objects around in 3D!
- 🔄 Always **refresh** the browser after editing your HTML
- 📐 `position="x y z"` → **x** = left/right, **y** = up/down, **z** = forward(−)/backward(+)
- 🎯 Add `class="clickable"` to any object you want to interact with
- 🖼️ Textures override colors — remove `src` if you want flat colors
- 📱 A-Frame works on **phones too** — just open the link in mobile Chrome/Safari

---

<p align="center">
  <strong>Made with ❤️ by Young Innovators STEM Lab</strong><br>
  <a href="https://github.com/alluringxstalwart/SourceYISL">Starter Assets</a> · 
  <a href="https://aframe.io/">A-Frame</a> · 
  <a href="https://www.meta.com/quest/">Meta Quest</a>
</p>
