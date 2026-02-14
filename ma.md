# 🥽 Complete A-Frame VR Workshop Guide — Meta Quest 3s Edition# Meta Quest 3s Controller Setup in A-Frame (Beginner Friendly Guide)



> **📋 Workshop-Ready:** Every code chunk is copy-paste ready!  This guide teaches you how to:

> **🧒 Beginner-Friendly:** Explained like you're 15 and just started coding  

> **🌐 GitHub Pages + TinyURL:** No Glitch needed — we use GitHub Pages for hosting  - Add Meta Quest 3s controllers

> **🎮 Meta Quest 3s:** Tested and ready for Quest 3s controllers- Enable laser interaction

- Make objects clickable

![A-Frame Banner](https://cloud.githubusercontent.com/assets/674727/25392020/6f011d10-298c-11e7-845e-c3c5baebd14d.jpg)- Add trigger-based color change interaction

- Structure your file properly for teaching students

---

---

## 📚 Table of Contents

# 📁 PART 1 — Basic Scene Setup

| # | Topic | What You'll Learn |

|---|-------|-------------------|If you are creating a new project, start with this base HTML file.

| 1 | [How We Host Our VR Experience](#how-we-host) | GitHub Pages + TinyURL workflow |

| 2 | [Basic Scene Setup](#part-1) | Your first VR world |Paste this into a new file like:

| 3 | [Meta Quest 3s Controllers](#part-2) | Lasers, buttons, head tracking |

| 4 | [Making Objects Clickable](#part-3) | Laser interaction with objects |```

| 5 | [Interaction Script (Color Change)](#part-4) | Click to change color |index.html

| 6 | [Adding Textures to Objects](#part-5) | Skins, images, materials |```

| 7 | [Import 3D Models from Tinkercad](#part-6) | Export → Upload → Load in VR |

| 8 | [Build Custom 3D Objects in Code](#part-7) | House, Tree, Car — using shapes |```html

| 9 | [Animations](#part-8) | Spin, bounce, pulse, glow |<!-- ========================= -->

| 10 | [360° Sky & Environment](#part-9) | Panoramic backgrounds |<!-- BASIC A-FRAME SCENE FILE -->

| 11 | [Lighting & Shadows](#part-10) | Realistic lighting |<!-- Paste this in a new .html file -->

| 12 | [Sound & Audio](#part-11) | Background music & sound effects |<!-- ========================= -->

| 13 | [Text in VR](#part-12) | Floating labels & titles |

| 14 | [Deploy: GitHub Pages + TinyURL](#deployment) | Go live on Quest |<html>

| 15 | [Complete Copy-Paste Examples](#examples) | Full working scenes |  <head>

| 16 | [Troubleshooting](#troubleshooting) | Fix common problems |    <!-- A-Frame Library -->

    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>

---  </head>



<a name="how-we-host"></a>  <body>

# 🌐 How We Host Our VR Experience    <a-scene>



## Our Simple 3-Step Workflow      <!-- SCENE OBJECTS -->

      <a-box position="-1 0.5 -3" rotation="0 45 0" color="#4CC3D9"></a-box>

```      <a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E"></a-sphere>

1. ✍️  CREATE → Write your index.html (copy chunks from this guide)      <a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color="#FFC65D"></a-cylinder>

2. ☁️  UPLOAD → Push to a GitHub repository      <a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4"></a-plane>

3. 🌍  SHARE  → Enable GitHub Pages → Shorten with TinyURL → Open on Meta Quest 3s      <a-sky color="#ECECEC"></a-sky>

```

    </a-scene>

> 💡 **Think of it like posting on Instagram:**    </body>

> You create content (your HTML file), upload it to GitHub (like posting to Instagram), GitHub Pages shows it to the world (like your public profile), and TinyURL makes the link easy to type (like a Linktree short link)!</html>

```

### ⚠️ Important Rules

---

- We are **NOT** using Glitch — only GitHub Pages

- Your link **must** be HTTPS (GitHub Pages gives this automatically ✅)# 🎮 PART 2 — Add Meta Quest 3s Controllers

- File **must** be named `index.html` (GitHub Pages looks for this file)

- Repository **must** be Public (so everyone can open it)## 📍 Where to Paste?



---Paste the following **inside `<a-scene>`**, either above or below your objects.



<a name="part-1"></a>---

# 📁 PART 1 — Basic Scene Setup

## 🔹 Step 1: Add Camera + Controller Rig

## 🎬 What is A-Frame?

```html

**Think of A-Frame like LEGO blocks for VR:**<!-- ========================= -->

- Each block is a 3D shape (`<a-box>`, `<a-sphere>`, `<a-cylinder>`)<!-- CAMERA + CONTROLLER RIG -->

- You place them in a virtual room (`<a-scene>`)<!-- Paste INSIDE <a-scene> -->

- No coding degree needed — just copy & paste HTML!<!-- ========================= -->



**Real-Life Example:** Just like Minecraft where you place blocks to build a world, A-Frame lets you place 3D objects using simple HTML tags!<a-entity id="rig">



![A-Frame Inspector](https://cloud.githubusercontent.com/assets/674727/25377018/27be9cce-295b-11e7-9098-3e85ac1fe172.gif)  <!-- VR Camera (Head Tracking) -->

  <a-entity camera position="0 1.6 0" look-controls></a-entity>

---

  <!-- LEFT CONTROLLER -->

## 📝 CODE CHUNK 1: Your First VR Scene  <a-entity

    id="leftController"

Create a file called `index.html` and paste this:    meta-touch-controls="hand: left"

    laser-controls="hand: left"

```html    raycaster="objects: .clickable; far: 20"

<!DOCTYPE html>    line="color: cyan">

<html>  </a-entity>

  <head>

    <meta charset="utf-8">  <!-- RIGHT CONTROLLER -->

    <title>My First VR Scene</title>  <a-entity

    <meta name="description" content="VR Workshop Demo">    id="rightController"

    meta-touch-controls="hand: right"

    <!-- A-Frame Library — This is the engine that powers our VR world -->    laser-controls="hand: right"

    <!-- Think of it like downloading a game engine (Unity/Unreal) but in one line -->    raycaster="objects: .clickable; far: 20"

    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>    line="color: magenta">

  </head>  </a-entity>



  <body></a-entity>

    <!-- a-scene = Your entire VR World (like a Minecraft world or Fortnite map) -->```

    <a-scene>

---

      <!-- ====== SCENE OBJECTS ====== -->

      <!-- These are like placing furniture in a room -->## 🧠 What This Does



      <!-- Box: Like a Rubik's cube floating in the air -->- `camera` → Your head tracking

      <a-box- `meta-touch-controls` → Connects Quest controllers

        position="-1 0.5 -3"- `laser-controls` → Shows laser pointer

        rotation="0 45 0"- `raycaster` → Detects clickable objects

        color="#4CC3D9">- `.clickable` → Only objects with this class can be interacted with

      </a-box>

---

      <!-- Sphere: Like a basketball -->

      <a-sphere# 🖱 PART 3 — Make Objects Clickable

        position="0 1.25 -5"

        radius="1.25"To make any object interactive, add:

        color="#EF2D5E">

      </a-sphere>```

class="clickable"

      <!-- Cylinder: Like a Red Bull can standing up -->```

      <a-cylinder

        position="1 0.75 -3"Example:

        radius="0.5"

        height="1.5"```html

        color="#FFC65D"><a-box 

      </a-cylinder>  position="-1 0.5 -3" 

  rotation="0 45 0" 

      <!-- Plane: The floor/ground you walk on -->  color="#4CC3D9"

      <a-plane  class="clickable">

        position="0 0 -4"</a-box>

        rotation="-90 0 0"```

        width="4"

        height="4"You can add this to sphere and cylinder as well.

        color="#7BC8A4">

      </a-plane>---



      <!-- Sky: Background color (like a Zoom virtual background) --># 🎨 PART 4 — Add Interaction Script (Color Change on Trigger)

      <a-sky color="#ECECEC"></a-sky>

## 📍 Where to Paste?

    </a-scene>

  </body>Paste this **inside `<a-scene>` at the bottom**, just before:

</html>

``````

</a-scene>

---```



## 🧠 Code Explanation (In Simple English)---



### What Each Tag Does:```html

<!-- ========================= -->

| Code | What It Means | Real-Life Example |<!-- INTERACTION SCRIPT -->

|------|---------------|-------------------|<!-- Paste before </a-scene> -->

| `<!DOCTYPE html>` | "Hey browser, this is an HTML page" | Like a label on a shipping box |<!-- ========================= -->

| `<script src="...aframe.min.js">` | Load the A-Frame VR engine | Like installing a game before playing |

| `<a-scene>` | Your VR room/world | The Fortnite map / Minecraft world |<script>

| `<a-box>` | A 3D cube | Rubik's cube 🟦 |  // Custom component to change color on click

| `<a-sphere>` | A 3D ball | Basketball 🏀 |  AFRAME.registerComponent('click-change-color', {

| `<a-cylinder>` | A 3D tube/can | Red Bull can 🥫 |    init: function () {

| `<a-plane>` | A flat surface | Floor in your room 🟩 |      this.el.addEventListener('click', () => {

| `<a-sky>` | The background of the world | Sky you see in GTA/Fortnite 🌤️ |        this.el.setAttribute(

          'color',

### Position System — How to Place Objects:          '#' + Math.floor(Math.random() * 16777215).toString(16)

        );

```      });

position="X   Y   Z"    }

          👆   👆   👆  });

          |    |    |

          |    |    +-- Forward(-) / Backward(+)  (depth, like walking forward)  // Attach component to all clickable objects

          |    +------- Up(+) / Down(-)           (height, like jumping)  document.addEventListener('DOMContentLoaded', function () {

          +------------ Right(+) / Left(-)        (side to side)    const objects = document.querySelectorAll('.clickable');

```    objects.forEach(obj => {

      obj.setAttribute('click-change-color', '');

**Example:** `position="2 1 -3"` means:    });

- `2` → 2 meters to the **RIGHT**  });

- `1` → 1 meter **UP** from ground</script>

- `-3` → 3 meters **IN FRONT** of you (negative Z = forward)```



> 💡 **Pro Tip:** Think of it like Google Maps coordinates, but for your VR world! X is left/right, Y is up/down, Z is forward/backward.---



### Rotation System — How to Turn Objects:# 🧱 Final File Structure Should Look Like This



``````html

rotation="X    Y    Z"<html>

          👆    👆    👆  <head>

          |     |     |    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>

          |     |     +-- Tilt sideways (like tilting your phone)  </head>

          |     +-------- Spin left/right (like a spinning top)

          +-------------- Tilt forward/back (like nodding your head)  <body>

```    <a-scene>



### Color System:      <!-- Controller Rig -->

      (Controller Chunk Here)

Colors use **hex codes** (like Instagram filter color codes):

- `#4CC3D9` = Light Blue      <!-- Scene Objects with class="clickable" -->

- `#EF2D5E` = Pink/Red      (Your Objects Here)

- `#FFC65D` = Yellow/Orange

- Use any color picker: [Google Color Picker](https://g.co/kgs/JfGHkD)      <!-- Interaction Script -->

      (Script Chunk Here)

---

    </a-scene>

## 📚 Official A-Frame Docs for This Section  </body>

</html>

| Topic | Link |```

|-------|------|

| Getting Started | https://aframe.io/docs/1.7.0/introduction/ |---

| Scene | https://aframe.io/docs/1.7.0/core/scene.html |

| Box Primitive | https://aframe.io/docs/1.7.0/primitives/a-box.html |# 🚀 How to Test on Meta Quest 3s

| Sphere Primitive | https://aframe.io/docs/1.7.0/primitives/a-sphere.html |

| Cylinder Primitive | https://aframe.io/docs/1.7.0/primitives/a-cylinder.html |1. Upload file to GitHub

| Plane Primitive | https://aframe.io/docs/1.7.0/primitives/a-plane.html |2. Make sure it loads over HTTPS

| Sky Primitive | https://aframe.io/docs/1.7.0/primitives/a-sky.html |3. Open link inside Quest browser

| Position Component | https://aframe.io/docs/1.7.0/components/position.html |4. Click "Enter VR"

| Rotation Component | https://aframe.io/docs/1.7.0/components/rotation.html |5. Point controller laser at object

| All Primitives (Shapes) | https://aframe.io/docs/1.7.0/introduction/html-and-primitives.html |6. Press trigger

7. Object color changes

---

---

<a name="part-2"></a>

# 🎮 PART 2 — Add Meta Quest 3s Controllers# 🎓 Teaching Notes for Students



## 🎯 What Are We Adding?This example demonstrates:



**Think of controllers like lightsabers in Star Wars:**- Basic VR scene creation

- They shoot laser beams 🔦- Head tracking

- You point at things and press trigger to interact- Controller tracking

- They track your real hand movements in VR- Raycasting

- Event handling

**Real-Life Example:** It's like using a TV remote, but instead of pressing buttons to change channels, you point a laser at 3D objects and click to interact! 📺➡️🎮- Custom A-Frame components

- DOM interaction inside VR

### 🎮 Meta Quest 3s Controller Buttons:

---

```

    [  Thumbstick  ]     ← Move around (like WASD on keyboard)# 📌 Future Lesson Extensions

    [   A / B      ]     ← Action buttons (right hand)

    [   X / Y      ]     ← Action buttons (left hand)You can build more advanced examples:

    [ TRIGGER 🔫  ]     ← Index finger button — MAIN CLICK (we use this!)

    [ GRIP   ✊   ]     ← Middle finger button — Grab objects- Thumbstick movement

```- Teleport locomotion

- Grab and throw system

---- Physics engine integration

- Hand tracking (without controllers)

## 📝 CODE CHUNK 2: Camera + Controllers- VR UI buttons

- Interactive menus

📍 **Where to paste:** Inside `<a-scene>`, at the **TOP** (before your objects).

---

```html

<!-- ======================================= --># End of Guide

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

## 🧠 Code Explanation (Line by Line)

### 🎥 Camera (Your Eyes):

```html
<a-entity camera position="0 1.6 0" look-controls>
```

| Part | What It Does | Example |
|------|-------------|---------|
| `camera` | Makes this your viewpoint (your eyes) | First-person view in COD |
| `position="0 1.6 0"` | Eye height at 1.6m (about 5'3") | Average human standing height |
| `look-controls` | Moving your head moves the camera | Looking around in real life |

### 🕹️ Controller Parts:

```html
<a-entity
  id="leftController"                          ← Give it a name (like naming a pet 🐶)
  meta-touch-controls="hand: left"             ← Connect to Quest left controller
  laser-controls="hand: left"                  ← Shoot a laser beam from it
  raycaster="objects: .clickable; far: 20"     ← What the laser can detect
  line="color: cyan">                          ← Laser beam color (cyan = light blue)
</a-entity>
```

| Attribute | What It Does | Real-Life Example |
|-----------|-------------|-------------------|
| `meta-touch-controls="hand: left"` | Connects to your physical Quest controller | Like pairing AirPods to your iPhone 📱 |
| `laser-controls="hand: left"` | Shows a visible laser beam | Like a laser pointer in a classroom presentation 🔴 |
| `raycaster="objects: .clickable; far: 20"` | Detects objects the laser hits (only `.clickable` ones, up to 20 units away) | Like a motion sensor that detects movement 📡 |
| `line="color: cyan"` | Color of the laser beam | Left = cyan (light blue), Right = magenta (pink) |

---

## 📚 Official A-Frame Docs for This Section

| Topic | Link |
|-------|------|
| Camera Component | https://aframe.io/docs/1.7.0/components/camera.html |
| Meta Touch Controls | https://aframe.io/docs/1.7.0/components/meta-touch-controls.html |
| Laser Controls | https://aframe.io/docs/1.7.0/components/laser-controls.html |
| Raycaster | https://aframe.io/docs/1.7.0/components/raycaster.html |
| Look Controls | https://aframe.io/docs/1.7.0/components/look-controls.html |
| Interactions & Controllers Guide | https://aframe.io/docs/1.7.0/introduction/interactions-and-controllers.html |

---

<a name="part-3"></a>
# 🖱️ PART 3 — Make Objects Clickable

## 🎯 What Does "Clickable" Mean?

**Think of it like Instagram posts:**
- A regular post → You can scroll past it
- A post with a "❤️ Like" button → You can tap it
- `class="clickable"` → Tells VR "Hey, this object can be clicked!"

**Without `class="clickable"`:** Your laser goes through the object like a ghost 👻  
**With `class="clickable"`:** Your laser stops on it and you can interact ✅

---

## 📝 CODE CHUNK 3: Clickable Objects

📍 **Where to paste:** Replace your existing scene objects inside `<a-scene>` (after the controller rig).

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

## 🧠 Why Do We Need `class="clickable"`?

Remember in **PART 2** we wrote this on the controller:

```html
raycaster="objects: .clickable; far: 20"
```

This tells the raycaster:
- **`objects: .clickable`** → "Only detect objects that have `class='clickable'`"
- **`far: 20`** → "Laser reaches up to 20 units (meters)"

> 💡 **Think of it like a bouncer at a nightclub:** Only people on the VIP list (with `class="clickable"`) get in! 🚪🕺

---

## 📚 Official A-Frame Docs for This Section

| Topic | Link |
|-------|------|
| Raycaster (Object Filtering) | https://aframe.io/docs/1.7.0/components/raycaster.html |
| Interactions Guide | https://aframe.io/docs/1.7.0/introduction/interactions-and-controllers.html |

---

<a name="part-4"></a>
# 🎨 PART 4 — Interaction Script (Color Change on Trigger)

## 🎯 What Does This Do?

When you point your laser at an object and press the **trigger button** → the object changes to a random color!

**Real-Life Example:** Like mood rings that change color when you touch them! 💍✨ Or like TikTok filters — tap the screen and the filter changes!

---

## 📝 CODE CHUNK 4: Color Change Script

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

## 🧠 Code Explanation (Super Detailed)

### The Flow — What Happens When You Click:

```
1. 🔦 Point laser at object
2. 🔫 Press trigger button on Quest controller
3. 👂 Script hears "click" event
4. 🎲 Generates random color (#a3f2c1)
5. 🎨 Changes object's color
6. ✨ Object turns a new color instantly!
```

### Breaking Down the Random Color Generator:

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

### What Does `AFRAME.registerComponent()` Do?

Think of it like this:
- **A-Frame has built-in powers** (position, color, rotation)
- **`registerComponent`** lets you create **custom powers** (like creating a custom TikTok effect)
- We created a power called `'click-change-color'` that changes color on click

---

## 📚 Official A-Frame Docs for This Section

| Topic | Link |
|-------|------|
| Writing a Component | https://aframe.io/docs/1.7.0/introduction/writing-a-component.html |
| JavaScript Events & DOM APIs | https://aframe.io/docs/1.7.0/introduction/javascript-events-dom-apis.html |
| Component API | https://aframe.io/docs/1.7.0/core/component.html |

---

<a name="part-5"></a>
# 🖼️ PART 5 — Adding Textures to Objects

## 🎯 What Are Textures?

**Textures are like skins/wrapping paper for 3D objects:**
- Without texture → Plain flat colors (boring! 😴)
- With texture → Realistic looks (wood, metal, brick, grass) 🤩

**Real-Life Example:**
- Fortnite skins → Change how your character looks
- Minecraft texture packs → Change how blocks look
- Phone wallpapers → Change how your screen looks

That's exactly what textures do for 3D objects!

---

## 📝 CODE CHUNK 5A: Quick Texture via URL (Simple Way)

📍 **Where to paste:** Replace your objects inside `<a-scene>`.

```html
<!-- ======================================= -->
<!-- TEXTURED OBJECTS — Quick URL Method      -->
<!-- Paste INSIDE <a-scene>                  -->
<!-- ======================================= -->

<!-- Wood textured box — src = image URL (like setting a wallpaper) -->
<a-box
  position="-1 0.5 -3"
  src="https://cdn.aframe.io/a-painter/images/wood.jpg"
  class="clickable">
</a-box>

<!-- 360° city sky — wraps around you like a dome -->
<a-sky src="https://cdn.aframe.io/360-image-gallery-boilerplate/img/city.jpg"></a-sky>
```

> ⚠️ **Note:** This way is quick but the texture loads EVERY time the page renders. Not great for performance if you have many textures.

---

## 📝 CODE CHUNK 5B: Asset System (RECOMMENDED ⭐ Best Way)

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

  <!-- ====== CONTROLLERS ====== -->
  <a-entity id="rig">
    <a-entity camera position="0 1.6 0" look-controls></a-entity>
    <a-entity meta-touch-controls="hand: left" laser-controls="hand: left" raycaster="objects: .clickable; far: 20" line="color: cyan"></a-entity>
    <a-entity meta-touch-controls="hand: right" laser-controls="hand: right" raycaster="objects: .clickable; far: 20" line="color: magenta"></a-entity>
  </a-entity>

  <!-- ====== TEXTURED OBJECTS ====== -->
  <!-- src="#wood-texture" → Uses the image with id="wood-texture" from <a-assets> -->
  <!-- Think: Like calling a saved contact instead of typing the full number -->

  <a-box position="-1 0.5 -3" src="#wood-texture" class="clickable"></a-box>
  <a-sphere position="0 1.25 -5" radius="1.25" src="#brick-texture" class="clickable"></a-sphere>
  <a-plane position="0 0 -4" rotation="-90 0 0" width="10" height="10" src="#floor-texture"></a-plane>
  <a-sky src="#sky-city"></a-sky>

</a-scene>
```

---

## 🧠 How the Asset System Works:

```
STEP 1: Save image with an ID
┌─────────────────────────────────────────────────────┐
│ <img id="wood-texture" src="https://...wood.jpg">   │
│                                                     │
│ Think: Saving a contact → Name: "wood-texture"      │
│                           Number: "https://...jpg"   │
└─────────────────────────────────────────────────────┘

STEP 2: Use image by ID
┌──────────────────────────────────────────────────────┐
│ <a-box src="#wood-texture"></a-box>                   │
│                                                      │
│ Think: Calling the saved contact → "#wood-texture"   │
└──────────────────────────────────────────────────────┘

BONUS: Reuse same texture (image loads only ONCE!)
┌──────────────────────────────────────────────────────┐
│ <a-box src="#wood-texture" position="0 0 -3"></a-box>│
│ <a-box src="#wood-texture" position="2 0 -3"></a-box>│
│ <a-box src="#wood-texture" position="4 0 -3"></a-box>│
│                                                      │
│ 3 wooden boxes, but image downloaded only once! 🚀   │
└──────────────────────────────────────────────────────┘
```

---

## 📝 CODE CHUNK 5C: Local Textures from Your GitHub Repo

If you have your own images, upload them to a `textures/` folder in your GitHub repo.

### Folder Structure:

```
your-repo/
├── index.html          ← Your VR scene
└── textures/           ← Create this folder
    ├── wood.jpg
    ├── metal.png
    └── grass.jpg
```

### How to Upload to GitHub:
1. Go to your repo on GitHub.com
2. Click **"Add file"** → **"Create new file"**
3. Type `textures/placeholder.txt` (this creates the folder)
4. Commit it
5. Then upload your images to the `textures/` folder

### Code:

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
<a-box position="-1 0.5 -3" src="#my-wood" class="clickable"></a-box>
<a-sphere position="0 1.25 -5" radius="1.25" src="#my-metal" class="clickable"></a-sphere>
<a-plane position="0 0 -4" rotation="-90 0 0" width="10" height="10" src="#my-grass"></a-plane>
```

---

## 📝 CODE CHUNK 5D: Material Properties (Advanced Textures)

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
  material="color: #C0C0C0; metalness: 1; roughness: 0"
  class="clickable">
</a-sphere>

<!-- Rough Stone Box — like a concrete block -->
<!-- metalness: 0 = not metallic | roughness: 1 = very rough -->
<a-box
  position="0 0.5 -4"
  material="color: #8B8682; metalness: 0; roughness: 1"
  class="clickable">
</a-box>

<!-- Glossy Plastic Cylinder — like a shiny toy -->
<!-- metalness: 0.3 = slightly metallic | roughness: 0.2 = mostly smooth -->
<a-cylinder
  position="2 0.75 -4"
  radius="0.5"
  height="1.5"
  material="color: #FF4500; metalness: 0.3; roughness: 0.2"
  class="clickable">
</a-cylinder>
```

### Material Properties Cheat Sheet:

| Property | Range | What It Does | Example |
|----------|-------|-------------|---------|
| `metalness` | 0 to 1 | How metallic (0=plastic, 1=chrome) | `metalness: 0.8` |
| `roughness` | 0 to 1 | How rough (0=mirror, 1=sandpaper) | `roughness: 0.3` |
| `opacity` | 0 to 1 | How see-through (0=invisible, 1=solid) | `opacity: 0.5` |
| `transparent` | true/false | Enable transparency | `transparent: true` |
| `side` | front/back/double | Which side to render | `side: double` |

---

## 🎨 Free Texture Download Websites:

| Website | What They Have | Link |
|---------|---------------|------|
| **Poly Haven** | Free 4K textures (wood, metal, ground) | https://polyhaven.com/textures |
| **Textures.com** | Huge library (15 free credits/day) | https://www.textures.com/ |
| **Unsplash** | Free high-res photos | https://unsplash.com/ |
| **ambientCG** | Free CC0 textures | https://ambientcg.com/ |

---

## 📚 Official A-Frame Docs for This Section

| Topic | Link |
|-------|------|
| Material Component | https://aframe.io/docs/1.7.0/components/material.html |
| Asset Management System | https://aframe.io/docs/1.7.0/core/asset-management-system.html |
| Building a Basic Scene (Textures) | https://aframe.io/docs/1.7.0/guides/building-a-basic-scene.html |

---

<a name="part-6"></a>
# 🎨 PART 6 — Import 3D Models from Tinkercad

## 🎯 What is Tinkercad?

**Tinkercad** is a free, browser-based 3D design tool by Autodesk. Think of it like **Paint 3D** but way more powerful — you can create robots, characters, buildings, anything!

**Real-Life Example:** Like building with digital LEGO blocks, then exporting your creation to put it in your VR world! 🏗️➡️🥽

**Link:** https://www.tinkercad.com/ (sign up for free)

---

## 🔧 Step-by-Step: Tinkercad → VR

### Step 1: Design in Tinkercad
1. Go to https://www.tinkercad.com/
2. Sign up / Log in
3. Click **"Create new design"**
4. Build your 3D object (drag shapes, combine them)

### Step 2: Export as GLB
1. Click **"Export"** button (top right corner)
2. Choose **".GLB"** format ← **IMPORTANT: Must be GLB!**
3. Download the file (e.g., `robot.glb`)

> ⚠️ **Why GLB?** GLB (GL Binary) is the best 3D format for the web. It's like how JPEG is the standard for photos — GLB is the standard for 3D models on the web. A-Frame supports it natively!

### Step 3: Upload to GitHub
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

## 📝 CODE CHUNK 6A: Import a Tinkercad Model (From Your GitHub)

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

  <!-- Controllers -->
  <a-entity id="rig">
    <a-entity camera position="0 1.6 0" look-controls></a-entity>
    <a-entity meta-touch-controls="hand: left" laser-controls="hand: left" raycaster="objects: .clickable; far: 20" line="color: cyan"></a-entity>
    <a-entity meta-touch-controls="hand: right" laser-controls="hand: right" raycaster="objects: .clickable; far: 20" line="color: magenta"></a-entity>
  </a-entity>

  <!-- Place the 3D model in the scene -->
  <!-- gltf-model="#my-tinkercad-model" → Load the model we saved in assets -->
  <a-entity
    gltf-model="#my-tinkercad-model"
    position="0 0 -3"
    rotation="0 0 0"
    scale="1 1 1"
    class="clickable">
  </a-entity>

  <a-plane position="0 0 -4" rotation="-90 0 0" width="10" height="10" color="#7BC8A4"></a-plane>
  <a-sky color="#87CEEB"></a-sky>

</a-scene>
```

---

## 📝 CODE CHUNK 6B: Common Model Adjustments

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
<!-- Try rotating 90° or 180° on Y axis -->
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

### Scale Cheat Sheet:

| Scale Value | What It Does | When To Use |
|-------------|-------------|-------------|
| `scale="0.01 0.01 0.01"` | 1% of original size | Model is HUGE |
| `scale="0.1 0.1 0.1"` | 10% of original size | Model is big |
| `scale="1 1 1"` | Original size (default) | Looks right already |
| `scale="5 5 5"` | 5x bigger | Model is small |
| `scale="10 10 10"` | 10x bigger | Model is tiny |
| `scale="1 2 1"` | Stretched tall | Make it taller only |

---

## 📝 CODE CHUNK 6C: Import Multiple Models

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
  scale="0.5 0.5 0.5"
  class="clickable">
</a-entity>

<!-- Car in the center -->
<a-entity
  gltf-model="#car"
  position="0 0 -5"
  scale="0.3 0.3 0.3"
  class="clickable">
</a-entity>

<!-- House on the right -->
<a-entity
  gltf-model="#house"
  position="3 0 -5"
  scale="0.2 0.2 0.2"
  class="clickable">
</a-entity>
```

---

## 📝 CODE CHUNK 6D: Load Free Models from URLs

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
  scale="0.5 0.5 0.5"
  class="clickable">
</a-entity>
```

> 💡 **Where to find free 3D models:**
> - **Sketchfab** — https://sketchfab.com/search?type=models&features=downloadable (filter by "Downloadable" → Download as GLB)
> - **Tinkercad** — https://www.tinkercad.com/ (make your own!)
> - **Poly Pizza** — https://poly.pizza/ (free low-poly models)
> - **glTF Sample Models** — https://github.com/KhronosGroup/glTF-Sample-Models (test models)

---

## 📚 Official A-Frame Docs for This Section

| Topic | Link |
|-------|------|
| GLTF Model Component | https://aframe.io/docs/1.7.0/components/gltf-model.html |
| 3D Models Guide | https://aframe.io/docs/1.7.0/introduction/models.html |
| Asset Management System | https://aframe.io/docs/1.7.0/core/asset-management-system.html |
| `<a-gltf-model>` Primitive | https://aframe.io/docs/1.7.0/primitives/a-gltf-model.html |

---

<a name="part-7"></a>
# 🛠️ PART 7 — Build Custom 3D Objects in Code

## 🎯 What is This?

You don't always need Tinkercad! You can build 3D objects by **combining basic shapes** — like building with LEGO blocks but in code!

**Real-Life Example:** Like building a snowman by stacking 3 snowballs — you combine simple shapes to make complex objects! ⛄

---

## 📝 CODE CHUNK 7A: Build a House 🏠

```html
<!-- ======================================= -->
<!-- CUSTOM 3D HOUSE — Made from basic shapes -->
<!-- Paste INSIDE <a-scene>                   -->
<!-- ======================================= -->

<!-- The entire house is wrapped in one <a-entity> so we can move it all together -->
<!-- Think: Like grouping layers in Photoshop -->
<a-entity position="0 0 -5" class="clickable">

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

## 📝 CODE CHUNK 7B: Build a Tree 🌳

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

## 📝 CODE CHUNK 7C: Build a Car 🚗

```html
<!-- ======================================= -->
<!-- CUSTOM 3D CAR                           -->
<!-- Paste INSIDE <a-scene>                  -->
<!-- ======================================= -->

<a-entity position="-3 0.5 -4" class="clickable">

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

## 📝 CODE CHUNK 7D: Build a Snowman ⛄

```html
<!-- ======================================= -->
<!-- CUSTOM 3D SNOWMAN                       -->
<!-- Paste INSIDE <a-scene>                  -->
<!-- ======================================= -->

<a-entity position="2 0 -4" class="clickable">

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

## 📚 Official A-Frame Docs for This Section

| Topic | Link |
|-------|------|
| Entity (Grouping Objects) | https://aframe.io/docs/1.7.0/core/entity.html |
| Cone Primitive | https://aframe.io/docs/1.7.0/primitives/a-cone.html |
| Geometry Component | https://aframe.io/docs/1.7.0/components/geometry.html |
| All Primitives List | https://aframe.io/docs/1.7.0/introduction/html-and-primitives.html |

---

<a name="part-8"></a>
# 🎬 PART 8 — Animations

## 🎯 What Are Animations?

Make your objects **move, spin, bounce, pulse, and glow** — automatically!

**Real-Life Example:** Like animated stickers on Instagram Stories — they move on their own! Or like the spinning logo on a loading screen.

---

## 📝 CODE CHUNK 8A: Basic Animations

📍 **Where to paste:** Add the `animation` attribute directly on any object.

```html
<!-- ======================================= -->
<!-- ANIMATED OBJECTS                         -->
<!-- Paste INSIDE <a-scene>                  -->
<!-- ======================================= -->

<!-- 🔄 SPINNING Box — Rotates 360° forever -->
<!-- Like a spinning display in a jewelry shop -->
<a-box
  position="-3 1 -4"
  color="#4CC3D9"
  class="clickable"
  animation="property: rotation; to: 0 360 0; loop: true; dur: 3000">
</a-box>

<!-- ⬆️⬇️ BOUNCING Sphere — Goes up and down -->
<!-- Like a basketball being dribbled -->
<a-sphere
  position="0 1 -4"
  radius="0.5"
  color="#EF2D5E"
  class="clickable"
  animation="property: position; to: 0 2.5 -4; dir: alternate; loop: true; dur: 1000">
</a-sphere>

<!-- 📈📉 PULSING Cylinder — Grows and shrinks -->
<!-- Like a heartbeat animation -->
<a-cylinder
  position="3 0.75 -4"
  radius="0.5"
  height="1.5"
  color="#FFC65D"
  class="clickable"
  animation="property: scale; to: 1.3 1.3 1.3; dir: alternate; loop: true; dur: 800">
</a-cylinder>
```

---

## 📝 CODE CHUNK 8B: Multiple Animations on One Object

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
  class="clickable"
  animation__spin="property: rotation; to: 0 360 0; loop: true; dur: 2000"
  animation__bounce="property: position; to: 0 2.5 -3; dir: alternate; loop: true; dur: 1500">
</a-box>
```

---

## 📝 CODE CHUNK 8C: Color Fade Animation

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
  class="clickable"
  animation="property: color; to: #0000FF; dir: alternate; loop: true; dur: 2000">
</a-sphere>
```

---

## 🧠 Animation Properties Explained:

| Property | What It Does | Values | Example |
|----------|-------------|--------|---------|
| `property` | What to animate | `rotation`, `position`, `scale`, `color`, `opacity` | `property: rotation` |
| `to` | End value | Depends on property | `to: 0 360 0` |
| `from` | Start value (optional) | Defaults to current | `from: 0 0 0` |
| `loop` | Repeat? | `true` or `false` or a number | `loop: true` |
| `dur` | Duration in milliseconds | Number | `dur: 3000` (3 seconds) |
| `dir` | Direction | `normal`, `alternate`, `reverse` | `dir: alternate` (back & forth) |
| `easing` | Speed curve | `linear`, `easeInOutQuad`, etc. | `easing: easeInOutQuad` |
| `delay` | Wait before starting | Milliseconds | `delay: 1000` (wait 1 sec) |

### Duration Guide:

| Value | Time | Speed |
|-------|------|-------|
| `dur: 500` | 0.5 seconds | Very fast ⚡ |
| `dur: 1000` | 1 second | Fast |
| `dur: 3000` | 3 seconds | Normal |
| `dur: 5000` | 5 seconds | Slow |
| `dur: 10000` | 10 seconds | Very slow 🐢 |

---

## 📚 Official A-Frame Docs for This Section

| Topic | Link |
|-------|------|
| Animation Component | https://aframe.io/docs/1.7.0/components/animation.html |

---

<a name="part-9"></a>
# 🌍 PART 9 — 360° Sky & Environment

## 🎯 What is a 360° Sky?

Instead of a flat color background, you can wrap a **360° photo** around your entire world — like standing inside a giant snow globe with a photo printed on the inside!

**Real-Life Example:** Like a Google Street View panorama, but you're standing inside it in VR! 🌆

---

## 📝 CODE CHUNK 9A: 360° Photo Sky

```html
<!-- ======================================= -->
<!-- 360° PANORAMIC SKY                      -->
<!-- Replace <a-sky color="..."> with this   -->
<!-- ======================================= -->

<a-assets>
  <!-- Load the 360° image -->
  <img id="sky-360" src="https://cdn.aframe.io/360-image-gallery-boilerplate/img/city.jpg">
</a-assets>

<!-- This wraps the image around you in a full 360° sphere -->
<!-- Like standing inside a snow globe with a city photo -->
<a-sky src="#sky-360"></a-sky>
```

---

## 📝 CODE CHUNK 9B: Gradient Sky with Fog

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

## 📚 Official A-Frame Docs for This Section

| Topic | Link |
|-------|------|
| Sky Primitive | https://aframe.io/docs/1.7.0/primitives/a-sky.html |
| Fog Component | https://aframe.io/docs/1.7.0/components/fog.html |
| 360° Image Gallery Guide | https://aframe.io/docs/1.7.0/guides/building-a-360-image-gallery.html |

---

<a name="part-10"></a>
# 💡 PART 10 — Lighting & Shadows

## 🎯 Why Add Lights?

By default, A-Frame adds basic lighting. But custom lights make your scene look **way more realistic** — like the difference between a phone flashlight and professional studio lighting! 📸

---

## 📝 CODE CHUNK 10: Custom Lighting

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

### Light Types Explained:

| Type | What It Does | Real-Life Example |
|------|-------------|-------------------|
| `ambient` | Soft light everywhere | Light coming through curtains |
| `directional` | Parallel rays from one direction | The sun ☀️ |
| `point` | Light from a single point in all directions | A light bulb 💡 |
| `spot` | Cone-shaped light | Flashlight / stage spotlight 🔦 |

---

## 📚 Official A-Frame Docs for This Section

| Topic | Link |
|-------|------|
| Light Component | https://aframe.io/docs/1.7.0/components/light.html |
| Shadow Component | https://aframe.io/docs/1.7.0/components/shadow.html |

---

<a name="part-11"></a>
# 🔊 PART 11 — Sound & Audio

## 🎯 Why Add Sound?

Sound makes VR feel **real**. Without it, VR is like watching a movie on mute! 🔇

---

## 📝 CODE CHUNK 11A: Background Music

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

> ⚠️ **Note:** Most browsers block autoplay audio. The user might need to click/interact with the page first before audio plays. This is a browser security policy, not an A-Frame bug.

---

## 📝 CODE CHUNK 11B: Sound Effect on Click

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

### How it works:
- `sound="src: #click-sound"` → Which audio file to play
- `on: click` → When to play it (triggers on click event)

---

## 📚 Official A-Frame Docs for This Section

| Topic | Link |
|-------|------|
| Sound Component | https://aframe.io/docs/1.7.0/components/sound.html |
| `<a-sound>` Primitive | https://aframe.io/docs/1.7.0/primitives/a-sound.html |

---

<a name="part-12"></a>
# ✏️ PART 12 — Text in VR

## 🎯 Why Add Text?

Add floating labels, titles, instructions, or signs to your VR world!

**Real-Life Example:** Like subtitles in a movie, but floating in 3D space! Or like signs in a museum! 🏛️

---

## 📝 CODE CHUNK 12: 3D Text

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

### Text Properties:

| Property | What It Does | Example |
|----------|-------------|---------|
| `value` | The text to display | `value="Hello World"` |
| `position` | Where in 3D space | `position="0 2 -3"` |
| `align` | Text alignment | `left`, `center`, `right` |
| `color` | Text color | `color="#FFFFFF"` (white) |
| `width` | Width of text block | `width="6"` |
| `font` | Font style | `mozillavr`, `roboto`, `exo2bold` |

---

## 📚 Official A-Frame Docs for This Section

| Topic | Link |
|-------|------|
| Text Component | https://aframe.io/docs/1.7.0/components/text.html |
| `<a-text>` Primitive | https://aframe.io/docs/1.7.0/primitives/a-text.html |

---

<a name="deployment"></a>
# 🚀 Deploy: GitHub Pages + TinyURL → Meta Quest 3s

## 📤 Step 1: Upload to GitHub

1. Go to **GitHub.com** → Sign in
2. Click **"New"** (green button) to create a new repository
3. Name it: `vr-workshop` (or whatever you like)
4. Make it **Public** ✅
5. Check **"Add a README file"** ✅
6. Click **"Create Repository"**
7. Click **"Add file"** → **"Upload files"**
8. Drag your `index.html` (and `models/`, `textures/`, `audio/` folders if you have them)
9. Click **"Commit changes"**

---

## 🌐 Step 2: Enable GitHub Pages

1. Go to your repo's **Settings** tab (gear icon ⚙️)
2. In the left sidebar, click **"Pages"**
3. Under **"Branch"**:
   - Select **`main`** branch
   - Select **`/ (root)`** folder
   - Click **"Save"**
4. **Wait 1-2 minutes** ⏳
5. Your link will appear at the top:
   ```
   https://YourUsername.github.io/vr-workshop/
   ```

> 💡 **If it says 404:** Wait another minute and refresh. GitHub Pages takes 1-5 minutes to deploy the first time.

---

## 🔗 Step 3: Shorten with TinyURL

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

## 🥽 Step 4: Open on Meta Quest 3s

### Option A: Type the Link 📝
1. Put on your Quest headset
2. Open the **Browser** app
3. Type the TinyURL (e.g., `tinyurl.com/vr-workshop-2026`)
4. Press Enter

### Option B: Send Link to Phone 📱 (SMART!)
1. Send the TinyURL to yourself on **WhatsApp/Messenger**
2. Open it on your phone
3. Quest may auto-detect it → "Open in VR?"
4. Click YES!

### Option C: QR Code 📸 (EASIEST!)
1. Go to any QR generator (e.g., https://www.qr-code-generator.com/)
2. Paste your TinyURL
3. Download the QR code
4. Scan it with Quest browser → Opens automatically!

---

## 🎮 Step 5: Test in VR

1. Click the **"Enter VR"** button (bottom right of the page)
2. Pick up your controllers
3. **YOU'RE IN!** 🎉

### ✅ Verification Checklist:

| Test | Expected Result |
|------|----------------|
| Look around | Camera follows your head movement |
| Hold controllers | See cyan (left) and magenta (right) lasers |
| Point at clickable object | Laser stops on the object |
| Press trigger | Object changes color (if script is added) |

---

<a name="examples"></a>
# 🎯 Complete Copy-Paste Examples

## 📝 EXAMPLE A: Full Textured Interactive Scene

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
            this.el.addEventListener('click', () => {
              const randomColor = '#' + Math.floor(Math.random() * 16777215).toString(16).padStart(6, '0');
              this.el.setAttribute('color', randomColor);
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

## 📝 EXAMPLE B: Custom Objects + Animations Scene

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
            this.el.addEventListener('click', () => {
              const randomColor = '#' + Math.floor(Math.random() * 16777215).toString(16).padStart(6, '0');
              this.el.setAttribute('color', randomColor);
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

## 📝 EXAMPLE C: Tinkercad Model Import Scene

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
            this.el.addEventListener('click', () => {
              const randomColor = '#' + Math.floor(Math.random() * 16777215).toString(16).padStart(6, '0');
              this.el.setAttribute('color', randomColor);
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
# 📌 Troubleshooting — Fix Common Problems

| # | Problem | Solution |
|---|---------|----------|
| 1 | GitHub Pages shows 404 | Wait 2-5 minutes after enabling. Make sure file is named `index.html` (lowercase!) |
| 2 | No "Enter VR" button | Must be HTTPS. GitHub Pages gives HTTPS automatically ✅ |
| 3 | Controllers not showing | Make sure Quest controllers are turned ON and paired |
| 4 | Laser not appearing | Check that you have the `laser-controls` and `line` attributes on controller entities |
| 5 | Can't click objects | Make sure object has `class="clickable"` |
| 6 | 3D model not visible | Check the URL is correct. Try adjusting `scale` (model may be too tiny or too huge) |
| 7 | Model is upside down | Add `rotation="-90 0 0"` or `rotation="0 180 0"` |
| 8 | Texture not loading | Make sure image URL is HTTPS. Check for typos in the `id` and `src` |
| 9 | Scene is very dark | Your 3D model might need custom lights. Add ambient + directional lights (see PART 10) |
| 10 | Audio not playing | Browsers block autoplay. User must interact with page first (click "Enter VR") |
| 11 | Everything is white | Check that your A-Frame `<script>` tag is loading correctly. Open browser console (F12) for errors |
| 12 | Slow loading | Use the Asset System (`<a-assets>`) to preload. Compress textures. Use smaller 3D models |

### 🔧 How to Debug:
1. Open your page in a regular browser (Chrome/Edge)
2. Press **F12** to open Developer Tools
3. Go to **Console** tab → Look for red errors
4. Fix the errors → Re-upload to GitHub → Wait for Pages to update

---

# 📚 All Official A-Frame Documentation Links

| Category | Topic | Link |
|----------|-------|------|
| **Getting Started** | Introduction | https://aframe.io/docs/1.7.0/introduction/ |
| **Getting Started** | Installation | https://aframe.io/docs/1.7.0/introduction/installation.html |
| **Getting Started** | HTML & Primitives | https://aframe.io/docs/1.7.0/introduction/html-and-primitives.html |
| **Guides** | Building a Basic Scene | https://aframe.io/docs/1.7.0/guides/building-a-basic-scene.html |
| **Guides** | Building a 360° Gallery | https://aframe.io/docs/1.7.0/guides/building-a-360-image-gallery.html |
| **Guides** | 3D Models | https://aframe.io/docs/1.7.0/introduction/models.html |
| **Guides** | Hosting & Publishing | https://aframe.io/docs/1.7.0/introduction/hosting-and-publishing.html |
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
| **Interactions** | Events & DOM APIs | https://aframe.io/docs/1.7.0/introduction/javascript-events-dom-apis.html |
| **Interactions** | Interactions Guide | https://aframe.io/docs/1.7.0/introduction/interactions-and-controllers.html |
| **Learning** | A-Frame School | https://aframe.io/aframe-school/ |
| **Community** | Discord Server | https://supermedium.com/discord |
| **Community** | Stack Overflow | https://stackoverflow.com/questions/tagged/aframe |
| **Resources** | Free 3D Models (Sketchfab) | https://sketchfab.com/search?type=models&features=downloadable |
| **Resources** | Free Textures (Poly Haven) | https://polyhaven.com/textures |
| **Resources** | Tinkercad | https://www.tinkercad.com/ |

---

# ✅ Workshop Checklist

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

# 🚀 What's Next? (Advanced Topics for Future Workshops)

Once students master the basics, explore these:

| Feature | Difficulty | Description |
|---------|-----------|-------------|
| Thumbstick Movement | ⭐⭐ | Walk around using controller thumbstick |
| Teleport Locomotion | ⭐⭐ | Point and click to teleport |
| Grab & Throw | ⭐⭐⭐ | Pick up objects with grip button |
| Physics Engine | ⭐⭐⭐ | Objects fall with gravity, bounce, collide |
| Hand Tracking | ⭐⭐⭐ | Use bare hands instead of controllers |
| Sound Effects | ⭐⭐ | Spatial audio that changes with distance |
| Multiplayer VR | ⭐⭐⭐⭐ | Multiple people in same VR world |
| AR (Augmented Reality) | ⭐⭐⭐ | Place virtual objects in real world |
| VR UI Menus | ⭐⭐⭐ | Interactive menus/buttons in VR |
| Particle Effects | ⭐⭐ | Fire, smoke, sparkle effects |

---

**Made with ❤️ for VR Workshop 2026**  
**A-Frame Version:** 1.7.1  
**Last Updated:** February 15, 2026  
**Hosting:** GitHub Pages + TinyURL (No Glitch!)  
**Hardware:** Meta Quest 3s
