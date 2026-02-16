# 🧱 A-Frame VR Workshop — Copyable Code Chunks

> **How to use this guide:** Each section below is a self-contained chunk you can copy and paste directly into your `index.html`. Read the comment above each chunk to know **what it does** and **where it goes**. A full structure map is at the bottom.

---

## 1 — Starter Template (The Shell)

> Copy this first. Everything else goes **inside** `<a-scene> ... </a-scene>`.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My VR Scene</title>
    <!-- Load the A-Frame library — this gives us all the VR tags -->
    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
  </head>
  <body>
    <a-scene>

      <!-- ALL YOUR CHUNKS GO HERE -->

    </a-scene>
  </body>
</html>
```

---

## 2 — Assets (Pre-load Images & Textures)

> Paste inside `<a-scene>`, **before** any objects. Pre-loading assets avoids flicker and lets you reuse textures with an id.

```html
<!-- Assets: pre-load images so they are ready when the scene starts -->
<a-assets>
  <img id="wood"     src="https://cdn.aframe.io/a-painter/images/wood.jpg">
  <img id="floor"    src="https://cdn.aframe.io/a-painter/images/floor.jpg">
  <img id="city-sky" src="https://cdn.aframe.io/360-image-gallery-boilerplate/img/city.jpg">
</a-assets>
```

### Adding Your Own Textures

```html
<!-- You can add any image URL as a texture and give it an id -->
<a-assets>
  <img id="myTexture" src="https://example.com/my-image.png">
</a-assets>

<!-- Then use it on any object with src="#myTexture" -->
<a-box src="#myTexture" position="0 1 -3"></a-box>
```

---

## 3 — Camera + Desktop Controls (Keyboard & Mouse)

> Gives you WASD movement, mouse look, and a white dot cursor that can click objects. Works on any PC browser.

```html
<!-- Camera with desktop mouse + keyboard controls -->
<a-entity id="rig">
  <a-entity camera position="0 1.6 0" look-controls wasd-controls>
    <!-- Desktop mouse cursor: the white dot in the center of the screen -->
    <!-- It can click any object that has class="clickable" -->
    <a-cursor
      color="#FFFFFF"
      fuse="false"
      raycaster="objects: .clickable; far: 20">
    </a-cursor>
  </a-entity>
</a-entity>
```

**Controls on Desktop:**
| Key / Action | What it does |
|---|---|
| `W` | Move forward |
| `A` | Move left |
| `S` | Move backward |
| `D` | Move right |
| Click + Drag | Look around |
| Click on object | Interact (if object has `class="clickable"`) |

---

## 4 — Meta Quest Controllers (VR Headset)

> Add this **inside** the `<a-entity id="rig">` block, right after the camera. Gives you laser pointers on both hands in VR.

```html
<!-- Left Quest controller — cyan laser pointer -->
<a-entity
  id="leftController"
  meta-touch-controls="hand: left"
  laser-controls="hand: left"
  raycaster="objects: .clickable; far: 20"
  line="color: cyan">
</a-entity>

<!-- Right Quest controller — magenta laser pointer -->
<a-entity
  id="rightController"
  meta-touch-controls="hand: right"
  laser-controls="hand: right"
  raycaster="objects: .clickable; far: 20"
  line="color: magenta">
</a-entity>
```

---

## 5 — Lights

> Without lights, everything looks flat. Paste anywhere inside `<a-scene>`.

```html
<!-- Ambient light: soft overall glow so nothing is pure black -->
<a-light type="ambient" color="#BBB" intensity="0.5"></a-light>

<!-- Directional light: like sunlight, comes from one direction and casts shadows -->
<a-light type="directional" color="#FFF" intensity="0.8" position="-1 2 1"></a-light>
```

### Other Light Types You Can Try

```html
<!-- Point light: like a light bulb, glows in all directions from one spot -->
<a-light type="point" color="#FF0" intensity="1" position="0 3 -3" distance="10"></a-light>

<!-- Spot light: like a flashlight, shines in a cone -->
<a-light type="spot" color="#FFF" intensity="1" position="0 4 -3" angle="45" penumbra="0.2"></a-light>
```

---

## 6 — Basic Shapes (Primitives)

> These are the building blocks of your scene. Change `position`, `color`, `rotation`, and `scale` to customize.

### Box

```html
<!-- A box (cube). position="x y z" sets where it appears. -->
<!-- x = left/right, y = up/down, z = forward(−)/backward(+) -->
<a-box
  position="-2 0.5 -3"
  rotation="0 45 0"
  color="#4CC3D9"
  width="1" height="1" depth="1"
  class="clickable">
</a-box>
```

### Sphere

```html
<!-- A sphere (ball). radius controls the size. -->
<a-sphere
  position="0 1.25 -5"
  radius="1.25"
  color="#EF2D5E"
  class="clickable">
</a-sphere>
```

### Cylinder

```html
<!-- A cylinder (pillar/tube). radius = thickness, height = tall. -->
<a-cylinder
  position="2 0.75 -3"
  radius="0.5"
  height="1.5"
  color="#FFC65D"
  class="clickable">
</a-cylinder>
```

### Cone

```html
<!-- A cone. radius-bottom is the base, radius-top is the tip (0 = pointy). -->
<a-cone
  position="3 1 -4"
  radius-bottom="1"
  radius-top="0"
  height="2"
  color="#8B5CF6"
  class="clickable">
</a-cone>
```

### Torus (Donut)

```html
<!-- A torus (donut shape). radius = ring size, radius-tubular = tube thickness. -->
<a-torus
  position="-3 1.5 -4"
  radius="1"
  radius-tubular="0.2"
  color="#10B981"
  class="clickable">
</a-torus>
```

### Ring

```html
<!-- A flat ring. radius-inner is the hole, radius-outer is the edge. -->
<a-ring
  position="0 2 -4"
  radius-inner="0.5"
  radius-outer="1"
  color="#F59E0B">
</a-ring>
```

### Plane (Flat Surface)

```html
<!-- A flat surface — useful for walls, floors, screens. -->
<a-plane
  position="0 1 -4"
  width="3"
  height="2"
  color="#3B82F6">
</a-plane>
```

---

## 7 — Textured Box (Apply a Texture to a Shape)

> Use `src="#id"` to apply a pre-loaded texture from `<a-assets>`.

```html
<!-- A wooden box — uses the "wood" texture loaded in assets -->
<a-box
  position="-2 0.5 -3"
  rotation="0 45 0"
  src="#wood"
  class="clickable">
</a-box>
```

---

## 8 — Environment (Floor + Sky)

> A ground plane and a 360° sky image. Paste inside `<a-scene>`.

```html
<!-- Floor: a rotated plane flat on the ground -->
<a-plane
  position="0 0 -4"
  rotation="-90 0 0"
  width="20"
  height="20"
  src="#floor">
</a-plane>

<!-- Sky: a 360° image wrapping around the entire scene -->
<a-sky src="#city-sky"></a-sky>
```

### Plain Color Sky (No Image Needed)

```html
<!-- Simple gradient-feel sky with a flat color -->
<a-sky color="#87CEEB"></a-sky>
```

---

## 9 — Text

> Floating text labels. `align="center"` centers horizontally. `width` controls text size.

```html
<!-- Big title floating in the scene -->
<a-text
  value="Welcome to VR Workshop!"
  position="0 3.5 -5"
  align="center"
  color="#FFFFFF"
  width="8">
</a-text>

<!-- Smaller instruction text closer to the user -->
<a-text
  value="Click objects to change color! (WASD to move, Mouse to look)"
  position="0 0.5 -2"
  align="center"
  color="#AAAAAA"
  width="5">
</a-text>
```

---

## 10 — Images & Posters

> Display a flat image in the scene (like a poster on a wall).

```html
<!-- Display an image floating in the scene -->
<!-- width and height control the display size, not the actual image resolution -->
<a-image
  src="https://raw.githubusercontent.com/alluringxstalwart/SourceYISL/main/Landscape.png"
  position="0 5 -10"
  width="25"
  height="7.5">
</a-image>
```

---

## 11 — Animations

> Add the `animation` attribute to ANY object to make it move, spin, scale, or change color automatically.

### Spin Forever

```html
<!-- Rotate 360° on Y-axis, looping forever, taking 5 seconds per rotation -->
<a-box
  position="-2 0.5 -3"
  color="#4CC3D9"
  animation="property: rotation; to: 0 360 0; loop: true; dur: 5000">
</a-box>
```

### Bounce Up and Down

```html
<!-- Move up and back down forever. dir: alternate reverses each cycle. -->
<a-sphere
  position="0 1.25 -5"
  color="#EF2D5E"
  animation="property: position; to: 0 2.5 -5; dir: alternate; loop: true; dur: 1500">
</a-sphere>
```

### Pulse (Grow and Shrink)

```html
<!-- Scale up to 1.3x then back to normal, looping -->
<a-cylinder
  position="2 0.75 -3"
  color="#FFC65D"
  animation="property: scale; to: 1.3 1.3 1.3; dir: alternate; loop: true; dur: 800">
</a-cylinder>
```

### Color Fade

```html
<!-- Smoothly shift from red to blue and back -->
<a-sphere
  position="0 1 -4"
  color="#FF0000"
  animation="property: material.color; type: color; to: #0000FF; dir: alternate; loop: true; dur: 2000">
</a-sphere>
```

### Fade In (Opacity)

```html
<!-- Fade in from invisible to fully visible over 2 seconds -->
<a-box
  position="0 1 -3"
  color="#00FF00"
  material="opacity: 0; transparent: true"
  animation="property: material.opacity; to: 1; dur: 2000">
</a-box>
```

---

## 12 — 3D Models (Import from Tinkercad / Blender / Online)

> Export your Tinkercad model as **OBJ** or **GLB/GLTF**. Host the file online (GitHub, etc.) and use its URL.

### GLB / GLTF Model (Recommended)

```html
<!-- Load a 3D model in GLB format (from Tinkercad, Blender, Sketchfab, etc.) -->
<!-- Export as GLB from Tinkercad: Design > Download > .GLB -->
<!-- Upload the file to GitHub or any file host and paste the URL below -->
<a-entity
  gltf-model="url(https://your-url-here.com/model.glb)"
  position="0 1 -4"
  scale="0.5 0.5 0.5"
  rotation="0 0 0"
  class="clickable">
</a-entity>
```

### OBJ + MTL Model

```html
<!-- Load an OBJ model with its material file -->
<!-- You need TWO files: the .obj (shape) and .mtl (colors/textures) -->
<a-entity
  obj-model="obj: url(https://your-url/model.obj); mtl: url(https://your-url/model.mtl)"
  position="0 1 -4"
  scale="0.01 0.01 0.01"
  class="clickable">
</a-entity>
```

### How to Get Your Tinkercad Model Into A-Frame

1. Open your design on [tinkercad.com](https://www.tinkercad.com)
2. Click **Export** (top-right) → choose **GLB**
3. Upload the `.glb` file to GitHub (or any web host)
4. Copy the **raw URL** and paste it into the `gltf-model` line above

---

## 13 — Click to Change Color (Interaction Script)

> Paste this **at the bottom** of `<a-scene>`, before the closing `</a-scene>` tag. Any object with `class="clickable"` will change to a random color when clicked.

```html
<!-- Interaction: click any object with class="clickable" to change its color -->
<script>
  AFRAME.registerComponent('click-change-color', {
    init: function () {
      this.el.addEventListener('click', function () {
        // Generate a random hex color
        var randomColor = '#' + Math.floor(Math.random() * 16777215).toString(16).padStart(6, '0');
        // Remove any texture so the color shows (important for textured objects)
        this.removeAttribute('src');
        this.setAttribute('material', 'src', '');
        // Apply the random color
        this.setAttribute('color', randomColor);
      });
    }
  });

  // Automatically attach the component to every clickable object
  document.addEventListener('DOMContentLoaded', function () {
    document.querySelectorAll('.clickable').forEach(function (obj) {
      obj.setAttribute('click-change-color', '');
    });
  });
</script>
```

---

## 14 — Click to Play Sound

> Make objects play a sound when clicked.

```html
<!-- First, add the sound file in <a-assets> -->
<a-assets>
  <audio id="clickSound" src="https://cdn.aframe.io/basic-guide/audio/backgroundnoise.wav" preload="auto"></audio>
</a-assets>

<!-- Then add this script before </a-scene> -->
<script>
  AFRAME.registerComponent('click-play-sound', {
    init: function () {
      this.el.addEventListener('click', function () {
        // Play the sound when this object is clicked
        this.setAttribute('sound', 'src: #clickSound; autoplay: true');
        this.components.sound.playSound();
      });
    }
  });
</script>

<!-- Add the component to any object -->
<!-- Example: <a-box class="clickable" click-play-sound position="0 1 -3"></a-box> -->
```

---

## 15 — Video in VR (Play a Video on a Screen)

> Show a video on a flat surface in the scene.

```html
<!-- Add the video to assets -->
<a-assets>
  <video id="myVideo" src="https://your-url/video.mp4" loop="true" crossorigin="anonymous"></video>
</a-assets>

<!-- Display the video on a flat plane like a screen -->
<a-video
  src="#myVideo"
  position="0 3 -6"
  width="8"
  height="4.5">
</a-video>
```

---

## 16 — Teleportation (Click Floor to Move)

> Lets the user click on the floor to teleport to that spot.

```html
<!-- Make the floor teleportable — add class="ground" to your floor plane -->
<a-plane
  position="0 0 -4"
  rotation="-90 0 0"
  width="40"
  height="40"
  src="#floor"
  class="ground">
</a-plane>

<!-- Add this script before </a-scene> -->
<script>
  AFRAME.registerComponent('teleport-on-click', {
    init: function () {
      var rig = document.querySelector('#rig');
      this.el.addEventListener('click', function (evt) {
        // Get the point where the user clicked on the floor
        var point = evt.detail.intersection.point;
        // Move the camera rig to that spot (keep Y at 0 so we stay on the ground)
        rig.setAttribute('position', {x: point.x, y: 0, z: point.z});
      });
    }
  });

  document.addEventListener('DOMContentLoaded', function () {
    document.querySelectorAll('.ground').forEach(function (obj) {
      obj.setAttribute('teleport-on-click', '');
    });
  });
</script>
```

> **Note:** Update your cursor/raycaster to also target `.ground`: `raycaster="objects: .clickable, .ground; far: 20"`

---

## 17 — Particle Effects (Simple Floating Particles)

> Uses the A-Frame particle system component. Add the extra script in `<head>`.

```html
<!-- Add this script tag in <head>, AFTER the aframe script -->
<script src="https://unpkg.com/aframe-particle-system-component@1.1.3/dist/aframe-particle-system-component.min.js"></script>

<!-- Then place this inside <a-scene> — floating dust/snow particles -->
<a-entity
  position="0 2.5 -4"
  particle-system="preset: dust; particleCount: 500; color: #EEE, #FFF">
</a-entity>
```

### Other Presets

```html
<!-- Snow -->
<a-entity particle-system="preset: snow; particleCount: 1000"></a-entity>

<!-- Rain -->
<a-entity particle-system="preset: rain; particleCount: 500"></a-entity>
```

---

## 18 — Multiple Animations on One Object

> Use `animation__name` (double underscore + any label) to stack multiple animations.

```html
<!-- This box spins AND pulses at the same time -->
<a-box
  position="0 1 -4"
  color="#E040FB"
  class="clickable"
  animation__spin="property: rotation; to: 0 360 0; loop: true; dur: 4000"
  animation__pulse="property: scale; to: 1.2 1.2 1.2; dir: alternate; loop: true; dur: 1000">
</a-box>
```

---

## 19 — Curved Image (Wrap an Image Around You)

> Displays an image on a curved surface — great for galleries.

```html
<!-- A curved image panel — like a cinema screen that wraps slightly -->
<a-curvedimage
  src="#city-sky"
  height="3"
  radius="5"
  theta-length="90"
  position="0 2 -4"
  rotation="0 90 0">
</a-curvedimage>
```

---

## 20 — Link to Another VR Page

> Click a portal to open another webpage in VR.

```html
<!-- A portal sphere that links to another page -->
<a-link
  href="https://aframe.io"
  title="A-Frame Website"
  position="3 1.5 -5"
  image="https://aframe.io/images/aframe-logo.png">
</a-link>
```

---

---

# 🗺️ Where Does Each Chunk Go? (Full Structure Map)

Below is the **skeleton** of the full HTML file showing **exactly** where each numbered chunk should be pasted:

```
<!DOCTYPE html>
<html>
  <head>
    ...
    <script src="aframe.min.js"></script>
    ┌──────────────────────────────────────────────────┐
    │  CHUNK 17 — Extra <script> tags go here          │
    │  (particle system, etc.) — AFTER the aframe      │
    │  script but still inside <head>                  │
    └──────────────────────────────────────────────────┘
  </head>
  <body>
    <a-scene>

      ┌──────────────────────────────────────────────────┐
      │  CHUNK 2 — <a-assets> (textures, images, audio,  │
      │  video) — always FIRST inside <a-scene>          │
      └──────────────────────────────────────────────────┘

      ┌──────────────────────────────────────────────────┐
      │  CHUNK 3 — Camera + Desktop Controls             │
      │    └─ CHUNK 4 — Quest VR Controllers             │
      │       (inside the same <a-entity id="rig">)      │
      └──────────────────────────────────────────────────┘

      ┌──────────────────────────────────────────────────┐
      │  CHUNK 5 — Lights                                │
      └──────────────────────────────────────────────────┘

      ┌──────────────────────────────────────────────────┐
      │  CHUNKS 6–12 — All your objects go here:         │
      │    • Basic shapes (box, sphere, cylinder, etc.)  │
      │    • Textured objects                            │
      │    • 3D models (Tinkercad GLB/OBJ)               │
      │    • Images & posters                            │
      │    • Text labels                                 │
      │    • Videos                                      │
      │    • Curved images, links, particles             │
      │    • Animated objects (add animation to any)      │
      └──────────────────────────────────────────────────┘

      ┌──────────────────────────────────────────────────┐
      │  CHUNK 8 — Floor + Sky (environment)             │
      └──────────────────────────────────────────────────┘

      ┌──────────────────────────────────────────────────┐
      │  CHUNKS 13–16 — <script> blocks go LAST          │
      │    • Click-change-color                          │
      │    • Click-play-sound                            │
      │    • Teleportation                               │
      │    (just before </a-scene>)                      │
      └──────────────────────────────────────────────────┘

    </a-scene>
  </body>
</html>
```

### Quick Rules

| Rule | Why |
|---|---|
| `<a-assets>` goes **first** inside `<a-scene>` | So textures/audio are loaded before objects try to use them |
| Camera + Controllers go **together** in one `<a-entity id="rig">` | So moving the rig moves everything (camera + hands) together |
| Lights go **before** objects | So objects are lit correctly when they appear |
| Objects go in **any order** in the middle | A-Frame renders them regardless of order |
| `<script>` blocks go at the **bottom** of `<a-scene>` | So all HTML elements exist before the script tries to find them |
| Add `class="clickable"` to any object you want to interact with | The cursor and controllers only detect objects with this class |
| Extra JS libraries (particles, etc.) go in `<head>` | They must load before A-Frame tries to use their components |

---

> **Tip:** Start with Chunks 1–5, then add one object at a time. Test after every change! 🚀
