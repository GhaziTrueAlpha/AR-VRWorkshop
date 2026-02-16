# 🥽 Complete A-Frame VR Workshop Guide — Meta Quest 3s Edition

> **📋 Workshop-Ready:** Every code chunk is copy-paste ready!
> **🧒 Beginner-Friendly:** Explained like you're 15 and just started coding
> **🌐 GitHub Pages + TinyURL:** No Glitch needed — we use GitHub Pages for hosting
> **🎮 Meta Quest 3s:** Tested and ready for Quest 3s controllers

![A-Frame Banner](https://cloud.githubusercontent.com/assets/674727/25392020/6f011d10-298c-11e7-845e-c3c5baebd14d.jpg)

---

## 🗺️ How This Guide Works

This guide takes you from **zero to VR hero** — step by step:

```
🟢 EASY (Parts 2-7)      → Simple HTML tags, no JavaScript needed
🟡 MEDIUM (Parts 8-10)   → Combining shapes, importing models
🔴 ADVANCED (Parts 11-13)→ Controllers, JavaScript, interactions
🧩 COPY-PASTE (Part 15)  → Ready-made code chunks for advanced features
```

> 💡 **Workshop Tip:** Start from Part 1 and go in order. Each part builds on the previous one. For advanced features, just copy-paste the code chunks from Part 15!

---

## 📚 Table of Contents

| # | Topic | Difficulty | What You'll Learn |
|---|-------|:----------:|-------------------|
| 1 | [How We Host Our VR Experience](#how-we-host) | ⚙️ Setup | GitHub Pages + TinyURL workflow |
| 2 | [Basic Scene Setup](#part-2) | 🟢 Easy | Your first VR world with shapes |
| 3 | [Adding Textures to Objects](#part-3) | 🟢 Easy | Skins, images, materials on objects |
| 4 | [Animations](#part-4) | 🟢 Easy | Spin, bounce, pulse, glow |
| 5 | [360° Sky & Environment](#part-5) | 🟢 Easy | Panoramic backgrounds & fog |
| 6 | [Lighting & Shadows](#part-6) | 🟢 Easy | Realistic lighting setup |
| 7 | [Text in VR](#part-7) | 🟢 Easy | Floating labels & titles |
| 8 | [Sound & Audio](#part-8) | 🟡 Medium | Background music & sound effects |
| 9 | [Build Custom 3D Objects in Code](#part-9) | 🟡 Medium | House, Tree, Car — using shapes |
| 10 | [Import 3D Models from Tinkercad](#part-10) | 🟡 Medium | Export → Upload → Load in VR |
| 11 | [Meta Quest 3s Controllers](#part-11) | 🔴 Advanced | Lasers, buttons, head tracking |
| 12 | [Making Objects Clickable](#part-12) | 🔴 Advanced | Laser interaction with objects |
| 13 | [Interaction Script (Color Change)](#part-13) | 🔴 Advanced | Click to change color (JavaScript) |
| 14 | [Deploy: GitHub Pages + TinyURL](#deployment) | ⚙️ Setup | Go live on Quest |
| 15 | [🧩 Advanced Copy-Paste Chunks](#part-15) | 🧩 Chunks | Teleport, Grab, Move, Physics & more |
| 16 | [Complete Copy-Paste Examples](#examples) | 📋 Reference | Full working scenes |
| 17 | [Troubleshooting](#troubleshooting) | 🔧 Help | Fix common problems |

---

<a name="how-we-host"></a>

## 🌐 1 — How We Host Our VR Experience

### Our Simple 3-Step Workflow

```
1. ✍️  CREATE → Write your index.html (copy chunks from this guide)
2. ☁️  UPLOAD → Push to a GitHub repository
3. 🌍  SHARE  → Enable GitHub Pages → Shorten with TinyURL → Open on Meta Quest 3s
```

> 💡 **Think of it like posting on Instagram:**
> You create content (your HTML file), upload it to GitHub (like posting to Instagram), GitHub Pages shows it to the world (like your public profile), and TinyURL makes the link easy to type (like a Linktree short link)!

### ⚠️ Important Rules

- We are **NOT** using Glitch — only GitHub Pages
- Your link **must** be HTTPS (GitHub Pages gives this automatically ✅)
- File **must** be named `index.html` (GitHub Pages looks for this file)
- Repository **must** be Public (so everyone can open it)

---

<a name="part-2"></a>

## 📁 PART 2 — Basic Scene Setup 🟢

### 🎬 What is A-Frame?

**Think of A-Frame like LEGO blocks for VR:**

- Each block is a 3D shape (`<a-box>`, `<a-sphere>`, `<a-cylinder>`)
- You place them in a virtual room (`<a-scene>`)
- No coding degree needed — just copy & paste HTML!

**Real-Life Example:** Just like Minecraft where you place blocks to build a world, A-Frame lets you place 3D objects using simple HTML tags!

![A-Frame Inspector](https://cloud.githubusercontent.com/assets/674727/25377018/27be9cce-295b-11e7-9098-3e85ac1fe172.gif)

---

### 📝 CODE CHUNK 1: Your First VR Scene

Create a file called `index.html` and paste this:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My First VR Scene</title>
    <meta name="description" content="VR Workshop Demo">

    <!-- A-Frame Library — This is the engine that powers our VR world -->
    <!-- Think of it like downloading a game engine (Unity/Unreal) but in one line -->
    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
  </head>

  <body>
    <!-- a-scene = Your entire VR World (like a Minecraft world or Fortnite map) -->
    <a-scene>

      <!-- ====== SCENE OBJECTS ====== -->
      <!-- These are like placing furniture in a room -->

      <!-- Box: Like a Rubik's cube floating in the air -->
      <a-box
        position="-1 0.5 -3"
        rotation="0 45 0"
        color="#4CC3D9">
      </a-box>

      <!-- Sphere: Like a basketball -->
      <a-sphere
        position="0 1.25 -5"
        radius="1.25"
        color="#EF2D5E">
      </a-sphere>

      <!-- Cylinder: Like a Red Bull can standing up -->
      <a-cylinder
        position="1 0.75 -3"
        radius="0.5"
        height="1.5"
        color="#FFC65D">
      </a-cylinder>

      <!-- Plane: The floor/ground you walk on -->
      <a-plane
        position="0 0 -4"
        rotation="-90 0 0"
        width="4"
        height="4"
        color="#7BC8A4">
      </a-plane>

      <!-- Sky: Background color (like a Zoom virtual background) -->
      <a-sky color="#ECECEC"></a-sky>

    </a-scene>
  </body>
</html>
```

---

### 🧠 Code Explanation (In Simple English)

#### What Each Tag Does:

| Code | What It Means | Real-Life Example |
|------|---------------|-------------------|
| `<!DOCTYPE html>` | "Hey browser, this is an HTML page" | Like a label on a shipping box |
| `<script src="...aframe.min.js">` | Load the A-Frame VR engine | Like installing a game before playing |
| `<a-scene>` | Your VR room/world | The Fortnite map / Minecraft world |
| `<a-box>` | A 3D cube | Rubik's cube 🟦 |
| `<a-sphere>` | A 3D ball | Basketball 🏀 |
| `<a-cylinder>` | A 3D tube/can | Red Bull can 🥫 |
| `<a-plane>` | A flat surface | Floor in your room 🟩 |
| `<a-sky>` | The background of the world | Sky you see in GTA/Fortnite 🌤️ |

#### Position System — How to Place Objects:

```
position="X   Y   Z"
          👆   👆   👆
          |    |    |
          |    |    +-- Forward(-) / Backward(+)  (depth, like walking forward)
          |    +------- Up(+) / Down(-)           (height, like jumping)
          +------------ Right(+) / Left(-)        (side to side)
```

**Example:** `position="2 1 -3"` means:

- `2` → 2 meters to the **RIGHT**
- `1` → 1 meter **UP** from ground
- `-3` → 3 meters **IN FRONT** of you (negative Z = forward)

> 💡 **Pro Tip:** Think of it like Google Maps coordinates, but for your VR world! X is left/right, Y is up/down, Z is forward/backward.

#### Rotation System — How to Turn Objects:

```
rotation="X    Y    Z"
          👆    👆    👆
          |     |     |
          |     |     +-- Tilt sideways (like tilting your phone)
          |     +-------- Spin left/right (like a spinning top)
          +-------------- Tilt forward/back (like nodding your head)
```

#### Color System:

Colors use **hex codes** (like Instagram filter color codes):

- `#4CC3D9` = Light Blue
- `#EF2D5E` = Pink/Red
- `#FFC65D` = Yellow/Orange
- Use any color picker: [Google Color Picker](https://g.co/kgs/JfGHkD)

---

### 📚 Official A-Frame Docs for Part 2

| Topic | Link |
|-------|------|
| Getting Started | https://aframe.io/docs/1.7.0/introduction/ |
| Scene | https://aframe.io/docs/1.7.0/core/scene.html |
| Box Primitive | https://aframe.io/docs/1.7.0/primitives/a-box.html |
| Sphere Primitive | https://aframe.io/docs/1.7.0/primitives/a-sphere.html |
| Cylinder Primitive | https://aframe.io/docs/1.7.0/primitives/a-cylinder.html |
| Plane Primitive | https://aframe.io/docs/1.7.0/primitives/a-plane.html |
| Sky Primitive | https://aframe.io/docs/1.7.0/primitives/a-sky.html |
| Position Component | https://aframe.io/docs/1.7.0/components/position.html |
| Rotation Component | https://aframe.io/docs/1.7.0/components/rotation.html |
| All Primitives (Shapes) | https://aframe.io/docs/1.7.0/introduction/html-and-primitives.html |

---

<a name="part-3"></a>

## 🖼️ PART 3 — Adding Textures to Objects 🟢

### 🎯 What Are Textures?

**Textures are like skins/wrapping paper for 3D objects:**

- Without texture → Plain flat colors (boring! 😴)
- With texture → Realistic looks (wood, metal, brick, grass) 🤩

**Real-Life Example:**

- Fortnite skins → Change how your character looks
- Minecraft texture packs → Change how blocks look
- Phone wallpapers → Change how your screen looks

That's exactly what textures do for 3D objects!

---

### 📝 CODE CHUNK 2A: Quick Texture via URL (Simplest Way)

The easiest way — just add a `src` attribute with an image URL. That's it!

📍 **Where to paste:** Replace your objects inside `<a-scene>`.

```html
<!-- ======================================= -->
<!-- TEXTURED OBJECTS — Quick URL Method      -->
<!-- Paste INSIDE <a-scene>                  -->
<!-- ======================================= -->

<!-- Wood textured box — src = image URL (like setting a wallpaper) -->
<a-box
  position="-1 0.5 -3"
  src="https://cdn.aframe.io/a-painter/images/wood.jpg">
</a-box>

<!-- Brick textured sphere -->
<a-sphere
  position="0 1.25 -5"
  radius="1.25"
  src="https://cdn.aframe.io/a-painter/images/brick.jpg">
</a-sphere>

<!-- 360 city sky — wraps around you like a dome -->
<a-sky src="https://cdn.aframe.io/360-image-gallery-boilerplate/img/city.jpg"></a-sky>
```

> ⚠️ **Note:** This way is quick but the texture loads EVERY time the page renders. Not great for performance if you have many textures.

---

### 📝 CODE CHUNK 2B: Asset System (RECOMMENDED ⭐ Best Way)

The Asset System **preloads** all textures before the scene renders. Like how a game shows a loading screen — everything loads first, then you play smoothly.

📍 **Where to paste:** This is a **complete `<a-scene>` block** — replace your entire scene.

```html
<!-- ======================================= -->
<!-- TEXTURED SCENE WITH ASSET SYSTEM        -->
<!-- This is the RECOMMENDED way             -->
<!-- ======================================= -->

<a-scene>

  <!-- ====== ASSET LOADING ZONE ====== -->
  <!-- Think: Like a game loading screen — everything downloads first -->
  <!-- Then objects use these textures instantly (no lag!) -->
  <a-assets>
    <img id="wood-texture" src="https://cdn.aframe.io/a-painter/images/wood.jpg">
    <img id="brick-texture" src="https://cdn.aframe.io/a-painter/images/brick.jpg">
    <img id="floor-texture" src="https://cdn.aframe.io/a-painter/images/floor.jpg">
    <img id="sky-city" src="https://cdn.aframe.io/360-image-gallery-boilerplate/img/city.jpg">
  </a-assets>

  <!-- ====== TEXTURED OBJECTS ====== -->
  <!-- src="#wood-texture" uses the image with id="wood-texture" from <a-assets> -->
  <!-- Think: Like calling a saved contact instead of typing the full number -->

  <a-box position="-1 0.5 -3" src="#wood-texture"></a-box>
  <a-sphere position="0 1.25 -5" radius="1.25" src="#brick-texture"></a-sphere>
  <a-plane position="0 0 -4" rotation="-90 0 0" width="10" height="10" src="#floor-texture"></a-plane>
  <a-sky src="#sky-city"></a-sky>

</a-scene>
```

---

### 🧠 How the Asset System Works:

```
STEP 1: Save image with an ID
  <img id="wood-texture" src="https://...wood.jpg">
  Think: Saving a contact -> Name: "wood-texture", Number: "https://...jpg"

STEP 2: Use image by ID
  <a-box src="#wood-texture"></a-box>
  Think: Calling the saved contact -> "#wood-texture"

BONUS: Reuse same texture (image loads only ONCE!)
  <a-box src="#wood-texture" position="0 0 -3"></a-box>
  <a-box src="#wood-texture" position="2 0 -3"></a-box>
  <a-box src="#wood-texture" position="4 0 -3"></a-box>
  3 wooden boxes, but image downloaded only once! 🚀
```

---

### 📝 CODE CHUNK 2C: Local Textures from Your GitHub Repo

If you have your own images, upload them to a `textures/` folder in your GitHub repo.

#### Folder Structure:

```
your-repo/
├── index.html          ← Your VR scene
└── textures/           ← Create this folder
    ├── wood.jpg
    ├── metal.png
    └── grass.jpg
```

#### How to Upload to GitHub:

1. Go to your repo on GitHub.com
2. Click **"Add file"** → **"Create new file"**
3. Type `textures/placeholder.txt` (this creates the folder)
4. Commit it
5. Then upload your images to the `textures/` folder

#### Code:

```html
<!-- ======================================= -->
<!-- LOCAL TEXTURES FROM YOUR GITHUB REPO    -->
<!-- Put your images in a "textures/" folder -->
<!-- ======================================= -->

<a-assets>
  <!-- These point to files in YOUR GitHub repo's textures/ folder -->
  <img id="my-wood" src="textures/wood.jpg">
  <img id="my-metal" src="textures/metal.png">
  <img id="my-grass" src="textures/grass.jpg">
</a-assets>

<!-- Use them just like before -->
<a-box position="-1 0.5 -3" src="#my-wood"></a-box>
<a-sphere position="0 1.25 -5" radius="1.25" src="#my-metal"></a-sphere>
<a-plane position="0 0 -4" rotation="-90 0 0" width="10" height="10" src="#my-grass"></a-plane>
```

---

### 📝 CODE CHUNK 2D: Material Properties (Advanced Textures)

Want your object to look like real metal or glass? Use the `material` component!

```html
<!-- ======================================= -->
<!-- ADVANCED MATERIALS — Metallic & Rough   -->
<!-- Paste INSIDE <a-scene>                  -->
<!-- ======================================= -->

<!-- Shiny Metal Ball — like a Chrome bumper -->
<!-- metalness: 1 = fully metallic | roughness: 0 = mirror smooth -->
<a-sphere
  position="-2 1 -4"
  radius="0.7"
  material="color: #C0C0C0; metalness: 1; roughness: 0">
</a-sphere>

<!-- Rough Stone Box — like a concrete block -->
<!-- metalness: 0 = not metallic | roughness: 1 = very rough -->
<a-box
  position="0 0.5 -4"
  material="color: #8B8682; metalness: 0; roughness: 1">
</a-box>

<!-- Glossy Plastic Cylinder — like a shiny toy -->
<!-- metalness: 0.3 = slightly metallic | roughness: 0.2 = mostly smooth -->
<a-cylinder
  position="2 0.75 -4"
  radius="0.5"
  height="1.5"
  material="color: #FF4500; metalness: 0.3; roughness: 0.2">
</a-cylinder>

<!-- Transparent Glass Box — see-through! -->
<a-box
  position="4 0.5 -4"
  material="color: #88CCFF; metalness: 0.1; roughness: 0; opacity: 0.4; transparent: true">
</a-box>
```

#### Material Properties Cheat Sheet:

| Property | Range | What It Does | Example |
|----------|-------|-------------|---------|
| `metalness` | 0 to 1 | How metallic (0=plastic, 1=chrome) | `metalness: 0.8` |
| `roughness` | 0 to 1 | How rough (0=mirror, 1=sandpaper) | `roughness: 0.3` |
| `opacity` | 0 to 1 | How see-through (0=invisible, 1=solid) | `opacity: 0.5` |
| `transparent` | true/false | Enable transparency | `transparent: true` |
| `side` | front/back/double | Which side to render | `side: double` |

---

### 📝 CODE CHUNK 2E: Texture + Color Combo

You can combine textures with colors for tinted effects:

```html
<!-- ======================================= -->
<!-- TEXTURE + COLOR TINTING                 -->
<!-- The color tints/mixes with the texture  -->
<!-- ======================================= -->

<!-- Normal wood texture -->
<a-box position="-2 0.5 -3" src="#wood-texture"></a-box>

<!-- Same wood but tinted red (like red-stained wood) -->
<a-box position="0 0.5 -3" src="#wood-texture" color="#FF6666"></a-box>

<!-- Same wood but tinted blue (like painted wood) -->
<a-box position="2 0.5 -3" src="#wood-texture" color="#6666FF"></a-box>
```

---

### 🎨 Free Texture Download Websites:

| Website | What They Have | Link |
|---------|---------------|------|
| **Poly Haven** | Free 4K textures (wood, metal, ground) | https://polyhaven.com/textures |
| **Textures.com** | Huge library (15 free credits/day) | https://www.textures.com/ |
| **Unsplash** | Free high-res photos | https://unsplash.com/ |
| **ambientCG** | Free CC0 textures | https://ambientcg.com/ |

---

### 📚 Official A-Frame Docs for Part 3

| Topic | Link |
|-------|------|
| Material Component | https://aframe.io/docs/1.7.0/components/material.html |
| Asset Management System | https://aframe.io/docs/1.7.0/core/asset-management-system.html |
| Building a Basic Scene (Textures) | https://aframe.io/docs/1.7.0/guides/building-a-basic-scene.html |

---

<a name="part-4"></a>

## 🎬 PART 4 — Animations 🟢

### 🎯 What Are Animations?

Make your objects **move, spin, bounce, pulse, and glow** — automatically! No JavaScript needed — just add an `animation` attribute!

**Real-Life Example:** Like animated stickers on Instagram Stories — they move on their own! Or like the spinning logo on a loading screen.

---

### 📝 CODE CHUNK 3A: Basic Animations

📍 **Where to paste:** Add the `animation` attribute directly on any object.

```html
<!-- ======================================= -->
<!-- ANIMATED OBJECTS                         -->
<!-- Paste INSIDE <a-scene>                  -->
<!-- ======================================= -->

<!-- SPINNING Box — Rotates 360 forever -->
<!-- Like a spinning display in a jewelry shop -->
<a-box
  position="-3 1 -4"
  color="#4CC3D9"
  animation="property: rotation; to: 0 360 0; loop: true; dur: 3000">
</a-box>

<!-- BOUNCING Sphere — Goes up and down -->
<!-- Like a basketball being dribbled -->
<a-sphere
  position="0 1 -4"
  radius="0.5"
  color="#EF2D5E"
  animation="property: position; to: 0 2.5 -4; dir: alternate; loop: true; dur: 1000">
</a-sphere>

<!-- PULSING Cylinder — Grows and shrinks -->
<!-- Like a heartbeat animation -->
<a-cylinder
  position="3 0.75 -4"
  radius="0.5"
  height="1.5"
  color="#FFC65D"
  animation="property: scale; to: 1.3 1.3 1.3; dir: alternate; loop: true; dur: 800">
</a-cylinder>
```

---

### 📝 CODE CHUNK 3B: Multiple Animations on One Object

Use `animation__name` (double underscore + any name) to add multiple animations:

```html
<!-- ======================================= -->
<!-- MULTIPLE ANIMATIONS ON ONE OBJECT       -->
<!-- ======================================= -->

<!-- This box SPINS and BOUNCES at the same time! -->
<!-- Like a fidget spinner thrown in the air -->
<a-box
  position="0 1 -3"
  color="#FF6347"
  animation__spin="property: rotation; to: 0 360 0; loop: true; dur: 2000"
  animation__bounce="property: position; to: 0 2.5 -3; dir: alternate; loop: true; dur: 1500">
</a-box>
```

---

### 📝 CODE CHUNK 3C: Color Fade Animation

```html
<!-- ======================================= -->
<!-- COLOR CHANGING ANIMATION                -->
<!-- Object fades between two colors         -->
<!-- ======================================= -->

<!-- Sphere that changes from red to blue and back -->
<!-- Like a mood lamp / LED strip -->
<a-sphere
  position="0 1.5 -4"
  radius="0.8"
  color="#FF0000"
  animation="property: color; to: #0000FF; dir: alternate; loop: true; dur: 2000">
</a-sphere>
```

---

### 📝 CODE CHUNK 3D: Textured Object with Animation

Combine what you learned from Part 3 (textures) with animations!

```html
<!-- ======================================= -->
<!-- TEXTURED + ANIMATED = 🔥               -->
<!-- ======================================= -->

<a-assets>
  <img id="wood" src="https://cdn.aframe.io/a-painter/images/wood.jpg">
</a-assets>

<!-- Spinning wooden box — like a treasure chest display -->
<a-box
  position="0 1 -4"
  src="#wood"
  animation__spin="property: rotation; to: 0 360 0; loop: true; dur: 4000"
  animation__hover="property: position; to: 0 1.5 -4; dir: alternate; loop: true; dur: 2000; easing: easeInOutQuad">
</a-box>
```

---

### 🧠 Animation Properties Explained:

| Property | What It Does | Values | Example |
|----------|-------------|--------|---------|
| `property` | What to animate | `rotation`, `position`, `scale`, `color`, `opacity` | `property: rotation` |
| `to` | End value | Depends on property | `to: 0 360 0` |
| `from` | Start value (optional) | Defaults to current | `from: 0 0 0` |
| `loop` | Repeat? | `true` or `false` or a number | `loop: true` |
| `dur` | Duration in milliseconds | Number | `dur: 3000` (3 seconds) |
| `dir` | Direction | `normal`, `alternate`, `reverse` | `dir: alternate` (back and forth) |
| `easing` | Speed curve | `linear`, `easeInOutQuad`, etc. | `easing: easeInOutQuad` |
| `delay` | Wait before starting | Milliseconds | `delay: 1000` (wait 1 sec) |

#### Duration Guide:

| Value | Time | Speed |
|-------|------|-------|
| `dur: 500` | 0.5 seconds | Very fast |
| `dur: 1000` | 1 second | Fast |
| `dur: 3000` | 3 seconds | Normal |
| `dur: 5000` | 5 seconds | Slow |
| `dur: 10000` | 10 seconds | Very slow |

---

### 📚 Official A-Frame Docs for Part 4

| Topic | Link |
|-------|------|
| Animation Component | https://aframe.io/docs/1.7.0/components/animation.html |

---

<a name="part-5"></a>

## 🌍 PART 5 — 360° Sky and Environment 🟢

### 🎯 What is a 360° Sky?

Instead of a flat color background, you can wrap a **360 photo** around your entire world — like standing inside a giant snow globe with a photo printed on the inside!

**Real-Life Example:** Like a Google Street View panorama, but you're standing inside it in VR!

---

### 📝 CODE CHUNK 4A: 360° Photo Sky

```html
<!-- ======================================= -->
<!-- 360 PANORAMIC SKY                       -->
<!-- Replace <a-sky color="..."> with this   -->
<!-- ======================================= -->

<a-assets>
  <!-- Load the 360 image -->
  <img id="sky-360" src="https://cdn.aframe.io/360-image-gallery-boilerplate/img/city.jpg">
</a-assets>

<!-- This wraps the image around you in a full 360 sphere -->
<!-- Like standing inside a snow globe with a city photo -->
<a-sky src="#sky-360"></a-sky>
```

---

### 📝 CODE CHUNK 4B: Gradient Sky with Fog

```html
<!-- ======================================= -->
<!-- COLORED SKY WITH FOG EFFECT             -->
<!-- Creates depth and atmosphere             -->
<!-- ======================================= -->

<!-- Blue sky -->
<a-sky color="#87CEEB"></a-sky>
```

Add this attribute to your `<a-scene>` tag to enable fog:

```html
<!-- Fog makes far objects fade out — adds depth/atmosphere -->
<!-- type="linear" = fog gets thicker over distance -->
<!-- near = where fog starts | far = where everything disappears -->
<a-scene fog="type: linear; color: #AAB; near: 5; far: 30">
```

---

### 📝 CODE CHUNK 4C: Different Sky Moods

```html
<!-- ======================================= -->
<!-- SKY COLOR MOODS — Pick your vibe!       -->
<!-- ======================================= -->

<!-- ☀️ Bright Day -->
<a-sky color="#87CEEB"></a-sky>

<!-- 🌅 Sunset -->
<a-sky color="#FF7F50"></a-sky>

<!-- 🌙 Night -->
<a-sky color="#0a0a2e"></a-sky>

<!-- 🌲 Forest Moody -->
<a-sky color="#2d5a27"></a-sky>

<!-- 🏜️ Desert Warm -->
<a-sky color="#EDC9AF"></a-sky>

<!-- 🌊 Ocean Blue -->
<a-sky color="#006994"></a-sky>
```

---

### 📚 Official A-Frame Docs for Part 5

| Topic | Link |
|-------|------|
| Sky Primitive | https://aframe.io/docs/1.7.0/primitives/a-sky.html |
| Fog Component | https://aframe.io/docs/1.7.0/components/fog.html |
| 360 Image Gallery Guide | https://aframe.io/docs/1.7.0/guides/building-a-360-image-gallery.html |

---

<a name="part-6"></a>

## 💡 PART 6 — Lighting and Shadows 🟢

### 🎯 Why Add Lights?

By default, A-Frame adds basic lighting. But custom lights make your scene look **way more realistic** — like the difference between a phone flashlight and professional studio lighting!

---

### 📝 CODE CHUNK 5: Custom Lighting

📍 **Where to paste:** Inside `<a-scene>`, near the top (before objects).

```html
<!-- ======================================= -->
<!-- CUSTOM LIGHTING SETUP                   -->
<!-- Paste INSIDE <a-scene>                  -->
<!-- ======================================= -->

<!-- Ambient Light: Fills the entire room with soft light -->
<!-- Like having a lamp that lights everything evenly -->
<!-- intensity: 0 = pitch dark, 1 = full brightness -->
<a-light
  type="ambient"
  color="#BBB"
  intensity="0.5">
</a-light>

<!-- Directional Light: Like the sun shining from one direction -->
<!-- position tells WHERE the light shines FROM -->
<a-light
  type="directional"
  color="#FFF"
  intensity="0.8"
  position="-1 2 1">
</a-light>

<!-- Point Light: Like a light bulb hanging in the air -->
<!-- Shines in ALL directions from one point -->
<a-light
  type="point"
  color="#FF9500"
  intensity="1"
  distance="10"
  position="0 3 -3">
</a-light>
```

#### Light Types Explained:

| Type | What It Does | Real-Life Example |
|------|-------------|-------------------|
| `ambient` | Soft light everywhere | Light coming through curtains |
| `directional` | Parallel rays from one direction | The sun |
| `point` | Light from a single point in all directions | A light bulb |
| `spot` | Cone-shaped light | Flashlight / stage spotlight |

---

### 📚 Official A-Frame Docs for Part 6

| Topic | Link |
|-------|------|
| Light Component | https://aframe.io/docs/1.7.0/components/light.html |
| Shadow Component | https://aframe.io/docs/1.7.0/components/shadow.html |

---

<a name="part-7"></a>

## ✏️ PART 7 — Text in VR 🟢

### 🎯 Why Add Text?

Add floating labels, titles, instructions, or signs to your VR world!

**Real-Life Example:** Like subtitles in a movie, but floating in 3D space! Or like signs in a museum!

---

### 📝 CODE CHUNK 6: 3D Text

```html
<!-- ======================================= -->
<!-- FLOATING 3D TEXT                        -->
<!-- Paste INSIDE <a-scene>                  -->
<!-- ======================================= -->

<!-- Big Title floating in the air -->
<a-text
  value="Welcome to My VR World!"
  position="0 3 -5"
  align="center"
  color="#FFFFFF"
  width="8"
  font="mozillavr">
</a-text>

<!-- Label above an object -->
<a-text
  value="Click Me!"
  position="-1 1.5 -3"
  align="center"
  color="#FFD700"
  width="3">
</a-text>

<!-- Instructions text -->
<a-text
  value="Point your laser and press trigger to interact"
  position="0 0.5 -2"
  align="center"
  color="#AAAAAA"
  width="4">
</a-text>
```

#### Text Properties:

| Property | What It Does | Example |
|----------|-------------|---------|
| `value` | The text to display | `value="Hello World"` |
| `position` | Where in 3D space | `position="0 2 -3"` |
| `align` | Text alignment | `left`, `center`, `right` |
| `color` | Text color | `color="#FFFFFF"` (white) |
| `width` | Width of text block | `width="6"` |
| `font` | Font style | `mozillavr`, `roboto`, `exo2bold` |

---

### 📚 Official A-Frame Docs for Part 7

| Topic | Link |
|-------|------|
| Text Component | https://aframe.io/docs/1.7.0/components/text.html |

---

<a name="part-8"></a>

## 🔊 PART 8 — Sound and Audio 🟡

### 🎯 Why Add Sound?

Sound makes VR feel **real**. Without it, VR is like watching a movie on mute!

---

### 📝 CODE CHUNK 7A: Background Music

📍 **Where to paste:** Inside `<a-scene>`.

```html
<!-- ======================================= -->
<!-- BACKGROUND MUSIC                        -->
<!-- Upload your .mp3 to GitHub first        -->
<!-- ======================================= -->

<a-assets>
  <audio
    id="bg-music"
    src="audio/background.mp3"
    preload="auto">
  </audio>
</a-assets>

<!-- Attach sound to the scene (plays everywhere) -->
<!-- autoplay: starts automatically | loop: repeats forever -->
<a-sound
  src="#bg-music"
  autoplay="true"
  loop="true"
  volume="0.5"
  position="0 0 0">
</a-sound>
```

> **Note:** Most browsers block autoplay audio. The user might need to click/interact with the page first before audio plays. This is a browser security policy, not an A-Frame bug.

---

### 📝 CODE CHUNK 7B: Sound Effect on Click

```html
<!-- ======================================= -->
<!-- SOUND EFFECT WHEN CLICKING AN OBJECT    -->
<!-- ======================================= -->

<a-assets>
  <audio id="click-sound" src="audio/click.mp3" preload="auto"></audio>
</a-assets>

<!-- This box plays a sound when clicked! -->
<a-box
  position="0 1 -3"
  color="#4CC3D9"
  class="clickable"
  sound="src: #click-sound; on: click">
</a-box>
```

#### How it works:

- `sound="src: #click-sound"` — Which audio file to play
- `on: click` — When to play it (triggers on click event)

---

### 📝 CODE CHUNK 7C: Folder Structure for Audio

```
your-repo/
├── index.html
├── textures/          ← Your texture images
│   ├── wood.jpg
│   └── grass.jpg
└── audio/             ← Create this folder
    ├── background.mp3
    └── click.mp3
```

> 💡 **Free sound effects:** https://freesound.org/ and https://pixabay.com/sound-effects/

---

### 📚 Official A-Frame Docs for Part 8

| Topic | Link |
|-------|------|
| Sound Component | https://aframe.io/docs/1.7.0/components/sound.html |

---

<a name="part-9"></a>

## 🛠️ PART 9 — Build Custom 3D Objects in Code 🟡

### 🎯 What is This?

You don't always need Tinkercad! You can build 3D objects by **combining basic shapes** — like building with LEGO blocks but in code!

**Real-Life Example:** Like building a snowman by stacking 3 snowballs — you combine simple shapes to make complex objects! ⛄

---

### 📝 CODE CHUNK 8A: Build a House 🏠

```html
<!-- ======================================= -->
<!-- CUSTOM 3D HOUSE — Made from basic shapes -->
<!-- Paste INSIDE <a-scene>                   -->
<!-- ======================================= -->

<!-- The entire house is wrapped in one <a-entity> so we can move it all together -->
<!-- Think: Like grouping layers in Photoshop -->
<a-entity position="0 0 -5">

  <!-- Walls (brown box) -->
  <a-box
    position="0 1 0"
    width="3" height="2" depth="3"
    color="#8B4513">
  </a-box>

  <!-- Roof (red cone on top) -->
  <a-cone
    position="0 2.5 0"
    radius-bottom="2.2" height="1.5"
    color="#DC143C">
  </a-cone>

  <!-- Door (dark brown rectangle) -->
  <a-box
    position="0 0.5 1.51"
    width="0.8" height="1.5" depth="0.1"
    color="#654321">
  </a-box>

  <!-- Left Window (light blue square) -->
  <a-plane
    position="-0.8 1.2 1.51"
    width="0.6" height="0.6"
    color="#87CEEB">
  </a-plane>

  <!-- Right Window -->
  <a-plane
    position="0.8 1.2 1.51"
    width="0.6" height="0.6"
    color="#87CEEB">
  </a-plane>

</a-entity>
```

---

### 📝 CODE CHUNK 8B: Build a Tree 🌳

```html
<!-- ======================================= -->
<!-- CUSTOM 3D TREE                          -->
<!-- Paste INSIDE <a-scene>                  -->
<!-- ======================================= -->

<a-entity position="3 0 -4">

  <!-- Trunk (brown cylinder) — like a log -->
  <a-cylinder
    position="0 0.75 0"
    radius="0.2" height="1.5"
    color="#8B4513">
  </a-cylinder>

  <!-- Main Leaves (big green sphere) -->
  <a-sphere
    position="0 2 0"
    radius="1"
    color="#228B22">
  </a-sphere>

  <!-- Extra Leaf Clusters (smaller spheres for a fuller look) -->
  <a-sphere position="0.5 1.8 0" radius="0.7" color="#32CD32"></a-sphere>
  <a-sphere position="-0.5 1.8 0" radius="0.7" color="#32CD32"></a-sphere>
  <a-sphere position="0 1.8 0.5" radius="0.7" color="#2E8B57"></a-sphere>

</a-entity>
```

---

### 📝 CODE CHUNK 8C: Build a Car 🚗

```html
<!-- ======================================= -->
<!-- CUSTOM 3D CAR                           -->
<!-- Paste INSIDE <a-scene>                  -->
<!-- ======================================= -->

<a-entity position="-3 0.5 -4">

  <!-- Car Body (red box) -->
  <a-box
    width="2" height="0.5" depth="1"
    color="#FF0000">
  </a-box>

  <!-- Car Roof/Cabin (darker red box on top) -->
  <a-box
    position="0 0.5 0"
    width="1.2" height="0.5" depth="0.8"
    color="#8B0000">
  </a-box>

  <!-- Wheels (4 black cylinders, rotated sideways) -->
  <!-- Front-Right Wheel -->
  <a-cylinder position="0.6 -0.25 0.6" radius="0.25" height="0.1" rotation="0 0 90" color="#111"></a-cylinder>
  <!-- Front-Left Wheel -->
  <a-cylinder position="0.6 -0.25 -0.6" radius="0.25" height="0.1" rotation="0 0 90" color="#111"></a-cylinder>
  <!-- Back-Right Wheel -->
  <a-cylinder position="-0.6 -0.25 0.6" radius="0.25" height="0.1" rotation="0 0 90" color="#111"></a-cylinder>
  <!-- Back-Left Wheel -->
  <a-cylinder position="-0.6 -0.25 -0.6" radius="0.25" height="0.1" rotation="0 0 90" color="#111"></a-cylinder>

</a-entity>
```

---

### 📝 CODE CHUNK 8D: Build a Snowman ⛄

```html
<!-- ======================================= -->
<!-- CUSTOM 3D SNOWMAN                       -->
<!-- Paste INSIDE <a-scene>                  -->
<!-- ======================================= -->

<a-entity position="2 0 -4">

  <!-- Bottom (biggest snowball) -->
  <a-sphere position="0 0.6 0" radius="0.6" color="#FFFFFF"></a-sphere>

  <!-- Middle (medium snowball) -->
  <a-sphere position="0 1.4 0" radius="0.45" color="#FFFFFF"></a-sphere>

  <!-- Head (small snowball) -->
  <a-sphere position="0 2 0" radius="0.3" color="#FFFFFF"></a-sphere>

  <!-- Eyes (tiny black spheres) -->
  <a-sphere position="-0.1 2.1 0.25" radius="0.04" color="#000"></a-sphere>
  <a-sphere position="0.1 2.1 0.25" radius="0.04" color="#000"></a-sphere>

  <!-- Nose (orange cone — carrot!) -->
  <a-cone position="0 2 0.3" rotation="-90 0 0" radius-bottom="0.05" height="0.3" color="#FF6600"></a-cone>

  <!-- Hat (black cylinder + disc) -->
  <a-cylinder position="0 2.35 0" radius="0.15" height="0.25" color="#111"></a-cylinder>
  <a-cylinder position="0 2.23 0" radius="0.25" height="0.03" color="#111"></a-cylinder>

</a-entity>
```

---

### 📚 Official A-Frame Docs for Part 9

| Topic | Link |
|-------|------|
| Entity (Grouping Objects) | https://aframe.io/docs/1.7.0/core/entity.html |
| Cone Primitive | https://aframe.io/docs/1.7.0/primitives/a-cone.html |
| Geometry Component | https://aframe.io/docs/1.7.0/components/geometry.html |
| All Primitives List | https://aframe.io/docs/1.7.0/introduction/html-and-primitives.html |

---

<a name="part-10"></a>

## 🎨 PART 10 — Import 3D Models from Tinkercad 🟡

### 🎯 What is Tinkercad?

**Tinkercad** is a free, browser-based 3D design tool by Autodesk. Think of it like **Paint 3D** but way more powerful — you can create robots, characters, buildings, anything!

**Real-Life Example:** Like building with digital LEGO blocks, then exporting your creation to put it in your VR world! 🏗️➡️🥽

**Link:** https://www.tinkercad.com/ (sign up for free)

---

### 🔧 Step-by-Step: Tinkercad → VR

#### Step 1: Design in Tinkercad

1. Go to https://www.tinkercad.com/
2. Sign up / Log in
3. Click **"Create new design"**
4. Build your 3D object (drag shapes, combine them)

#### Step 2: Export as GLB

1. Click **"Export"** button (top right corner)
2. Choose **".GLB"** format ← **IMPORTANT: Must be GLB!**
3. Download the file (e.g., `robot.glb`)

> ⚠️ **Why GLB?** GLB (GL Binary) is the best 3D format for the web. It's like how JPEG is the standard for photos — GLB is the standard for 3D models on the web. A-Frame supports it natively!

#### Step 3: Upload to GitHub

1. Go to your GitHub repo
2. Click **"Add file"** → **"Upload files"**
3. Create a `models/` folder and upload your `.glb` file
4. Commit changes

Your file URL will be:

```
https://raw.githubusercontent.com/YourUsername/your-repo/main/models/robot.glb
```

> 💡 **To get the raw URL:** Click on the file in GitHub → Click **"Raw"** button → Copy the URL from the browser bar.

---

### 📝 CODE CHUNK 9A: Import a Tinkercad Model (From Your GitHub)

📍 **Where to paste:** Inside `<a-scene>`.

```html
<!-- ======================================= -->
<!-- IMPORT 3D MODEL FROM TINKERCAD          -->
<!-- Upload your .glb file to GitHub first   -->
<!-- ======================================= -->

<a-scene>

  <!-- Load the 3D model file (like downloading a game asset) -->
  <a-assets>
    <a-asset-item
      id="my-tinkercad-model"
      src="models/robot.glb">
    </a-asset-item>
  </a-assets>

  <!-- Place the 3D model in the scene -->
  <!-- gltf-model="#my-tinkercad-model" loads the model we saved in assets -->
  <a-entity
    gltf-model="#my-tinkercad-model"
    position="0 0 -3"
    rotation="0 0 0"
    scale="1 1 1">
  </a-entity>

  <a-plane position="0 0 -4" rotation="-90 0 0" width="10" height="10" color="#7BC8A4"></a-plane>
  <a-sky color="#87CEEB"></a-sky>

</a-scene>
```

---

### 📝 CODE CHUNK 9B: Common Model Adjustments

Your model might be too big, too small, or facing the wrong way. Here's how to fix it:

```html
<!-- ======================================= -->
<!-- MODEL ADJUSTMENTS CHEAT SHEET           -->
<!-- ======================================= -->

<!-- Model too BIG? Scale it DOWN -->
<!-- scale="0.1 0.1 0.1" means 10% of original size -->
<a-entity
  gltf-model="#my-tinkercad-model"
  scale="0.1 0.1 0.1"
  position="0 0 -3">
</a-entity>

<!-- Model too SMALL? Scale it UP -->
<!-- scale="5 5 5" means 5x bigger -->
<a-entity
  gltf-model="#my-tinkercad-model"
  scale="5 5 5"
  position="0 0 -3">
</a-entity>

<!-- Model facing WRONG direction? Rotate it -->
<!-- Try rotating 90 or 180 on Y axis -->
<a-entity
  gltf-model="#my-tinkercad-model"
  rotation="0 180 0"
  position="0 0 -3">
</a-entity>

<!-- Model floating above ground? Move it DOWN -->
<!-- Adjust Y position (second number) -->
<a-entity
  gltf-model="#my-tinkercad-model"
  position="0 -0.5 -3">
</a-entity>

<!-- Model spinning continuously (cool display!) -->
<a-entity
  gltf-model="#my-tinkercad-model"
  position="0 1 -3"
  animation="property: rotation; to: 0 360 0; loop: true; dur: 5000">
</a-entity>
```

#### Scale Cheat Sheet:

| Scale Value | What It Does | When To Use |
|-------------|-------------|-------------|
| `scale="0.01 0.01 0.01"` | 1% of original size | Model is HUGE |
| `scale="0.1 0.1 0.1"` | 10% of original size | Model is big |
| `scale="1 1 1"` | Original size (default) | Looks right already |
| `scale="5 5 5"` | 5x bigger | Model is small |
| `scale="10 10 10"` | 10x bigger | Model is tiny |
| `scale="1 2 1"` | Stretched tall | Make it taller only |

---

### 📝 CODE CHUNK 9C: Import Multiple Models

```html
<!-- ======================================= -->
<!-- MULTIPLE 3D MODELS IN ONE SCENE         -->
<!-- ======================================= -->

<a-assets>
  <a-asset-item id="robot" src="models/robot.glb"></a-asset-item>
  <a-asset-item id="car" src="models/car.glb"></a-asset-item>
  <a-asset-item id="house" src="models/house.glb"></a-asset-item>
</a-assets>

<!-- Robot on the left -->
<a-entity
  gltf-model="#robot"
  position="-3 0 -5"
  scale="0.5 0.5 0.5">
</a-entity>

<!-- Car in the center -->
<a-entity
  gltf-model="#car"
  position="0 0 -5"
  scale="0.3 0.3 0.3">
</a-entity>

<!-- House on the right -->
<a-entity
  gltf-model="#house"
  position="3 0 -5"
  scale="0.2 0.2 0.2">
</a-entity>
```

---

### 📝 CODE CHUNK 9D: Load Free Models from URLs

You can also load models from direct URLs (no download needed):

```html
<!-- ======================================= -->
<!-- LOAD 3D MODEL FROM A DIRECT URL         -->
<!-- No need to download first!              -->
<!-- ======================================= -->

<a-assets>
  <!-- Direct URL to a .glb file hosted somewhere online -->
  <a-asset-item
    id="duck"
    src="https://raw.githubusercontent.com/KhronosGroup/glTF-Sample-Models/main/2.0/Duck/glTF-Binary/Duck.glb">
  </a-asset-item>
</a-assets>

<!-- Place the duck in the scene -->
<a-entity
  gltf-model="#duck"
  position="0 0 -3"
  scale="0.5 0.5 0.5">
</a-entity>
```

> 💡 **Where to find free 3D models:**
>
> - **Sketchfab** — https://sketchfab.com/search?type=models&features=downloadable
> - **Tinkercad** — https://www.tinkercad.com/ (make your own!)
> - **Poly Pizza** — https://poly.pizza/ (free low-poly models)
> - **glTF Sample Models** — https://github.com/KhronosGroup/glTF-Sample-Models (test models)

---

### 📚 Official A-Frame Docs for Part 10

| Topic | Link |
|-------|------|
| GLTF Model Component | https://aframe.io/docs/1.7.0/components/gltf-model.html |
| 3D Models Guide | https://aframe.io/docs/1.7.0/introduction/models.html |
| Asset Management System | https://aframe.io/docs/1.7.0/core/asset-management-system.html |

---

<a name="part-11"></a>

## 🎮 PART 11 — Meta Quest 3s Controllers 🔴

> ⚠️ **This is where it gets more advanced!** Parts 2-10 were just HTML attributes. Now we're adding VR controller support — the code is more complex but still copy-paste friendly!

### 🎯 What Are We Adding?

**Think of controllers like lightsabers in Star Wars:**

- They shoot laser beams 🔦
- You point at things and press trigger to interact
- They track your real hand movements in VR

**Real-Life Example:** It's like using a TV remote, but instead of pressing buttons to change channels, you point a laser at 3D objects and click to interact! 📺➡️🎮

#### 🎮 Meta Quest 3s Controller Buttons:

```
    [  Thumbstick  ]     ← Move around (like WASD on keyboard)
    [   A / B      ]     ← Action buttons (right hand)
    [   X / Y      ]     ← Action buttons (left hand)
    [ TRIGGER 🔫  ]     ← Index finger button — MAIN CLICK (we use this!)
    [ GRIP   ✊   ]     ← Middle finger button — Grab objects
```

---

### 📝 CODE CHUNK 10: Camera + Controllers

📍 **Where to paste:** Inside `<a-scene>`, at the **TOP** (before your objects).

```html
<!-- ======================================= -->
<!-- CAMERA + CONTROLLER RIG                 -->
<!-- Paste INSIDE <a-scene> at the TOP       -->
<!-- ======================================= -->

<!-- "rig" = Your VR body (head + both hands) -->
<!-- Think of it like your character in a video game -->
<a-entity id="rig">

  <!-- VR Camera = Your Eyes/Head -->
  <!-- position="0 1.6 0" = 1.6 meters tall (average human eye height) -->
  <!-- look-controls = Move your real head to look around -->
  <!-- Think: This is your first-person POV like in Call of Duty -->
  <a-entity
    camera
    position="0 1.6 0"
    look-controls>
  </a-entity>

  <!-- LEFT CONTROLLER = Your Left Hand in VR -->
  <a-entity
    id="leftController"
    meta-touch-controls="hand: left"
    laser-controls="hand: left"
    raycaster="objects: .clickable; far: 20"
    line="color: cyan">
  </a-entity>

  <!-- RIGHT CONTROLLER = Your Right Hand in VR -->
  <a-entity
    id="rightController"
    meta-touch-controls="hand: right"
    laser-controls="hand: right"
    raycaster="objects: .clickable; far: 20"
    line="color: magenta">
  </a-entity>

</a-entity>
```

---

### 🧠 Code Explanation (Line by Line)

#### 🎥 Camera (Your Eyes):

```html
<a-entity camera position="0 1.6 0" look-controls>
```

| Part | What It Does | Example |
|------|-------------|---------|
| `camera` | Makes this your viewpoint (your eyes) | First-person view in COD |
| `position="0 1.6 0"` | Eye height at 1.6m (about 5'3") | Average human standing height |
| `look-controls` | Moving your head moves the camera | Looking around in real life |

#### 🕹️ Controller Attributes:

| Attribute | What It Does | Real-Life Example |
|-----------|-------------|-------------------|
| `meta-touch-controls="hand: left"` | Connects to your physical Quest controller | Like pairing AirPods to your iPhone 📱 |
| `laser-controls="hand: left"` | Shows a visible laser beam | Like a laser pointer in a classroom presentation 🔴 |
| `raycaster="objects: .clickable; far: 20"` | Detects objects the laser hits (only `.clickable` ones, up to 20 units away) | Like a motion sensor that detects movement 📡 |
| `line="color: cyan"` | Color of the laser beam | Left = cyan (light blue), Right = magenta (pink) |

---

### 📚 Official A-Frame Docs for Part 11

| Topic | Link |
|-------|------|
| Camera Component | https://aframe.io/docs/1.7.0/components/camera.html |
| Meta Touch Controls | https://aframe.io/docs/1.7.0/components/meta-touch-controls.html |
| Laser Controls | https://aframe.io/docs/1.7.0/components/laser-controls.html |
| Raycaster | https://aframe.io/docs/1.7.0/components/raycaster.html |
| Look Controls | https://aframe.io/docs/1.7.0/components/look-controls.html |
| Interactions & Controllers Guide | https://aframe.io/docs/1.7.0/introduction/interactions-and-controllers.html |

---

<a name="part-12"></a>

## 🖱️ PART 12 — Make Objects Clickable 🔴

### 🎯 What Does "Clickable" Mean?

**Think of it like Instagram posts:**

- A regular post → You can scroll past it
- A post with a "❤️ Like" button → You can tap it
- `class="clickable"` → Tells VR "Hey, this object can be clicked!"

**Without `class="clickable"`:** Your laser goes through the object like a ghost 👻
**With `class="clickable"`:** Your laser stops on it and you can interact ✅

---

### 📝 CODE CHUNK 11: Clickable Objects

📍 **Where to paste:** Replace your existing scene objects inside `<a-scene>` (after the controller rig from Part 11).

```html
<!-- ======================================= -->
<!-- CLICKABLE SCENE OBJECTS                 -->
<!-- Paste INSIDE <a-scene> after controllers -->
<!-- ======================================= -->

<!-- class="clickable" = Laser can interact with this object -->
<!-- Without it, the laser passes through like a ghost! 👻 -->

<!-- Clickable Box ✅ -->
<a-box
  position="-1 0.5 -3"
  rotation="0 45 0"
  color="#4CC3D9"
  class="clickable">
</a-box>

<!-- Clickable Sphere ✅ -->
<a-sphere
  position="0 1.25 -5"
  radius="1.25"
  color="#EF2D5E"
  class="clickable">
</a-sphere>

<!-- Clickable Cylinder ✅ -->
<a-cylinder
  position="1 0.75 -3"
  radius="0.5"
  height="1.5"
  color="#FFC65D"
  class="clickable">
</a-cylinder>

<!-- NOT Clickable — Laser passes through (it's just the floor) -->
<a-plane
  position="0 0 -4"
  rotation="-90 0 0"
  width="4"
  height="4"
  color="#7BC8A4">
</a-plane>

<!-- Sky (background) — Not clickable -->
<a-sky color="#ECECEC"></a-sky>
```

---

### 🧠 Why Do We Need `class="clickable"`?

Remember in **PART 11** we wrote this on the controller:

```html
raycaster="objects: .clickable; far: 20"
```

This tells the raycaster:

- **`objects: .clickable`** → "Only detect objects that have `class='clickable'`"
- **`far: 20`** → "Laser reaches up to 20 units (meters)"

> 💡 **Think of it like a bouncer at a nightclub:** Only people on the VIP list (with `class="clickable"`) get in! 🚪🕺

---

### 📚 Official A-Frame Docs for Part 12

| Topic | Link |
|-------|------|
| Raycaster (Object Filtering) | https://aframe.io/docs/1.7.0/components/raycaster.html |
| Interactions Guide | https://aframe.io/docs/1.7.0/introduction/interactions-and-controllers.html |

---

<a name="part-13"></a>

## 🎨 PART 13 — Interaction Script (Color Change on Trigger) 🔴

### 🎯 What Does This Do?

When you point your laser at an object and press the **trigger button** → the object changes to a random color!

**Real-Life Example:** Like mood rings that change color when you touch them! 💍✨ Or like TikTok filters — tap the screen and the filter changes!

> ⚠️ **This is JavaScript!** Don't worry — just copy-paste the whole chunk. You don't need to understand every line.

---

### 📝 CODE CHUNK 12: Color Change Script

📍 **Where to paste:** Inside `<a-scene>`, at the very **BOTTOM** (just before `</a-scene>`).

```html
<!-- ======================================= -->
<!-- INTERACTION SCRIPT — COLOR CHANGE       -->
<!-- Paste INSIDE <a-scene> at the BOTTOM    -->
<!-- Just before </a-scene>                  -->
<!-- ======================================= -->

<script>
  // -----------------------------------------------
  // STEP 1: Create a custom "superpower" for objects
  // Think: Like creating a custom Snapchat filter
  // -----------------------------------------------
  AFRAME.registerComponent('click-change-color', {
    init: function () {

      // STEP 2: Listen for clicks on this object
      // Think: Like a doorbell waiting for someone to press it 🚪🔔
      this.el.addEventListener('click', () => {

        // STEP 3: Generate a random color and apply it
        // Think: Like shaking a spray paint can and spraying 🎨
        const randomColor = '#' + Math.floor(Math.random() * 16777215).toString(16).padStart(6, '0');
        this.el.setAttribute('color', randomColor);

      });
    }
  });

  // -----------------------------------------------
  // STEP 4: Wait for the page to fully load
  // Think: Like waiting for a game to finish loading before playing
  // -----------------------------------------------
  document.addEventListener('DOMContentLoaded', function () {

    // STEP 5: Find ALL clickable objects in the scene
    const clickableObjects = document.querySelectorAll('.clickable');

    // STEP 6: Give each clickable object the color-change superpower
    clickableObjects.forEach(function (obj) {
      obj.setAttribute('click-change-color', '');
    });

  });
</script>
```

---

### 🧠 Code Explanation (Super Detailed)

#### The Flow — What Happens When You Click:

```
1. 🔦 Point laser at object
2. 🔫 Press trigger button on Quest controller
3. 👂 Script hears "click" event
4. 🎲 Generates random color (#a3f2c1)
5. 🎨 Changes object's color
6. ✨ Object turns a new color instantly!
```

#### Breaking Down the Random Color Generator:

```javascript
'#' + Math.floor(Math.random() * 16777215).toString(16).padStart(6, '0')
```

Let's break this apart step by step:

| Step | Code | What Happens | Example |
|------|------|-------------|---------|
| 1 | `Math.random()` | Random number 0-1 | `0.846372` |
| 2 | `* 16777215` | Multiply for full color range | `14193826.4` |
| 3 | `Math.floor()` | Remove decimals | `14193826` |
| 4 | `.toString(16)` | Convert to hex (color code) | `d8a142` |
| 5 | `.padStart(6, '0')` | Make sure it's always 6 digits | `d8a142` |
| 6 | `'#' +` | Add the hash symbol | `#d8a142` |

> 💡 **Why 16777215?** Because 256 red × 256 green × 256 blue = 16,777,216 possible colors! That's every color your screen can show!

#### What Does `AFRAME.registerComponent()` Do?

Think of it like this:

- **A-Frame has built-in powers** (position, color, rotation)
- **`registerComponent`** lets you create **custom powers** (like creating a custom TikTok effect)
- We created a power called `'click-change-color'` that changes color on click

---

### 📚 Official A-Frame Docs for Part 13

| Topic | Link |
|-------|------|
| Writing a Component | https://aframe.io/docs/1.7.0/introduction/writing-a-component.html |
| JavaScript Events & DOM APIs | https://aframe.io/docs/1.7.0/introduction/javascript-events-dom-apis.html |
| Component API | https://aframe.io/docs/1.7.0/core/component.html |

---

<a name="deployment"></a>

## 🚀 PART 14 — Deploy: GitHub Pages + TinyURL to Meta Quest 3s

### Step 1: Upload to GitHub

1. Go to **GitHub.com** and Sign in
2. Click **"New"** (green button) to create a new repository
3. Name it: `vr-workshop` (or whatever you like)
4. Make it **Public**
5. Check **"Add a README file"**
6. Click **"Create Repository"**
7. Click **"Add file"** then **"Upload files"**
8. Drag your `index.html` (and `models/`, `textures/`, `audio/` folders if you have them)
9. Click **"Commit changes"**

---

### Step 2: Enable GitHub Pages

1. Go to your repo's **Settings** tab (gear icon)
2. In the left sidebar, click **"Pages"**
3. Under **"Branch"**:
   - Select **`main`** branch
   - Select **`/ (root)`** folder
   - Click **"Save"**
4. **Wait 1-2 minutes**
5. Your link will appear at the top:

```
https://YourUsername.github.io/vr-workshop/
```

> 💡 **If it says 404:** Wait another minute and refresh. GitHub Pages takes 1-5 minutes to deploy the first time.

---

### Step 3: Shorten with TinyURL

1. Copy your GitHub Pages link
2. Go to https://tinyurl.com/
3. Paste your link
4. *(Optional)* Add a custom alias like `vr-workshop-2026`
5. Click **"Make TinyURL!"**
6. You get a short link:

```
https://tinyurl.com/vr-workshop-2026
```

> 💡 **Why TinyURL?** GitHub Pages URLs are long and hard to type on Quest. TinyURL makes it easy! Like using a short link instead of a full address.

---

### Step 4: Open on Meta Quest 3s

#### Option A: Type the Link

1. Put on your Quest headset
2. Open the **Browser** app
3. Type the TinyURL (e.g., `tinyurl.com/vr-workshop-2026`)
4. Press Enter

#### Option B: Send Link to Phone (SMART!)

1. Send the TinyURL to yourself on **WhatsApp/Messenger**
2. Open it on your phone
3. Quest may auto-detect it and ask "Open in VR?"
4. Click YES!

#### Option C: QR Code (EASIEST!)

1. Go to any QR generator (e.g., https://www.qr-code-generator.com/)
2. Paste your TinyURL
3. Download the QR code
4. Scan it with Quest browser and it opens automatically!

---

### Step 5: Test in VR

1. Click the **"Enter VR"** button (bottom right of the page)
2. Pick up your controllers
3. **YOU'RE IN!** 🎉

#### Verification Checklist:

| Test | Expected Result |
|------|----------------|
| Look around | Camera follows your head movement |
| Hold controllers | See cyan (left) and magenta (right) lasers |
| Point at clickable object | Laser stops on the object |
| Press trigger | Object changes color (if script is added) |

---

<a name="part-15"></a>

## 🧩 PART 15 — Advanced Copy-Paste Code Chunks

> **⚠️ These are advanced features.** They use JavaScript and complex A-Frame components. You don't need to understand every line — just **copy-paste** the chunk into your project and it works!
>
> **How to use this section:**
> 1. Pick a feature you want
> 2. Copy the entire code chunk
> 3. Paste it into your `index.html` where indicated
> 4. Done! ✅

---

### 🧩 CHUNK A: Thumbstick Movement (Walk Around in VR)

By default, you're stuck in one place in A-Frame. This code lets you **walk around** using the left thumbstick — like WASD movement in a PC game!

📍 **Where to paste:** Replace the camera rig section inside `<a-scene>`.

> ⚠️ **IMPORTANT:** You MUST add this extra script in your `<head>` tag (BEFORE the A-Frame script):
> ```html
> <script src="https://cdn.jsdelivr.net/gh/c-frame/aframe-extras@7.5.0/dist/aframe-extras.min.js"></script>
> ```

```html
<!-- ======================================= -->
<!-- 🧩 THUMBSTICK MOVEMENT                  -->
<!-- Walk around using left controller stick  -->
<!-- Replace your existing camera rig         -->
<!-- ======================================= -->

<!-- Movement rig — the whole thing moves when you walk -->
<a-entity
  id="rig"
  movement-controls="controls: gamepad; speed: 0.3"
  position="0 0 0">

  <!-- Your eyes -->
  <a-entity
    camera
    position="0 1.6 0"
    look-controls="pointerLockEnabled: false">
  </a-entity>

  <!-- Left hand — controls movement via thumbstick automatically -->
  <a-entity
    id="leftController"
    meta-touch-controls="hand: left"
    laser-controls="hand: left"
    raycaster="objects: .clickable; far: 20"
    line="color: cyan">
  </a-entity>

  <!-- Right hand -->
  <a-entity
    id="rightController"
    meta-touch-controls="hand: right"
    laser-controls="hand: right"
    raycaster="objects: .clickable; far: 20"
    line="color: magenta">
  </a-entity>

</a-entity>
```

---

### 🧩 CHUNK B: Teleportation (Point and Click to Move)

Instead of walking, point your controller at the ground and click to **teleport** there instantly! Like fast travel in Skyrim.

📍 **Where to paste:** Replace your camera rig section.

> ⚠️ **IMPORTANT:** Requires `aframe-extras` script in `<head>` (same as Chunk A). Also make sure your floor has `class="ground"`.

```html
<!-- ======================================= -->
<!-- 🧩 TELEPORTATION                        -->
<!-- Point at floor + click = teleport there  -->
<!-- ======================================= -->

<a-entity id="rig" position="0 0 0">

  <!-- Camera (your eyes) -->
  <a-entity camera position="0 1.6 0" look-controls></a-entity>

  <!-- Left Controller with TELEPORT -->
  <a-entity
    id="leftController"
    meta-touch-controls="hand: left"
    laser-controls="hand: left"
    raycaster="objects: .clickable, .ground; far: 20"
    line="color: cyan"
    teleport-controls="cameraRig: #rig; teleportOrigin: [camera]; type: line; button: trigger; curveShootingSpeed: 10; landingNormal: 0 1 0; defaultPlaneSize: 100">
  </a-entity>

  <!-- Right Controller (regular laser) -->
  <a-entity
    id="rightController"
    meta-touch-controls="hand: right"
    laser-controls="hand: right"
    raycaster="objects: .clickable; far: 20"
    line="color: magenta">
  </a-entity>

</a-entity>

<!-- Make your floor teleportable by adding class="ground" -->
<a-plane
  position="0 0 -4"
  rotation="-90 0 0"
  width="30" height="30"
  color="#7BC8A4"
  class="ground">
</a-plane>
```

---

### 🧩 CHUNK C: Grab Objects with Grip Button

Pick up objects with the grip button (middle finger) and drop them! Like picking up weapons in VR games.

📍 **Where to paste:** Add the `<script>` block inside `<a-scene>`, at the bottom.

```html
<!-- ======================================= -->
<!-- 🧩 GRAB OBJECTS WITH GRIP BUTTON        -->
<!-- Hold grip to grab, release to drop      -->
<!-- ======================================= -->

<script>
  AFRAME.registerComponent('grabbable', {
    init: function () {
      this.el.classList.add('clickable');
      this.grabbed = false;
      this.grabber = null;
    }
  });

  AFRAME.registerComponent('grab-controls', {
    schema: { hand: { type: 'string', default: 'right' } },

    init: function () {
      var el = this.el;
      var self = this;
      self.grabbedEl = null;

      // When grip button is pressed
      el.addEventListener('gripdown', function () {
        var raycaster = el.components.raycaster;
        if (!raycaster) return;
        var intersections = raycaster.intersections;
        if (intersections.length === 0) return;

        var target = intersections[0].object.el;
        if (!target || !target.hasAttribute('grabbable')) return;

        // Grab it! (attach to controller)
        self.grabbedEl = target;
        target.setAttribute('position', '0 0 -0.5');
        el.appendChild(target);
      });

      // When grip button is released
      el.addEventListener('gripup', function () {
        if (!self.grabbedEl) return;

        // Drop it! (put back in scene)
        var worldPos = new THREE.Vector3();
        self.grabbedEl.object3D.getWorldPosition(worldPos);

        var scene = document.querySelector('a-scene');
        scene.appendChild(self.grabbedEl);
        self.grabbedEl.setAttribute('position', worldPos);
        self.grabbedEl = null;
      });
    }
  });
</script>
```

**How to use it:** Add `grab-controls` to your controller and `grabbable` to objects:

```html
<!-- Controller with grab ability -->
<a-entity
  id="rightController"
  meta-touch-controls="hand: right"
  laser-controls="hand: right"
  raycaster="objects: .clickable; far: 5"
  line="color: magenta"
  grab-controls="hand: right">
</a-entity>

<!-- Grabbable objects -->
<a-box position="0 1 -3" color="#4CC3D9" grabbable></a-box>
<a-sphere position="1 1 -3" color="#EF2D5E" grabbable></a-sphere>
```

---

### 🧩 CHUNK D: Spawn Objects on Click (Object Creator)

Every time you press the trigger, a new random-colored box appears where your laser is pointing! Like placing blocks in Minecraft.

📍 **Where to paste:** Add the `<script>` block inside `<a-scene>`, at the bottom.

```html
<!-- ======================================= -->
<!-- 🧩 SPAWN OBJECTS ON TRIGGER CLICK       -->
<!-- Click trigger = new box appears          -->
<!-- ======================================= -->

<script>
  AFRAME.registerComponent('spawn-on-click', {
    init: function () {
      var el = this.el;

      el.addEventListener('triggerdown', function () {
        var raycaster = el.components.raycaster;
        if (!raycaster) return;

        var intersections = raycaster.intersections;
        var spawnPos;

        if (intersections.length > 0) {
          // Spawn where laser hits
          spawnPos = intersections[0].point;
        } else {
          // Spawn 3 meters in front of controller
          var worldPos = new THREE.Vector3(0, 0, -3);
          el.object3D.localToWorld(worldPos);
          spawnPos = worldPos;
        }

        // Create a random-colored box
        var newBox = document.createElement('a-box');
        var randomColor = '#' + Math.floor(Math.random() * 16777215).toString(16).padStart(6, '0');
        newBox.setAttribute('position', spawnPos.x + ' ' + spawnPos.y + ' ' + spawnPos.z);
        newBox.setAttribute('color', randomColor);
        newBox.setAttribute('scale', '0.3 0.3 0.3');
        newBox.setAttribute('class', 'clickable');
        newBox.setAttribute('click-change-color', '');

        document.querySelector('a-scene').appendChild(newBox);
      });
    }
  });
</script>
```

**How to use it:** Add `spawn-on-click` to a controller:

```html
<a-entity
  id="leftController"
  meta-touch-controls="hand: left"
  laser-controls="hand: left"
  raycaster="objects: .clickable; far: 20"
  line="color: cyan"
  spawn-on-click>
</a-entity>
```

---

### 🧩 CHUNK E: Object Highlight on Hover (Glow Effect)

Objects glow/highlight when you point your laser at them — like hover effects on websites!

📍 **Where to paste:** Add the `<script>` block inside `<a-scene>`, at the bottom.

```html
<!-- ======================================= -->
<!-- 🧩 GLOW/HIGHLIGHT ON HOVER             -->
<!-- Objects light up when laser points      -->
<!-- ======================================= -->

<script>
  AFRAME.registerComponent('hover-highlight', {
    init: function () {
      var el = this.el;
      var originalColor;

      // When laser enters this object
      el.addEventListener('mouseenter', function () {
        originalColor = el.getAttribute('color') || '#FFFFFF';
        el.setAttribute('color', '#FFD700');  // Gold highlight
        el.setAttribute('scale', '1.1 1.1 1.1');  // Slightly bigger
      });

      // When laser leaves this object
      el.addEventListener('mouseleave', function () {
        el.setAttribute('color', originalColor);
        el.setAttribute('scale', '1 1 1');  // Back to normal
      });
    }
  });

  // Auto-apply to all clickable objects
  document.addEventListener('DOMContentLoaded', function () {
    document.querySelectorAll('.clickable').forEach(function (obj) {
      obj.setAttribute('hover-highlight', '');
    });
  });
</script>
```

> 💡 This auto-applies to all objects with `class="clickable"` — no extra setup needed!

---

### 🧩 CHUNK F: Scale Objects (Grow/Shrink on A/B Buttons)

Press A button to make the targeted object bigger, B button to make it smaller!

📍 **Where to paste:** Add the `<script>` block inside `<a-scene>`, at the bottom.

```html
<!-- ======================================= -->
<!-- 🧩 SCALE OBJECTS WITH A/B BUTTONS       -->
<!-- A = grow bigger | B = shrink smaller    -->
<!-- ======================================= -->

<script>
  AFRAME.registerComponent('scale-controls', {
    init: function () {
      var el = this.el;

      // A button = grow
      el.addEventListener('abuttondown', function () {
        var raycaster = el.components.raycaster;
        if (!raycaster || raycaster.intersections.length === 0) return;
        var target = raycaster.intersections[0].object.el;
        var currentScale = target.getAttribute('scale') || { x: 1, y: 1, z: 1 };
        var newScale = currentScale.x + 0.2;
        target.setAttribute('scale', newScale + ' ' + newScale + ' ' + newScale);
      });

      // B button = shrink
      el.addEventListener('bbuttondown', function () {
        var raycaster = el.components.raycaster;
        if (!raycaster || raycaster.intersections.length === 0) return;
        var target = raycaster.intersections[0].object.el;
        var currentScale = target.getAttribute('scale') || { x: 1, y: 1, z: 1 };
        var newScale = Math.max(0.1, currentScale.x - 0.2);  // Don't go below 0.1
        target.setAttribute('scale', newScale + ' ' + newScale + ' ' + newScale);
      });
    }
  });
</script>
```

**How to use it:** Add `scale-controls` to right controller:

```html
<a-entity
  id="rightController"
  meta-touch-controls="hand: right"
  laser-controls="hand: right"
  raycaster="objects: .clickable; far: 20"
  line="color: magenta"
  scale-controls>
</a-entity>
```

---

### 🧩 CHUNK G: Delete Objects (X Button)

Press X button while pointing at an object to delete it! Like erasing in Minecraft.

📍 **Where to paste:** Add the `<script>` block inside `<a-scene>`, at the bottom.

```html
<!-- ======================================= -->
<!-- 🧩 DELETE OBJECTS WITH X BUTTON         -->
<!-- Point laser + press X = object removed  -->
<!-- ======================================= -->

<script>
  AFRAME.registerComponent('delete-controls', {
    init: function () {
      var el = this.el;

      el.addEventListener('xbuttondown', function () {
        var raycaster = el.components.raycaster;
        if (!raycaster || raycaster.intersections.length === 0) return;

        var target = raycaster.intersections[0].object.el;
        if (target && target.classList.contains('clickable')) {
          // Shrink animation then remove
          target.setAttribute('animation', 'property: scale; to: 0 0 0; dur: 300');
          setTimeout(function () {
            target.parentNode.removeChild(target);
          }, 300);
        }
      });
    }
  });
</script>
```

**How to use it:** Add `delete-controls` to left controller:

```html
<a-entity
  id="leftController"
  meta-touch-controls="hand: left"
  laser-controls="hand: left"
  raycaster="objects: .clickable; far: 20"
  line="color: cyan"
  delete-controls>
</a-entity>
```

---

### 🧩 CHUNK H: Proximity Trigger (Auto-action When Close)

Objects automatically do something when you get close to them — like automatic doors or proximity sensors!

📍 **Where to paste:** Add the `<script>` block inside `<a-scene>`, at the bottom.

```html
<!-- ======================================= -->
<!-- 🧩 PROXIMITY TRIGGER                    -->
<!-- Object reacts when player gets close    -->
<!-- ======================================= -->

<script>
  AFRAME.registerComponent('proximity-trigger', {
    schema: {
      distance: { type: 'number', default: 3 },
      color: { type: 'string', default: '#FF0000' }
    },

    init: function () {
      this.camera = document.querySelector('[camera]');
      this.originalColor = this.el.getAttribute('color') || '#FFFFFF';
      this.triggered = false;
    },

    tick: function () {
      if (!this.camera) return;

      var cameraPos = this.camera.object3D.getWorldPosition(new THREE.Vector3());
      var objectPos = this.el.object3D.getWorldPosition(new THREE.Vector3());
      var dist = cameraPos.distanceTo(objectPos);

      if (dist < this.data.distance && !this.triggered) {
        this.triggered = true;
        this.el.setAttribute('color', this.data.color);
        this.el.setAttribute('scale', '1.5 1.5 1.5');
      } else if (dist >= this.data.distance && this.triggered) {
        this.triggered = false;
        this.el.setAttribute('color', this.originalColor);
        this.el.setAttribute('scale', '1 1 1');
      }
    }
  });
</script>
```

**How to use it:** Add `proximity-trigger` to any object:

```html
<a-sphere
  position="0 1 -5"
  color="#4CC3D9"
  proximity-trigger="distance: 2; color: #FF0000">
</a-sphere>
```

---

### 🧩 CHUNK I: VR Info Panel (Billboard/Sign)

A floating info panel — great for instructions, labels, or menus!

📍 **Where to paste:** Inside `<a-scene>`.

```html
<!-- ======================================= -->
<!-- 🧩 VR INFO PANEL / BILLBOARD           -->
<!-- Floating panel for instructions          -->
<!-- ======================================= -->

<!-- Background panel -->
<a-entity position="0 2 -4">

  <!-- Dark background (semi-transparent) -->
  <a-plane
    width="3" height="1.5"
    material="color: #000; opacity: 0.8; transparent: true; side: double">
  </a-plane>

  <!-- Title -->
  <a-text
    value="VR Workshop"
    position="0 0.4 0.01"
    align="center"
    color="#FFD700"
    width="4">
  </a-text>

  <!-- Body text -->
  <a-text
    value="Point your laser at objects\nPress TRIGGER to change color\nUse THUMBSTICK to move"
    position="0 -0.1 0.01"
    align="center"
    color="#FFFFFF"
    width="3">
  </a-text>

</a-entity>
```

---

### 🧩 CHUNK J: Complete Advanced Scene (All Features Combined)

This is a **complete working file** with thumbstick movement, clickable objects, color change, hover highlight, and a 360° sky — all combined!

📍 **Copy this entire file** into your `index.html`:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>VR Workshop — Advanced Scene</title>
    <meta name="description" content="Advanced VR Workshop with Controllers">

    <!-- Extra features library (movement, teleport) -->
    <script src="https://cdn.jsdelivr.net/gh/c-frame/aframe-extras@7.5.0/dist/aframe-extras.min.js"></script>

    <!-- A-Frame VR Engine -->
    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
  </head>

  <body>
    <a-scene fog="type: linear; color: #87CEEB; near: 15; far: 50">

      <!-- ====== LOAD ALL ASSETS ====== -->
      <a-assets>
        <img id="wood" src="https://cdn.aframe.io/a-painter/images/wood.jpg">
        <img id="floor" src="https://cdn.aframe.io/a-painter/images/floor.jpg">
        <img id="sky-img" src="https://cdn.aframe.io/360-image-gallery-boilerplate/img/city.jpg">
      </a-assets>

      <!-- ====== LIGHTING ====== -->
      <a-light type="ambient" color="#BBB" intensity="0.6"></a-light>
      <a-light type="directional" color="#FFF" intensity="0.8" position="-1 2 1"></a-light>

      <!-- ====== CAMERA + CONTROLLERS WITH MOVEMENT ====== -->
      <a-entity
        id="rig"
        movement-controls="controls: gamepad; speed: 0.3"
        position="0 0 0">

        <a-entity camera position="0 1.6 0" look-controls></a-entity>

        <a-entity
          id="leftController"
          meta-touch-controls="hand: left"
          laser-controls="hand: left"
          raycaster="objects: .clickable; far: 20"
          line="color: cyan">
        </a-entity>

        <a-entity
          id="rightController"
          meta-touch-controls="hand: right"
          laser-controls="hand: right"
          raycaster="objects: .clickable; far: 20"
          line="color: magenta"
          scale-controls>
        </a-entity>

      </a-entity>

      <!-- ====== INFO PANEL ====== -->
      <a-entity position="0 2.5 -4">
        <a-plane width="4" height="1.2" material="color: #111; opacity: 0.85; transparent: true"></a-plane>
        <a-text value="VR Workshop — Advanced Demo" position="0 0.3 0.01" align="center" color="#FFD700" width="5"></a-text>
        <a-text value="TRIGGER: change color | A/B: scale | Thumbstick: walk" position="0 -0.15 0.01" align="center" color="#FFF" width="4"></a-text>
      </a-entity>

      <!-- ====== CLICKABLE OBJECTS ====== -->
      <a-box position="-2 0.5 -5" src="#wood" class="clickable"
        animation__spin="property: rotation; to: 0 360 0; loop: true; dur: 6000"></a-box>

      <a-sphere position="0 1.25 -6" radius="1" color="#EF2D5E" class="clickable"
        animation="property: position; to: 0 2 -6; dir: alternate; loop: true; dur: 1500"></a-sphere>

      <a-cylinder position="2 0.75 -5" radius="0.5" height="1.5" color="#FFC65D" class="clickable"
        animation="property: scale; to: 1.2 1.2 1.2; dir: alternate; loop: true; dur: 900"></a-cylinder>

      <a-box position="-4 0.5 -7" color="#9B59B6"
        material="metalness: 0.8; roughness: 0.2" class="clickable"></a-box>

      <a-sphere position="4 1 -7" radius="0.8"
        material="color: #3498DB; metalness: 1; roughness: 0" class="clickable"></a-sphere>

      <!-- ====== HOUSE ====== -->
      <a-entity position="-6 0 -10" class="clickable">
        <a-box position="0 1 0" width="3" height="2" depth="3" color="#8B4513"></a-box>
        <a-cone position="0 2.5 0" radius-bottom="2.2" height="1.5" color="#DC143C"></a-cone>
        <a-box position="0 0.5 1.51" width="0.8" height="1.5" depth="0.1" color="#654321"></a-box>
      </a-entity>

      <!-- ====== TREE ====== -->
      <a-entity position="6 0 -8">
        <a-cylinder position="0 0.75 0" radius="0.2" height="1.5" color="#8B4513"></a-cylinder>
        <a-sphere position="0 2 0" radius="1" color="#228B22"></a-sphere>
        <a-sphere position="0.5 1.8 0" radius="0.7" color="#32CD32"></a-sphere>
        <a-sphere position="-0.5 1.8 0" radius="0.7" color="#32CD32"></a-sphere>
      </a-entity>

      <!-- ====== ENVIRONMENT ====== -->
      <a-plane position="0 0 -10" rotation="-90 0 0" width="40" height="40" src="#floor"></a-plane>
      <a-sky src="#sky-img"></a-sky>

      <!-- ====== ALL SCRIPTS ====== -->
      <script>
        // --- Color change on click ---
        AFRAME.registerComponent('click-change-color', {
          init: function () {
            this.el.addEventListener('click', function () {
              var c = '#' + Math.floor(Math.random() * 16777215).toString(16).padStart(6, '0');
              this.setAttribute('color', c);
            });
          }
        });

        // --- Hover highlight ---
        AFRAME.registerComponent('hover-highlight', {
          init: function () {
            var el = this.el;
            var orig;
            el.addEventListener('mouseenter', function () {
              orig = el.getAttribute('color') || '#FFF';
              el.setAttribute('scale', '1.1 1.1 1.1');
            });
            el.addEventListener('mouseleave', function () {
              el.setAttribute('scale', '1 1 1');
            });
          }
        });

        // --- Scale with A/B buttons ---
        AFRAME.registerComponent('scale-controls', {
          init: function () {
            var el = this.el;
            el.addEventListener('abuttondown', function () {
              var r = el.components.raycaster;
              if (!r || r.intersections.length === 0) return;
              var t = r.intersections[0].object.el;
              var s = t.getAttribute('scale') || { x: 1, y: 1, z: 1 };
              var n = s.x + 0.2;
              t.setAttribute('scale', n + ' ' + n + ' ' + n);
            });
            el.addEventListener('bbuttondown', function () {
              var r = el.components.raycaster;
              if (!r || r.intersections.length === 0) return;
              var t = r.intersections[0].object.el;
              var s = t.getAttribute('scale') || { x: 1, y: 1, z: 1 };
              var n = Math.max(0.1, s.x - 0.2);
              t.setAttribute('scale', n + ' ' + n + ' ' + n);
            });
          }
        });

        // --- Auto-apply to all clickable ---
        document.addEventListener('DOMContentLoaded', function () {
          document.querySelectorAll('.clickable').forEach(function (o) {
            o.setAttribute('click-change-color', '');
            o.setAttribute('hover-highlight', '');
          });
        });
      </script>

    </a-scene>
  </body>
</html>
```

---

### 🧩 Quick Reference: Which Button Does What?

| Button | Event Name | Typical Use |
|--------|-----------|-------------|
| Trigger (index finger) | `triggerdown` / `triggerup` | Click / Select |
| Grip (middle finger) | `gripdown` / `gripup` | Grab / Hold |
| A Button (right) | `abuttondown` / `abuttonup` | Action 1 |
| B Button (right) | `bbuttondown` / `bbuttonup` | Action 2 |
| X Button (left) | `xbuttondown` / `xbuttonup` | Action 3 |
| Y Button (left) | `ybuttondown` / `ybuttonup` | Action 4 |
| Thumbstick press | `thumbstickdown` | Special action |
| Thumbstick move | `thumbstickmoved` | Movement / rotation |

---

### 🧩 Quick Reference: Where to Paste What

```
<html>
  <head>
    📍 Extra scripts go HERE (aframe-extras, etc.)
    📍 A-Frame script goes HERE
  </head>
  <body>
    <a-scene>

      📍 <a-assets> go HERE (textures, models, audio)

      📍 <a-light> go HERE (lighting)

      📍 Camera + Controller rig goes HERE

      📍 Scene objects go HERE (boxes, spheres, models, etc.)

      📍 <a-text> goes HERE (labels, titles)

      📍 <a-sky> goes HERE (background)

      📍 <script> blocks go HERE (interactions, at the BOTTOM)

    </a-scene>
  </body>
</html>
```

---

<a name="examples"></a>

## 🎯 PART 16 — Complete Copy-Paste Examples

### EXAMPLE A: Full Textured Interactive Scene

This is a **complete, working file**. Copy this entire thing into your `index.html`:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>VR Workshop — Textured Scene</title>
    <meta name="description" content="Interactive VR Workshop Demo with Textures">
    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
  </head>
  <body>
    <a-scene>

      <!-- ====== LOAD TEXTURES FIRST ====== -->
      <a-assets>
        <img id="wood" src="https://cdn.aframe.io/a-painter/images/wood.jpg">
        <img id="floor" src="https://cdn.aframe.io/a-painter/images/floor.jpg">
        <img id="city-sky" src="https://cdn.aframe.io/360-image-gallery-boilerplate/img/city.jpg">
      </a-assets>

      <!-- ====== CONTROLLERS ====== -->
      <a-entity id="rig">
        <a-entity camera position="0 1.6 0" look-controls></a-entity>
        <a-entity
          meta-touch-controls="hand: left"
          laser-controls="hand: left"
          raycaster="objects: .clickable; far: 20"
          line="color: cyan">
        </a-entity>
        <a-entity
          meta-touch-controls="hand: right"
          laser-controls="hand: right"
          raycaster="objects: .clickable; far: 20"
          line="color: magenta">
        </a-entity>
      </a-entity>

      <!-- ====== SCENE OBJECTS ====== -->
      <a-box position="-2 0.5 -3" src="#wood" class="clickable"></a-box>
      <a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E" class="clickable"></a-sphere>
      <a-cylinder position="2 0.75 -3" radius="0.5" height="1.5" color="#FFC65D" class="clickable"></a-cylinder>

      <!-- ====== ENVIRONMENT ====== -->
      <a-plane position="0 0 -4" rotation="-90 0 0" width="20" height="20" src="#floor"></a-plane>
      <a-sky src="#city-sky"></a-sky>

      <!-- ====== FLOATING TITLE ====== -->
      <a-text value="Welcome to VR Workshop!" position="0 3 -5" align="center" color="#FFF" width="8"></a-text>

      <!-- ====== INTERACTION SCRIPT ====== -->
      <script>
        AFRAME.registerComponent('click-change-color', {
          init: function () {
            this.el.addEventListener('click', function () {
              var randomColor = '#' + Math.floor(Math.random() * 16777215).toString(16).padStart(6, '0');
              this.setAttribute('color', randomColor);
            });
          }
        });
        document.addEventListener('DOMContentLoaded', function () {
          document.querySelectorAll('.clickable').forEach(function (obj) {
            obj.setAttribute('click-change-color', '');
          });
        });
      </script>

    </a-scene>
  </body>
</html>
```

---

### EXAMPLE B: Custom Objects + Animations Scene

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>VR Workshop — Custom World</title>
    <meta name="description" content="Custom 3D Objects with Animations">
    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
  </head>
  <body>
    <a-scene fog="type: linear; color: #AAB; near: 10; far: 40">

      <!-- ====== CONTROLLERS ====== -->
      <a-entity id="rig">
        <a-entity camera position="0 1.6 0" look-controls></a-entity>
        <a-entity
          meta-touch-controls="hand: left"
          laser-controls="hand: left"
          raycaster="objects: .clickable; far: 20"
          line="color: cyan">
        </a-entity>
        <a-entity
          meta-touch-controls="hand: right"
          laser-controls="hand: right"
          raycaster="objects: .clickable; far: 20"
          line="color: magenta">
        </a-entity>
      </a-entity>

      <!-- ====== LIGHTS ====== -->
      <a-light type="ambient" color="#BBB" intensity="0.5"></a-light>
      <a-light type="directional" color="#FFF" intensity="0.8" position="-1 2 1"></a-light>

      <!-- ====== HOUSE ====== -->
      <a-entity position="-4 0 -6" class="clickable">
        <a-box position="0 1 0" width="3" height="2" depth="3" color="#8B4513"></a-box>
        <a-cone position="0 2.5 0" radius-bottom="2.2" height="1.5" color="#DC143C"></a-cone>
        <a-box position="0 0.5 1.51" width="0.8" height="1.5" depth="0.1" color="#654321"></a-box>
        <a-plane position="-0.8 1.2 1.51" width="0.6" height="0.6" color="#87CEEB"></a-plane>
        <a-plane position="0.8 1.2 1.51" width="0.6" height="0.6" color="#87CEEB"></a-plane>
      </a-entity>

      <!-- ====== TREE ====== -->
      <a-entity position="4 0 -5">
        <a-cylinder position="0 0.75 0" radius="0.2" height="1.5" color="#8B4513"></a-cylinder>
        <a-sphere position="0 2 0" radius="1" color="#228B22"></a-sphere>
        <a-sphere position="0.5 1.8 0" radius="0.7" color="#32CD32"></a-sphere>
        <a-sphere position="-0.5 1.8 0" radius="0.7" color="#32CD32"></a-sphere>
      </a-entity>

      <!-- ====== MOVING CAR ====== -->
      <a-entity
        position="-5 0.5 -3"
        class="clickable"
        animation="property: position; to: 5 0.5 -3; dur: 6000; dir: alternate; loop: true; easing: easeInOutQuad">
        <a-box width="2" height="0.5" depth="1" color="#FF0000"></a-box>
        <a-box position="0 0.5 0" width="1.2" height="0.5" depth="0.8" color="#8B0000"></a-box>
        <a-cylinder position="0.6 -0.25 0.6" radius="0.25" height="0.1" rotation="0 0 90" color="#111"></a-cylinder>
        <a-cylinder position="0.6 -0.25 -0.6" radius="0.25" height="0.1" rotation="0 0 90" color="#111"></a-cylinder>
        <a-cylinder position="-0.6 -0.25 0.6" radius="0.25" height="0.1" rotation="0 0 90" color="#111"></a-cylinder>
        <a-cylinder position="-0.6 -0.25 -0.6" radius="0.25" height="0.1" rotation="0 0 90" color="#111"></a-cylinder>
      </a-entity>

      <!-- ====== SPINNING FLOATING OBJECT ====== -->
      <a-box
        position="0 2 -6"
        color="#9B59B6"
        class="clickable"
        animation__spin="property: rotation; to: 360 360 0; loop: true; dur: 4000"
        animation__float="property: position; to: 0 3 -6; dir: alternate; loop: true; dur: 2000">
      </a-box>

      <!-- ====== TITLE ====== -->
      <a-text value="My Custom VR World" position="0 4 -6" align="center" color="#FFF" width="10"></a-text>

      <!-- ====== ENVIRONMENT ====== -->
      <a-plane position="0 0 -5" rotation="-90 0 0" width="30" height="30" color="#7BC8A4"></a-plane>
      <a-sky color="#87CEEB"></a-sky>

      <!-- ====== INTERACTION SCRIPT ====== -->
      <script>
        AFRAME.registerComponent('click-change-color', {
          init: function () {
            this.el.addEventListener('click', function () {
              var randomColor = '#' + Math.floor(Math.random() * 16777215).toString(16).padStart(6, '0');
              this.setAttribute('color', randomColor);
            });
          }
        });
        document.addEventListener('DOMContentLoaded', function () {
          document.querySelectorAll('.clickable').forEach(function (obj) {
            obj.setAttribute('click-change-color', '');
          });
        });
      </script>

    </a-scene>
  </body>
</html>
```

---

### EXAMPLE C: Tinkercad Model Import Scene

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>VR Workshop — 3D Model Showcase</title>
    <meta name="description" content="Imported 3D Models from Tinkercad">
    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
  </head>
  <body>
    <a-scene>

      <!-- ====== LOAD 3D MODELS ====== -->
      <a-assets>
        <!-- Replace these with YOUR model files uploaded to GitHub -->
        <a-asset-item id="my-model" src="models/my-design.glb"></a-asset-item>
        <img id="floor" src="https://cdn.aframe.io/a-painter/images/floor.jpg">
      </a-assets>

      <!-- ====== CONTROLLERS ====== -->
      <a-entity id="rig">
        <a-entity camera position="0 1.6 0" look-controls></a-entity>
        <a-entity
          meta-touch-controls="hand: left"
          laser-controls="hand: left"
          raycaster="objects: .clickable; far: 20"
          line="color: cyan">
        </a-entity>
        <a-entity
          meta-touch-controls="hand: right"
          laser-controls="hand: right"
          raycaster="objects: .clickable; far: 20"
          line="color: magenta">
        </a-entity>
      </a-entity>

      <!-- ====== LIGHTS (important for 3D models!) ====== -->
      <a-light type="ambient" color="#FFF" intensity="0.6"></a-light>
      <a-light type="directional" color="#FFF" intensity="0.8" position="1 2 1"></a-light>

      <!-- ====== YOUR 3D MODEL ====== -->
      <!-- Adjust scale and position until it looks right -->
      <a-entity
        gltf-model="#my-model"
        position="0 0 -3"
        scale="1 1 1"
        class="clickable"
        animation="property: rotation; to: 0 360 0; loop: true; dur: 8000">
      </a-entity>

      <!-- ====== LABEL ====== -->
      <a-text value="My Tinkercad Creation" position="0 2.5 -3" align="center" color="#FFF" width="5"></a-text>

      <!-- ====== ENVIRONMENT ====== -->
      <a-plane position="0 0 -4" rotation="-90 0 0" width="20" height="20" src="#floor"></a-plane>
      <a-sky color="#1a1a2e"></a-sky>

      <!-- ====== INTERACTION SCRIPT ====== -->
      <script>
        AFRAME.registerComponent('click-change-color', {
          init: function () {
            this.el.addEventListener('click', function () {
              var randomColor = '#' + Math.floor(Math.random() * 16777215).toString(16).padStart(6, '0');
              this.setAttribute('color', randomColor);
            });
          }
        });
        document.addEventListener('DOMContentLoaded', function () {
          document.querySelectorAll('.clickable').forEach(function (obj) {
            obj.setAttribute('click-change-color', '');
          });
        });
      </script>

    </a-scene>
  </body>
</html>
```

---

<a name="troubleshooting"></a>

## 📌 PART 17 — Troubleshooting — Fix Common Problems

| # | Problem | Solution |
|---|---------|----------|
| 1 | GitHub Pages shows 404 | Wait 2-5 minutes after enabling. Make sure file is named `index.html` (lowercase!) |
| 2 | No "Enter VR" button | Must be HTTPS. GitHub Pages gives HTTPS automatically |
| 3 | Controllers not showing | Make sure Quest controllers are turned ON and paired |
| 4 | Laser not appearing | Check that you have the `laser-controls` and `line` attributes on controller entities |
| 5 | Can't click objects | Make sure object has `class="clickable"` |
| 6 | 3D model not visible | Check the URL is correct. Try adjusting `scale` (model may be too tiny or too huge) |
| 7 | Model is upside down | Add `rotation="-90 0 0"` or `rotation="0 180 0"` |
| 8 | Texture not loading | Make sure image URL is HTTPS. Check for typos in the `id` and `src` |
| 9 | Scene is very dark | Your 3D model might need custom lights. Add ambient + directional lights (see PART 6) |
| 10 | Audio not playing | Browsers block autoplay. User must interact with page first (click "Enter VR") |
| 11 | Everything is white | Check that your A-Frame script tag is loading correctly. Open browser console (F12) for errors |
| 12 | Slow loading | Use the Asset System to preload. Compress textures. Use smaller 3D models |
| 13 | Thumbstick not working | Make sure you added the `aframe-extras` script in `<head>` BEFORE the A-Frame script |
| 14 | Teleport not working | Your floor must have `class="ground"` and `aframe-extras` must be loaded |
| 15 | Movement too fast/slow | Change `speed` value in `movement-controls="speed: 0.3"` (lower = slower) |

### How to Debug:

1. Open your page in a regular browser (Chrome/Edge)
2. Press **F12** to open Developer Tools
3. Go to **Console** tab and look for red errors
4. Fix the errors, re-upload to GitHub, and wait for Pages to update

---

## 📚 All Official A-Frame Documentation Links

| Category | Topic | Link |
|----------|-------|------|
| **Getting Started** | Introduction | https://aframe.io/docs/1.7.0/introduction/ |
| **Getting Started** | Installation | https://aframe.io/docs/1.7.0/introduction/installation.html |
| **Getting Started** | HTML and Primitives | https://aframe.io/docs/1.7.0/introduction/html-and-primitives.html |
| **Guides** | Building a Basic Scene | https://aframe.io/docs/1.7.0/guides/building-a-basic-scene.html |
| **Guides** | Building a 360 Gallery | https://aframe.io/docs/1.7.0/guides/building-a-360-image-gallery.html |
| **Guides** | 3D Models | https://aframe.io/docs/1.7.0/introduction/models.html |
| **Guides** | Hosting and Publishing | https://aframe.io/docs/1.7.0/introduction/hosting-and-publishing.html |
| **Core** | Scene | https://aframe.io/docs/1.7.0/core/scene.html |
| **Core** | Entity | https://aframe.io/docs/1.7.0/core/entity.html |
| **Core** | Component | https://aframe.io/docs/1.7.0/core/component.html |
| **Core** | Asset Management | https://aframe.io/docs/1.7.0/core/asset-management-system.html |
| **Components** | Camera | https://aframe.io/docs/1.7.0/components/camera.html |
| **Components** | Meta Touch Controls | https://aframe.io/docs/1.7.0/components/meta-touch-controls.html |
| **Components** | Laser Controls | https://aframe.io/docs/1.7.0/components/laser-controls.html |
| **Components** | Raycaster | https://aframe.io/docs/1.7.0/components/raycaster.html |
| **Components** | Material | https://aframe.io/docs/1.7.0/components/material.html |
| **Components** | GLTF Model | https://aframe.io/docs/1.7.0/components/gltf-model.html |
| **Components** | Animation | https://aframe.io/docs/1.7.0/components/animation.html |
| **Components** | Light | https://aframe.io/docs/1.7.0/components/light.html |
| **Components** | Sound | https://aframe.io/docs/1.7.0/components/sound.html |
| **Components** | Text | https://aframe.io/docs/1.7.0/components/text.html |
| **Components** | Fog | https://aframe.io/docs/1.7.0/components/fog.html |
| **Components** | Position | https://aframe.io/docs/1.7.0/components/position.html |
| **Components** | Rotation | https://aframe.io/docs/1.7.0/components/rotation.html |
| **Components** | Scale | https://aframe.io/docs/1.7.0/components/scale.html |
| **Components** | Geometry | https://aframe.io/docs/1.7.0/components/geometry.html |
| **Components** | Writing a Component | https://aframe.io/docs/1.7.0/introduction/writing-a-component.html |
| **Interactions** | Events and DOM APIs | https://aframe.io/docs/1.7.0/introduction/javascript-events-dom-apis.html |
| **Interactions** | Interactions Guide | https://aframe.io/docs/1.7.0/introduction/interactions-and-controllers.html |
| **Learning** | A-Frame School | https://aframe.io/aframe-school/ |
| **Community** | Stack Overflow | https://stackoverflow.com/questions/tagged/aframe |
| **Resources** | Free 3D Models (Sketchfab) | https://sketchfab.com/search?type=models&features=downloadable |
| **Resources** | Free Textures (Poly Haven) | https://polyhaven.com/textures |
| **Resources** | Tinkercad | https://www.tinkercad.com/ |

---

## ✅ Workshop Checklist

Before sharing with students, verify:

- [ ] `index.html` file has `<!DOCTYPE html>` at the top
- [ ] A-Frame script tag loads correctly (`1.7.1`)
- [ ] GitHub repo is **Public**
- [ ] GitHub Pages is **enabled** (Settings → Pages → main branch)
- [ ] Page loads in regular browser (Chrome/Edge)
- [ ] "Enter VR" button appears (bottom right)
- [ ] TinyURL created and works
- [ ] Tested on Meta Quest 3s browser
- [ ] Controllers are visible with laser beams
- [ ] Click interaction works (objects change color)

---

## 🚀 What's Next? (Advanced Topics for Future Workshops)

Once students master the basics, explore these:

| Feature | Difficulty | Description |
|---------|-----------|-------------|
| Hand Tracking | 🔴 Hard | Use bare hands instead of controllers |
| Physics Engine | 🔴 Hard | Objects fall with gravity, bounce, collide |
| Multiplayer VR | 🔴 Very Hard | Multiple people in same VR world |
| AR (Augmented Reality) | 🔴 Hard | Place virtual objects in real world |
| Particle Effects | 🟡 Medium | Fire, smoke, sparkle effects |
| Dynamic UI Menus | 🔴 Hard | Interactive menus/buttons in VR |

---

**Made with ❤️ for VR Workshop 2026**

**A-Frame Version:** 1.7.1

**Last Updated:** February 17, 2026

**Hosting:** GitHub Pages + TinyURL (No Glitch!)

**Hardware:** Meta Quest 3s
