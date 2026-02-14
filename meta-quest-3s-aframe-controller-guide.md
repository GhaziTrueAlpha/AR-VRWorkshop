# Meta Quest 3s Controller Setup in A-Frame (Beginner Friendly Guide)

This guide teaches you how to:

- Add Meta Quest 3s controllers
- Enable laser interaction
- Make objects clickable
- Add trigger-based color change interaction
- Structure your file properly for teaching students

---

# 📁 PART 1 — Basic Scene Setup

If you are creating a new project, start with this base HTML file.

Paste this into a new file like:

```
index.html
```

```html
<!-- ========================= -->
<!-- BASIC A-FRAME SCENE FILE -->
<!-- Paste this in a new .html file -->
<!-- ========================= -->

<html>
  <head>
    <!-- A-Frame Library -->
    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
  </head>

  <body>
    <a-scene>

      <!-- SCENE OBJECTS -->
      <a-box position="-1 0.5 -3" rotation="0 45 0" color="#4CC3D9"></a-box>
      <a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E"></a-sphere>
      <a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color="#FFC65D"></a-cylinder>
      <a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4"></a-plane>
      <a-sky color="#ECECEC"></a-sky>

    </a-scene>
  </body>
</html>
```

---

# 🎮 PART 2 — Add Meta Quest 3s Controllers

## 📍 Where to Paste?

Paste the following **inside `<a-scene>`**, either above or below your objects.

---

## 🔹 Step 1: Add Camera + Controller Rig

```html
<!-- ========================= -->
<!-- CAMERA + CONTROLLER RIG -->
<!-- Paste INSIDE <a-scene> -->
<!-- ========================= -->

<a-entity id="rig">

  <!-- VR Camera (Head Tracking) -->
  <a-entity camera position="0 1.6 0" look-controls></a-entity>

  <!-- LEFT CONTROLLER -->
  <a-entity
    id="leftController"
    meta-touch-controls="hand: left"
    laser-controls="hand: left"
    raycaster="objects: .clickable; far: 20"
    line="color: cyan">
  </a-entity>

  <!-- RIGHT CONTROLLER -->
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

## 🧠 What This Does

- `camera` → Your head tracking
- `meta-touch-controls` → Connects Quest controllers
- `laser-controls` → Shows laser pointer
- `raycaster` → Detects clickable objects
- `.clickable` → Only objects with this class can be interacted with

---

# 🖱 PART 3 — Make Objects Clickable

To make any object interactive, add:

```
class="clickable"
```

Example:

```html
<a-box 
  position="-1 0.5 -3" 
  rotation="0 45 0" 
  color="#4CC3D9"
  class="clickable">
</a-box>
```

You can add this to sphere and cylinder as well.

---

# 🎨 PART 4 — Add Interaction Script (Color Change on Trigger)

## 📍 Where to Paste?

Paste this **inside `<a-scene>` at the bottom**, just before:

```
</a-scene>
```

---

```html
<!-- ========================= -->
<!-- INTERACTION SCRIPT -->
<!-- Paste before </a-scene> -->
<!-- ========================= -->

<script>
  // Custom component to change color on click
  AFRAME.registerComponent('click-change-color', {
    init: function () {
      this.el.addEventListener('click', () => {
        this.el.setAttribute(
          'color',
          '#' + Math.floor(Math.random() * 16777215).toString(16)
        );
      });
    }
  });

  // Attach component to all clickable objects
  document.addEventListener('DOMContentLoaded', function () {
    const objects = document.querySelectorAll('.clickable');
    objects.forEach(obj => {
      obj.setAttribute('click-change-color', '');
    });
  });
</script>
```

---

# 🧱 Final File Structure Should Look Like This

```html
<html>
  <head>
    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
  </head>

  <body>
    <a-scene>

      <!-- Controller Rig -->
      (Controller Chunk Here)

      <!-- Scene Objects with class="clickable" -->
      (Your Objects Here)

      <!-- Interaction Script -->
      (Script Chunk Here)

    </a-scene>
  </body>
</html>
```

---

# 🚀 How to Test on Meta Quest 3s

1. Upload file to GitHub
2. Make sure it loads over HTTPS
3. Open link inside Quest browser
4. Click "Enter VR"
5. Point controller laser at object
6. Press trigger
7. Object color changes

---

# 🎓 Teaching Notes for Students

This example demonstrates:

- Basic VR scene creation
- Head tracking
- Controller tracking
- Raycasting
- Event handling
- Custom A-Frame components
- DOM interaction inside VR

---

# �️ PART 5 — Adding Textures to Objects

## 📍 Option 1: Using Image URLs

You can add textures using direct image URLs:

```html
<!-- ========================= -->
<!-- TEXTURED OBJECTS -->
<!-- Paste INSIDE <a-scene> -->
<!-- ========================= -->

<!-- Box with Wood Texture -->
<a-box 
  position="-1 0.5 -3" 
  rotation="0 45 0" 
  src="https://cdn.aframe.io/a-painter/images/wood.jpg"
  class="clickable">
</a-box>

<!-- Sphere with Earth Texture -->
<a-sphere 
  position="0 1.25 -5" 
  radius="1.25" 
  src="https://cdn.aframe.io/360-image-gallery-boilerplate/img/sechelt.jpg"
  class="clickable">
</a-sphere>

<!-- Sky with 360 Image -->
<a-sky src="https://cdn.aframe.io/360-image-gallery-boilerplate/img/city.jpg"></a-sky>
```

---

## 📍 Option 2: Using Asset Management System (RECOMMENDED)

This is the **proper way** to load textures - it preloads images before scene starts:

```html
<!-- ========================= -->
<!-- ASSET MANAGEMENT SYSTEM -->
<!-- Paste INSIDE <a-scene> at the TOP -->
<!-- ========================= -->

<a-scene>
  <!-- Assets Section - Load First -->
  <a-assets>
    <img id="woodTexture" src="https://cdn.aframe.io/a-painter/images/wood.jpg">
    <img id="brickTexture" src="https://cdn.aframe.io/a-painter/images/brick.jpg">
    <img id="skyTexture" src="https://cdn.aframe.io/360-image-gallery-boilerplate/img/city.jpg">
    <img id="groundTexture" src="https://cdn.aframe.io/a-painter/images/floor.jpg">
  </a-assets>

  <!-- Use Assets by ID -->
  <a-box position="-1 0.5 -3" src="#woodTexture" class="clickable"></a-box>
  <a-sphere position="0 1.25 -5" src="#brickTexture" class="clickable"></a-sphere>
  <a-plane position="0 0 -4" rotation="-90 0 0" width="10" height="10" src="#groundTexture"></a-plane>
  <a-sky src="#skyTexture"></a-sky>

  <!-- Rest of your scene... -->
</a-scene>
```

---

## 📍 Option 3: Using Local Images

If you have images in your project folder:

```
project/
├── index.html
└── textures/
    ├── wood.jpg
    ├── metal.png
    └── grass.jpg
```

```html
<a-assets>
  <img id="wood" src="textures/wood.jpg">
  <img id="metal" src="textures/metal.png">
  <img id="grass" src="textures/grass.jpg">
</a-assets>

<a-box position="-1 0.5 -3" src="#wood" class="clickable"></a-box>
```

---

# 🎨 PART 6 — Importing 3D Models from Tinkercad

## 🔧 Step-by-Step Process

### 1️⃣ Export from Tinkercad

1. Open your design in Tinkercad
2. Click **"Export"** button (top right)
3. Choose **"GLTF"** format (recommended) or **"OBJ"**
4. Download the `.glb` or `.gltf` file

---

### 2️⃣ Host Your 3D Model

You need to upload your model file to a web server. Options:

**Option A: GitHub (Free & Easy)**
1. Create a GitHub repository
2. Upload your `.glb` file
3. Use the raw file URL

**Option B: Glitch.com (Quick Testing)**
1. Create a Glitch project
2. Upload file to `assets` folder
3. Copy the CDN URL

**Option C: Your Own Web Server**
- Upload to your hosting
- Note the full URL

---

### 3️⃣ Add Model to A-Frame Scene

```html
<!-- ========================= -->
<!-- IMPORTING 3D MODEL FROM TINKERCAD -->
<!-- Paste INSIDE <a-scene> -->
<!-- ========================= -->

<a-scene>
  <!-- Load Model in Assets -->
  <a-assets>
    <a-asset-item id="myModel" src="YOUR_MODEL_URL.glb"></a-asset-item>
  </a-assets>

  <!-- Place Model in Scene -->
  <a-entity 
    gltf-model="#myModel" 
    position="0 0 -3" 
    rotation="0 0 0"
    scale="1 1 1"
    class="clickable">
  </a-entity>

  <!-- Rest of scene... -->
</a-scene>
```

---

### 4️⃣ Real Example with URL

```html
<a-scene>
  <a-assets>
    <!-- Replace with your actual model URL -->
    <a-asset-item 
      id="robot" 
      src="https://cdn.glitch.com/your-project/robot.glb">
    </a-asset-item>
  </a-assets>

  <!-- Robot Model -->
  <a-entity 
    gltf-model="#robot" 
    position="0 0.5 -3" 
    rotation="0 45 0"
    scale="0.5 0.5 0.5"
    class="clickable"
    animation="property: rotation; to: 0 360 0; loop: true; dur: 10000">
  </a-entity>
</a-scene>
```

---

## 🎯 Common Adjustments for Tinkercad Models

```html
<!-- Model Too Big? Scale Down -->
<a-entity gltf-model="#myModel" scale="0.1 0.1 0.1"></a-entity>

<!-- Model Too Small? Scale Up -->
<a-entity gltf-model="#myModel" scale="5 5 5"></a-entity>

<!-- Model Wrong Orientation? Rotate -->
<a-entity gltf-model="#myModel" rotation="-90 0 0"></a-entity>

<!-- Add Animation -->
<a-entity 
  gltf-model="#myModel" 
  animation="property: rotation; to: 0 360 0; loop: true; dur: 5000">
</a-entity>
```

---

# 🛠️ PART 7 — Creating Custom 3D Objects with Primitives

## 🏠 Example 1: Build a Simple House

```html
<!-- ========================= -->
<!-- CUSTOM HOUSE FROM PRIMITIVES -->
<!-- Paste INSIDE <a-scene> -->
<!-- ========================= -->

<!-- Group objects together -->
<a-entity position="0 0 -5">
  <!-- House Base -->
  <a-box 
    position="0 1 0" 
    width="3" 
    height="2" 
    depth="3" 
    color="#8B4513">
  </a-box>

  <!-- Roof -->
  <a-cone 
    position="0 2.5 0" 
    radius-bottom="2.2" 
    radius-top="0" 
    height="1.5" 
    color="#DC143C"
    rotation="0 45 0">
  </a-cone>

  <!-- Door -->
  <a-box 
    position="0 0.5 1.51" 
    width="0.8" 
    height="1.5" 
    depth="0.1" 
    color="#654321">
  </a-box>

  <!-- Window Left -->
  <a-plane 
    position="-0.8 1.2 1.51" 
    width="0.6" 
    height="0.6" 
    color="#87CEEB">
  </a-plane>

  <!-- Window Right -->
  <a-plane 
    position="0.8 1.2 1.51" 
    width="0.6" 
    height="0.6" 
    color="#87CEEB">
  </a-plane>
</a-entity>
```

---

## 🌳 Example 2: Create a Tree

```html
<!-- ========================= -->
<!-- CUSTOM TREE FROM PRIMITIVES -->
<!-- Paste INSIDE <a-scene> -->
<!-- ========================= -->

<a-entity position="3 0 -4">
  <!-- Tree Trunk -->
  <a-cylinder 
    position="0 0.5 0" 
    radius="0.2" 
    height="2" 
    color="#8B4513">
  </a-cylinder>

  <!-- Tree Leaves (Sphere) -->
  <a-sphere 
    position="0 2 0" 
    radius="1" 
    color="#228B22">
  </a-sphere>

  <!-- More Leaf Spheres -->
  <a-sphere position="0.5 1.8 0" radius="0.7" color="#32CD32"></a-sphere>
  <a-sphere position="-0.5 1.8 0" radius="0.7" color="#32CD32"></a-sphere>
</a-entity>
```

---

## 🚗 Example 3: Build a Simple Car

```html
<!-- ========================= -->
<!-- CUSTOM CAR FROM PRIMITIVES -->
<!-- Paste INSIDE <a-scene> -->
<!-- ========================= -->

<a-entity position="-3 0.5 -4" class="clickable">
  <!-- Car Body -->
  <a-box 
    position="0 0 0" 
    width="2" 
    height="0.5" 
    depth="1" 
    color="#FF0000">
  </a-box>

  <!-- Car Top -->
  <a-box 
    position="0 0.5 -0.2" 
    width="1.2" 
    height="0.5" 
    depth="0.8" 
    color="#8B0000">
  </a-box>

  <!-- Wheel 1 -->
  <a-cylinder 
    position="0.6 -0.25 0.6" 
    radius="0.25" 
    height="0.1" 
    rotation="0 0 90" 
    color="#000000">
  </a-cylinder>

  <!-- Wheel 2 -->
  <a-cylinder 
    position="0.6 -0.25 -0.6" 
    radius="0.25" 
    height="0.1" 
    rotation="0 0 90" 
    color="#000000">
  </a-cylinder>

  <!-- Wheel 3 -->
  <a-cylinder 
    position="-0.6 -0.25 0.6" 
    radius="0.25" 
    height="0.1" 
    rotation="0 0 90" 
    color="#000000">
  </a-cylinder>

  <!-- Wheel 4 -->
  <a-cylinder 
    position="-0.6 -0.25 -0.6" 
    radius="0.25" 
    height="0.1" 
    rotation="0 0 90" 
    color="#000000">
  </a-cylinder>
</a-entity>
```

---

## 🎮 Example 4: Gamepad/Controller Model

```html
<!-- ========================= -->
<!-- CUSTOM GAMEPAD FROM PRIMITIVES -->
<!-- Paste INSIDE <a-scene> -->
<!-- ========================= -->

<a-entity position="0 1 -2" rotation="20 0 0">
  <!-- Main Body -->
  <a-box 
    width="1.5" 
    height="0.3" 
    depth="0.8" 
    color="#2C2C2C">
  </a-box>

  <!-- Left Grip -->
  <a-cylinder 
    position="-0.5 -0.3 0" 
    radius="0.15" 
    height="0.5" 
    rotation="0 0 20" 
    color="#1C1C1C">
  </a-cylinder>

  <!-- Right Grip -->
  <a-cylinder 
    position="0.5 -0.3 0" 
    radius="0.15" 
    height="0.5" 
    rotation="0 0 -20" 
    color="#1C1C1C">
  </a-cylinder>

  <!-- Button A (Red) -->
  <a-sphere 
    position="0.3 0.2 0.2" 
    radius="0.08" 
    color="#FF0000">
  </a-sphere>

  <!-- Button B (Blue) -->
  <a-sphere 
    position="0.5 0.2 0.1" 
    radius="0.08" 
    color="#0000FF">
  </a-sphere>
</a-entity>
```

---

# 🎬 PART 8 — Adding Animations to Objects

## 📍 Basic Animation Examples

```html
<!-- ========================= -->
<!-- ANIMATED OBJECTS -->
<!-- Paste INSIDE <a-scene> -->
<!-- ========================= -->

<!-- Rotating Box -->
<a-box 
  position="-2 1 -3" 
  color="#4CC3D9"
  animation="property: rotation; to: 0 360 0; loop: true; dur: 3000">
</a-box>

<!-- Bouncing Sphere -->
<a-sphere 
  position="0 1 -3" 
  radius="0.5" 
  color="#EF2D5E"
  animation="property: position; to: 0 2 -3; dir: alternate; loop: true; dur: 1000">
</a-sphere>

<!-- Pulsing Cylinder -->
<a-cylinder 
  position="2 1 -3" 
  color="#FFC65D"
  animation="property: scale; to: 1.5 1.5 1.5; dir: alternate; loop: true; dur: 1500">
</a-cylinder>

<!-- Color Changing Object -->
<a-box 
  position="0 0.5 -5" 
  animation="property: color; to: #FF0000; dir: alternate; loop: true; dur: 2000">
</a-box>
```

---

## 📍 Multiple Animations on One Object

```html
<!-- Rotate AND Move -->
<a-box 
  position="0 1 -3"
  animation__rotate="property: rotation; to: 0 360 0; loop: true; dur: 3000"
  animation__bounce="property: position; to: 0 2 -3; dir: alternate; loop: true; dur: 1000">
</a-box>
```

---

# 🎯 PART 9 — Complete Workshop-Ready Examples

## 🎪 Example A: Complete Textured Scene

```html
<!DOCTYPE html>
<html>
  <head>
    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
  </head>
  <body>
    <a-scene>
      
      <!-- Assets -->
      <a-assets>
        <img id="wood" src="https://cdn.aframe.io/a-painter/images/wood.jpg">
        <img id="grass" src="https://cdn.aframe.io/a-painter/images/floor.jpg">
        <img id="sky" src="https://cdn.aframe.io/360-image-gallery-boilerplate/img/city.jpg">
      </a-assets>

      <!-- Controllers -->
      <a-entity id="rig">
        <a-entity camera position="0 1.6 0" look-controls></a-entity>
        <a-entity meta-touch-controls="hand: left" laser-controls="hand: left" raycaster="objects: .clickable" line="color: cyan"></a-entity>
        <a-entity meta-touch-controls="hand: right" laser-controls="hand: right" raycaster="objects: .clickable" line="color: magenta"></a-entity>
      </a-entity>

      <!-- Scene Objects -->
      <a-box position="-1 0.5 -3" src="#wood" class="clickable"></a-box>
      <a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E" class="clickable"></a-sphere>
      <a-plane position="0 0 -4" rotation="-90 0 0" width="10" height="10" src="#grass"></a-plane>
      <a-sky src="#sky"></a-sky>

      <!-- Interaction Script -->
      <script>
        AFRAME.registerComponent('click-change-color', {
          init: function () {
            this.el.addEventListener('click', () => {
              this.el.setAttribute('color', '#' + Math.floor(Math.random() * 16777215).toString(16));
            });
          }
        });
        document.addEventListener('DOMContentLoaded', function () {
          const objects = document.querySelectorAll('.clickable');
          objects.forEach(obj => obj.setAttribute('click-change-color', ''));
        });
      </script>

    </a-scene>
  </body>
</html>
```

---

## 🏘️ Example B: Scene with Custom Objects

```html
<!DOCTYPE html>
<html>
  <head>
    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
  </head>
  <body>
    <a-scene>

      <!-- Controllers -->
      <a-entity id="rig">
        <a-entity camera position="0 1.6 0" look-controls></a-entity>
        <a-entity meta-touch-controls="hand: left" laser-controls="hand: left" raycaster="objects: .clickable" line="color: cyan"></a-entity>
        <a-entity meta-touch-controls="hand: right" laser-controls="hand: right" raycaster="objects: .clickable" line="color: magenta"></a-entity>
      </a-entity>

      <!-- Custom House -->
      <a-entity position="-3 0 -5" class="clickable">
        <a-box position="0 1 0" width="3" height="2" depth="3" color="#8B4513"></a-box>
        <a-cone position="0 2.5 0" radius-bottom="2.2" height="1.5" color="#DC143C"></a-cone>
        <a-box position="0 0.5 1.51" width="0.8" height="1.5" depth="0.1" color="#654321"></a-box>
      </a-entity>

      <!-- Custom Tree -->
      <a-entity position="3 0 -4">
        <a-cylinder position="0 0.5 0" radius="0.2" height="2" color="#8B4513"></a-cylinder>
        <a-sphere position="0 2 0" radius="1" color="#228B22"></a-sphere>
      </a-entity>

      <!-- Custom Car -->
      <a-entity position="0 0.5 -3" class="clickable"
        animation="property: position; to: 5 0.5 -3; dur: 5000; dir: alternate; loop: true">
        <a-box width="2" height="0.5" depth="1" color="#FF0000"></a-box>
        <a-box position="0 0.5 -0.2" width="1.2" height="0.5" depth="0.8" color="#8B0000"></a-box>
        <a-cylinder position="0.6 -0.25 0.6" radius="0.25" height="0.1" rotation="0 0 90" color="#000"></a-cylinder>
        <a-cylinder position="0.6 -0.25 -0.6" radius="0.25" height="0.1" rotation="0 0 90" color="#000"></a-cylinder>
        <a-cylinder position="-0.6 -0.25 0.6" radius="0.25" height="0.1" rotation="0 0 90" color="#000"></a-cylinder>
        <a-cylinder position="-0.6 -0.25 -0.6" radius="0.25" height="0.1" rotation="0 0 90" color="#000"></a-cylinder>
      </a-entity>

      <!-- Ground and Sky -->
      <a-plane position="0 0 -4" rotation="-90 0 0" width="20" height="20" color="#7BC8A4"></a-plane>
      <a-sky color="#87CEEB"></a-sky>

      <!-- Interaction Script -->
      <script>
        AFRAME.registerComponent('click-change-color', {
          init: function () {
            this.el.addEventListener('click', () => {
              this.el.setAttribute('color', '#' + Math.floor(Math.random() * 16777215).toString(16));
            });
          }
        });
        document.addEventListener('DOMContentLoaded', function () {
          const objects = document.querySelectorAll('.clickable');
          objects.forEach(obj => obj.setAttribute('click-change-color', ''));
        });
      </script>

    </a-scene>
  </body>
</html>
```

---

## 🎨 Example C: 3D Model Import Scene

```html
<!DOCTYPE html>
<html>
  <head>
    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
  </head>
  <body>
    <a-scene>

      <!-- Assets (Replace with YOUR model URL) -->
      <a-assets>
        <a-asset-item id="myModel" src="YOUR_MODEL_URL.glb"></a-asset-item>
        <img id="ground" src="https://cdn.aframe.io/a-painter/images/floor.jpg">
      </a-assets>

      <!-- Controllers -->
      <a-entity id="rig">
        <a-entity camera position="0 1.6 0" look-controls></a-entity>
        <a-entity meta-touch-controls="hand: left" laser-controls="hand: left" raycaster="objects: .clickable" line="color: cyan"></a-entity>
        <a-entity meta-touch-controls="hand: right" laser-controls="hand: right" raycaster="objects: .clickable" line="color: magenta"></a-entity>
      </a-entity>

      <!-- Your 3D Model -->
      <a-entity 
        gltf-model="#myModel" 
        position="0 0 -3" 
        scale="1 1 1"
        rotation="0 0 0"
        class="clickable"
        animation="property: rotation; to: 0 360 0; loop: true; dur: 10000">
      </a-entity>

      <!-- Environment -->
      <a-plane position="0 0 0" rotation="-90 0 0" width="20" height="20" src="#ground"></a-plane>
      <a-sky color="#ECECEC"></a-sky>

      <!-- Interaction Script -->
      <script>
        AFRAME.registerComponent('click-change-color', {
          init: function () {
            this.el.addEventListener('click', () => {
              const newScale = this.el.getAttribute('scale');
              this.el.setAttribute('scale', {
                x: newScale.x * 1.2,
                y: newScale.y * 1.2,
                z: newScale.z * 1.2
              });
            });
          }
        });
        document.addEventListener('DOMContentLoaded', function () {
          const objects = document.querySelectorAll('.clickable');
          objects.forEach(obj => obj.setAttribute('click-change-color', ''));
        });
      </script>

    </a-scene>
  </body>
</html>
```

---

# 📌 Quick Reference: Common Issues & Solutions

## ❌ Problem: Model Too Big/Small
```html
<!-- Solution: Adjust scale -->
<a-entity gltf-model="#model" scale="0.5 0.5 0.5"></a-entity>
```

## ❌ Problem: Model Upside Down
```html
<!-- Solution: Rotate 180 degrees -->
<a-entity gltf-model="#model" rotation="180 0 0"></a-entity>
```

## ❌ Problem: Texture Not Loading
```html
<!-- Solution: Check URL and use HTTPS -->
<img id="tex" src="https://example.com/texture.jpg" crossorigin="anonymous">
```

## ❌ Problem: Controllers Not Working
```html
<!-- Solution: Make sure objects have class="clickable" -->
<a-box class="clickable"></a-box>
```

## ❌ Problem: CORS Error with Model
```html
<!-- Solution: Add crossorigin to asset -->
<a-asset-item id="model" src="URL.glb" crossorigin="anonymous"></a-asset-item>
```

---

# 🎓 Workshop Tips for Students

1. **Start Simple**: Begin with basic shapes, then add complexity
2. **Test Often**: Enter VR mode frequently to check your work
3. **Use Comments**: Label your code sections clearly
4. **Save Versions**: Keep backup copies before major changes
5. **Share URLs**: Use GitHub or Glitch for easy sharing
6. **Debug in Browser**: Open browser console (F12) to see errors

---

# 📚 Additional Resources

- **A-Frame Documentation**: https://aframe.io/docs/
- **A-Frame School**: https://aframe.io/aframe-school/
- **Free 3D Models**: https://sketchfab.com/
- **Free Textures**: https://www.textures.com/
- **Tinkercad**: https://www.tinkercad.com/

---

# 🚀 Future Extensions

You can build more advanced examples:

- Thumbstick movement
- Teleport locomotion
- Grab and throw physics
- Multi-player networking
- Hand tracking (without controllers)
- VR UI menus
- Sound effects and spatial audio
- Particle systems
- Physics engine integration

---

# ✅ Workshop Checklist

Before sharing with students, ensure:

- [ ] All code chunks are copy-paste ready
- [ ] Asset URLs are working (HTTPS)
- [ ] Controller code is included
- [ ] Examples are tested in VR
- [ ] Comments explain each section
- [ ] File structure is clear
- [ ] Troubleshooting section is included

---

# End of Guide
