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

# 📌 Future Lesson Extensions

You can build more advanced examples:

- Thumbstick movement
- Teleport locomotion
- Grab and throw system
- Physics engine integration
- Hand tracking (without controllers)
- VR UI buttons
- Interactive menus

---

# End of Guide
