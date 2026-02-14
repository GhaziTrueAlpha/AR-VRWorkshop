# 🥽 Complete Meta Quest 3s A-Frame Workshop Guide

> **Workshop-Ready**: Every code chunk is copy-paste ready!  
> **Beginner-Friendly**: Explained like you're 15 and just started coding  
> **GitHub Pages**: Designed specifically for GitHub Pages hosting + TinyURL

---

## 📚 Table of Contents

1. [Introduction & Setup](#intro)
2. [Basic Scene Setup](#part-1)
3. [Meta Quest Controllers](#part-2)
4. [Making Objects Clickable](#part-3)
5. [Interaction Scripts](#part-4)
6. [Deployment: GitHub Pages + TinyURL](#deployment)
7. [Adding Textures](#part-5)
8. [Importing 3D Models from Tinkercad](#part-6)
9. [Building Custom 3D Objects](#part-7)
10. [Adding Animations](#part-8)
11. [Complete Workshop Examples](#part-9)

---

<a name="intro"></a>
# 🌐 How We'll Host Our VR Experience

**Our Simple 3-Step Process:**
1. ✍️ **Create** your `index.html` file (copy chunks from this guide)
2. ☁️ **Upload** to GitHub repository
3. 🌍 **Enable GitHub Pages** → Get link → **Shorten with TinyURL** → **Open in Meta Quest 3s**

> 💡 **Think of it like Instagram:**  
> You create content (HTML), upload to GitHub (like Instagram), GitHub Pages shows it to the world (like your profile), and TinyURL makes it easy to share (like a bio link)!

---

<a name="part-1"></a>
# 📁 PART 1 — Basic Scene Setup

## 🎬 What is A-Frame?

**Think of A-Frame like LEGO blocks for VR:**
- Each block is a 3D shape (`<a-box>`, `<a-sphere>`)
- You place them in a virtual room (`<a-scene>`)
- No coding degree needed - just copy & paste!

**Real-Life Example:** Just like Minecraft where you place blocks, A-Frame lets you place 3D objects using simple HTML tags!

---

## 📝 Your First VR Scene

Create a file called `index.html` and paste this:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My First VR Scene</title>
    <meta name="description" content="VR Workshop Demo">
    
    <!-- A-Frame Library - Like importing React or jQuery -->
    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
  </head>

  <body>
    <!-- a-scene = Your VR World Container (like a Minecraft world) -->
    <a-scene>

      <!-- SCENE OBJECTS - Like placing furniture in a room -->
      
      <!-- Box: position = "left/right  up/down  forward/back" -->
      <a-box 
        position="-1 0.5 -3" 
        rotation="0 45 0" 
        color="#4CC3D9">
      </a-box>
      
      <!-- Sphere: Think of it like a basketball -->
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
      
      <!-- Plane: The floor/ground -->
      <a-plane 
        position="0 0 -4" 
        rotation="-90 0 0" 
        width="4" 
        height="4" 
        color="#7BC8A4">
      </a-plane>
      
      <!-- Sky: The background (like a Zoom virtual background) -->
      <a-sky color="#ECECEC"></a-sky>

    </a-scene>
  </body>
</html>
```

---

## 🧠 Code Explanation (In Simple English)

### What Each Line Does:

| Code | What It Means | Real-Life Example |
|------|---------------|-------------------|
| `<a-scene>` | Your VR room/world | The Fortnite map |
| `position="-1 0.5 -3"` | Where object sits (X Y Z) | GPS coordinates but for VR |
| `rotation="0 45 0"` | Which way it's turned | Turning your phone landscape |
| `color="#4CC3D9"` | The object's color | Instagram filter color code |
| `<a-box>` | A 3D cube | Rubik's cube |
| `<a-sphere>` | A 3D ball | Basketball |
| `<a-cylinder>` | A 3D tube | Red Bull can |
| `<a-plane>` | A flat surface | Floor in your house |
| `<a-sky>` | The background | Sky in GTA/Fortnite |

### Position System Explained:

```
position="X  Y  Z"
         👆 👆 👆
         |  |  |
         |  |  +-- Forward(-) / Backward(+)
         |  +---- Up(+) / Down(-)
         +------- Right(+) / Left(-)
```

**Example:** `position="2 1 -3"` means:
- `2` = 2 units to the RIGHT
- `1` = 1 unit UP from ground
- `-3` = 3 units IN FRONT of you

---

## 📚 Official A-Frame Documentation

- **Scene**: https://aframe.io/docs/1.7.0/core/scene.html
- **Primitives (Shapes)**: https://aframe.io/docs/1.7.0/primitives/a-box.html
- **Position/Rotation**: https://aframe.io/docs/1.7.0/components/position.html

---

<a name="part-2"></a>
# 🎮 PART 2 — Add Meta Quest 3s Controllers

## 🎯 What Are We Adding?

**Think of controllers like lightsabers in Star Wars:**
- They shoot laser beams
- Point at things and click to interact
- Track your hand movements in real-time

**Real-Life Example:** Like using a laser pointer in a presentation, but in VR! 🔴

---

## 📍 Where to Paste?

Paste inside `<a-scene>`, right after the opening tag:

```html
<a-scene>
  <!-- PASTE CONTROLLER CODE HERE -->
  
  <!-- Your objects come after -->
</a-scene>
```

---

## 🔹 The Controller Code:

```html
<!-- ========================= -->
<!-- CAMERA + CONTROLLER RIG -->
<!-- Paste INSIDE <a-scene> at the TOP -->
<!-- ========================= -->

<!-- "rig" = Your VR body (head + hands) -->
<a-entity id="rig">

  <!-- VR Camera = Your Eyes/Head -->
  <!-- Think: This is your POV like in Call of Duty -->
  <a-entity 
    camera 
    position="0 1.6 0" 
    look-controls>
  </a-entity>

  <!-- LEFT CONTROLLER = Your Left Hand -->
  <a-entity
    id="leftController"
    meta-touch-controls="hand: left"
    laser-controls="hand: left"
    raycaster="objects: .clickable; far: 20"
    line="color: cyan">
  </a-entity>

  <!-- RIGHT CONTROLLER = Your Right Hand -->
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

## 🧠 What Each Part Does:

### 🎥 Camera:
```html
<a-entity camera position="0 1.6 0" look-controls>
```
- **`camera`** = Your eyes in VR (first-person view)
- **`position="0 1.6 0"`** = Height at 1.6m (5'3" tall - average human eye height)
- **`look-controls`** = Move head to look around (like real life)

### 🕹️ Controller Parts:

```html
<a-entity
  id="leftController"                        ← Name it (like naming a pet)
  meta-touch-controls="hand: left"           ← Connect to Quest controller
  laser-controls="hand: left"                ← Show laser beam
  raycaster="objects: .clickable; far: 20"   ← Detect what laser hits
  line="color: cyan">                        ← Laser color (cyan = light blue)
</a-entity>
```

#### Breaking It Down:

| Part | What It Does | Example |
|------|--------------|---------|
| `meta-touch-controls="hand: left"` | Connects to your physical Quest controller | Like pairing AirPods to iPhone |
| `laser-controls="hand: left"` | Shoots a laser beam from controller | Like a laser pointer in presentations |
| `raycaster="objects: .clickable; far: 20"` | Detects what the laser hits (only `.clickable` objects, up to 20 units away) | Like motion sensors that detect movement |
| `line="color: cyan"` | Color of your laser beam (left=cyan, right=magenta) | So you know which hand is which! |

---

## 🎮 Controller Buttons:

The Meta Quest 3s controllers have:
- **Trigger** (index finger) - Main click button ← WE USE THIS
- **Grip** (middle finger) - Grab button
- **Thumbstick** - Movement
- **A/B buttons** (right hand)
- **X/Y buttons** (left hand)

---

## 📚 Official A-Frame Documentation

- **Camera**: https://aframe.io/docs/1.7.0/components/camera.html
- **Meta Touch Controls**: https://aframe.io/docs/1.7.0/components/meta-touch-controls.html
- **Laser Controls**: https://aframe.io/docs/1.7.0/components/laser-controls.html
- **Raycaster**: https://aframe.io/docs/1.7.0/components/raycaster.html

---

<a name="part-3"></a>
# 🖱 PART 3 — Make Objects Clickable

## 🎯 What Does "Clickable" Mean?

**Think of it like Instagram posts:**
- Regular posts = You can scroll past them
- Posts with "❤️ Like" button = You can click/tap them
- `class="clickable"` = Tells VR "Hey, this object can be clicked!"

**Without `class="clickable"`:** Your laser goes through it (like a ghost 👻)  
**With `class="clickable"`:** Your laser stops and you can click it! ✅

---

## 🔹 How to Make ANY Object Clickable

Just add this one line:

```html
class="clickable"
```

---

## 📝 Examples:

### Before (Not Clickable):
```html
<a-box position="-1 0.5 -3" color="#4CC3D9"></a-box>
```
**Result:** Laser goes through it ❌

### After (Clickable):
```html
<a-box 
  position="-1 0.5 -3" 
  color="#4CC3D9"
  class="clickable">
</a-box>
```
**Result:** Laser stops on it, you can click! ✅

---

## 🎨 Make Multiple Objects Clickable:

```html
<!-- Clickable Box -->
<a-box 
  position="-1 0.5 -3" 
  color="#4CC3D9"
  class="clickable">
</a-box>

<!-- Clickable Sphere -->
<a-sphere 
  position="0 1.25 -5" 
  radius="1.25" 
  color="#EF2D5E"
  class="clickable">
</a-sphere>

<!-- NOT Clickable - Laser goes through -->
<a-plane 
  position="0 0 -4" 
  rotation="-90 0 0" 
  width="4" 
  height="4" 
  color="#7BC8A4">
</a-plane>
```

---

## 🧠 Why Do We Need This?

Remember in **PART 2** we wrote:
```html
raycaster="objects: .clickable; far: 20"
```

This tells the raycaster:
- **"objects: .clickable"** = "Only detect objects with class='clickable'"
- **Like a bouncer at a club** = Only people on the list get in! 🚪

---

## 📚 Official A-Frame Documentation

- **Raycaster**: https://aframe.io/docs/1.7.0/components/raycaster.html
- **Event Handling**: https://aframe.io/docs/1.7.0/introduction/interactions-and-controllers.html

---

<a name="part-4"></a>
# 🎨 PART 4 — Add Interaction Script

## 🎯 What Does This Do?

**Think of it like TikTok filters:**
- You tap screen → Filter changes
- You click object in VR → Color changes

**Real-Life Example:** Like mood rings that change color when you touch them! 💍✨

---

## 📍 Where to Paste?

Paste inside `<a-scene>` at the bottom, just before `</a-scene>`:

---

## 💻 The Script:

```html
<!-- ========================= -->
<!-- INTERACTION SCRIPT -->
<!-- Paste before </a-scene> -->
<!-- ========================= -->

<script>
  // Step 1: Create a custom component
  AFRAME.registerComponent('click-change-color', {
    init: function () {
      // Step 2: Listen for clicks
      this.el.addEventListener('click', () => {
        // Step 3: Change to random color
        this.el.setAttribute(
          'color',
          '#' + Math.floor(Math.random() * 16777215).toString(16)
        );
      });
    }
  });

  // Step 4: Wait for page to load
  document.addEventListener('DOMContentLoaded', function () {
    // Step 5: Find all clickable objects
    const objects = document.querySelectorAll('.clickable');
    
    // Step 6: Give each object the color-change power
    objects.forEach(obj => {
      obj.setAttribute('click-change-color', '');
    });
  });
</script>
```

---

## 🧠 How It Works:

### The Flow:
```
1. Point laser at object
2. Press trigger button
3. Script hears "click"
4. Generates random color
5. Object changes color
6. ✨ MAGIC! ✨
```

### Code Breakdown:

#### 1. Create Custom Component
```javascript
AFRAME.registerComponent('click-change-color', {
```
**What:** Creates a new A-Frame "superpower"  
**Like:** Creating a custom Snapchat filter

#### 2. Listen for Clicks
```javascript
this.el.addEventListener('click', () => {
```
**What:** Waits for someone to click this object  
**Like:** A doorbell waiting for someone to press it 🚪🔔

#### 3. Generate Random Color
```javascript
'#' + Math.floor(Math.random() * 16777215).toString(16)
```
**Let's break this down:**
- `Math.random()` = Random number 0-1 → `0.846372`
- `* 16777215` = Multiply for color range → `14193826.4`
- `Math.floor()` = Remove decimals → `14193826`
- `.toString(16)` = Convert to hex → `d8a142`
- `'#' +` = Add # → `#d8a142` ✅

**Why 16777215?** 256 red × 256 green × 256 blue = 16,777,216 colors!

#### 4. Apply Color
```javascript
this.el.setAttribute('color', '#d8a142');
```
**What:** Changes the object's color  
**Like:** Using spray paint in GTA

---

## 📚 Official A-Frame Documentation

- **Components**: https://aframe.io/docs/1.7.0/introduction/writing-a-component.html
- **Events**: https://aframe.io/docs/1.7.0/introduction/javascript-events-dom-apis.html

---

<a name="deployment"></a>
# 🚀 GitHub Pages Deployment + TinyURL

## 📤 Step 1: Upload to GitHub

1. Go to **GitHub.com** and sign in
2. Click **"New Repository"** (green button)
3. Name it: `vr-workshop`
4. Make it **Public** ✅
5. Click **"Create Repository"**
6. Upload your `index.html`:
   - Click "Add file" → "Upload files"
   - Drag `index.html`
   - Click "Commit changes"

---

## 🌐 Step 2: Enable GitHub Pages

1. Go to **Settings** tab
2. Click **"Pages"** (left sidebar)
3. Under "Branch":
   - Select `main` branch
   - Select `/root` folder
   - Click **Save**
4. **Wait 1-2 minutes** ⏳
5. Your link appears:
   ```
   https://YourUsername.github.io/vr-workshop/
   ```

---

## 🔗 Step 3: Shorten with TinyURL

1. **Copy your GitHub Pages link**
2. Go to: https://tinyurl.com/
3. **Paste your link**
4. Click **"Make TinyURL!"**
5. Get short link:
   ```
   https://tinyurl.com/my-vr-demo
   ```
6. **Optional:** Customize alias (e.g., `vr-workshop-2026`)

---

## 🥽 Step 4: Open in Meta Quest 3s

### **Option A:** Type Link
1. Put on Quest
2. Open **Browser app**
3. Type TinyURL
4. Press Enter

### **Option B:** Send Link (SMART!)
1. **Send TinyURL to your phone** (WhatsApp/Messenger)
2. **Open link on phone**
3. **Quest auto-detects it!**
4. Notification: "Open in VR?"
5. Click YES!

### **Option C:** QR Code (EASIEST!)
1. Generate QR from TinyURL
2. Scan with Quest browser
3. Opens automatically!

---

## 🎮 Step 5: Test in VR

1. Click **"Enter VR"** button (bottom right)
2. Put on headset
3. Pick up controllers
4. **YOU'RE IN!** 🎉

---

## ✅ Testing:

1. Look around → Head moves camera
2. Hold controllers → See cyan/magenta lasers
3. Point at box → Laser stops
4. Press trigger → Box changes color! 🎨

---

<a name="part-5"></a>
# 🖼️ PART 5 — Adding Textures

## 🎯 What Are Textures?

**Like:**
- Skins in Fortnite/Minecraft
- Wrapping paper on gifts 🎁
- Phone wallpapers

**Without texture:** Flat colors (boring!)  
**With texture:** Realistic (wood, metal, grass)

---

## 📍 Option 1: Direct URLs (Quick)

```html
<!-- Wood Texture -->
<a-box 
  position="-1 0.5 -3" 
  src="https://cdn.aframe.io/a-painter/images/wood.jpg"
  class="clickable">
</a-box>

<!-- 360° Sky -->
<a-sky src="https://cdn.aframe.io/360-image-gallery-boilerplate/img/city.jpg"></a-sky>
```

---

## 📍 Option 2: Asset System (RECOMMENDED ⭐)

**Why better?**
- Preloads (no lag!)
- Reuse textures (saves data)
- Professional way

```html
<a-scene>
  
  <!-- Load textures first -->
  <a-assets>
    <img id="wood" src="https://cdn.aframe.io/a-painter/images/wood.jpg">
    <img id="brick" src="https://cdn.aframe.io/a-painter/images/brick.jpg">
    <img id="grass" src="https://cdn.aframe.io/a-painter/images/floor.jpg">
    <img id="city" src="https://cdn.aframe.io/360-image-gallery-boilerplate/img/city.jpg">
  </a-assets>

  <!-- Use textures by ID (with #) -->
  <a-box position="-1 0.5 -3" src="#wood" class="clickable"></a-box>
  <a-sphere position="0 1.25 -5" src="#brick" class="clickable"></a-sphere>
  <a-plane position="0 0 -4" rotation="-90 0 0" width="10" height="10" src="#grass"></a-plane>
  <a-sky src="#city"></a-sky>

</a-scene>
```

### How It Works:
```html
<!-- Save texture with ID (like saving a contact) -->
<img id="wood" src="https://...wood.jpg">

<!-- Use texture by ID (like calling a contact) -->
<a-box src="#wood"></a-box>

<!-- Reuse! (image loads only ONCE) -->
<a-box src="#wood" position="0 0 -3"></a-box>
<a-box src="#wood" position="2 0 -3"></a-box>
<a-box src="#wood" position="4 0 -3"></a-box>
```

---

## 📍 Option 3: Local Files (From Your GitHub)

### Folder Structure:
```
your-repo/
├── index.html
└── textures/
    ├── wood.jpg
    ├── metal.png
    └── grass.jpg
```

### Upload to GitHub:
1. Create `textures` folder in repo
2. Upload images to that folder
3. Commit changes

### Use in Code:
```html
<a-assets>
  <img id="wood" src="textures/wood.jpg">
  <img id="metal" src="textures/metal.png">
  <img id="grass" src="textures/grass.jpg">
</a-assets>

<a-box position="-1 0.5 -3" src="#wood" class="clickable"></a-box>
```

---

## 🎨 Free Texture Websites:

- **Poly Haven** (polyhaven.com) - Free 4K textures
- **Textures.com** - 15 free credits/day
- **Unsplash.com** - Free photos
- **A-Frame CDN** - Ready VR textures

---

## 📚 Official Documentation

- **Textures**: https://aframe.io/docs/1.7.0/components/material.html
- **Assets**: https://aframe.io/docs/1.7.0/core/asset-management-system.html

---

<a name="part-6"></a>
# 🎨 PART 6 — Import 3D Models from Tinkercad

## 🔧 Step-by-Step:

### 1️⃣ Export from Tinkercad
1. Open design in Tinkercad
2. Click **"Export"** (top right)
3. Choose **"GLTF"** format (`.glb` file)
4. Download

### 2️⃣ Upload to GitHub
1. Go to your repo
2. Create `models` folder
3. Upload your `.glb` file
4. Commit changes
5. **Copy the file URL:**
   ```
   https://raw.githubusercontent.com/YourUsername/vr-workshop/main/models/robot.glb
   ```

### 3️⃣ Add to A-Frame Scene

```html
<a-scene>
  
  <!-- Load model -->
  <a-assets>
    <a-asset-item 
      id="myModel" 
      src="https://raw.githubusercontent.com/YourUsername/vr-workshop/main/models/robot.glb">
    </a-asset-item>
  </a-assets>

  <!-- Place model in scene -->
  <a-entity 
    gltf-model="#myModel" 
    position="0 0 -3" 
    rotation="0 0 0"
    scale="1 1 1"
    class="clickable">
  </a-entity>

</a-scene>
```

---

## 🎯 Common Adjustments:

```html
<!-- Model too big? Scale down -->
<a-entity gltf-model="#myModel" scale="0.1 0.1 0.1"></a-entity>

<!-- Model too small? Scale up -->
<a-entity gltf-model="#myModel" scale="5 5 5"></a-entity>

<!-- Wrong orientation? Rotate -->
<a-entity gltf-model="#myModel" rotation="-90 0 0"></a-entity>

<!-- Add spinning animation -->
<a-entity 
  gltf-model="#myModel" 
  animation="property: rotation; to: 0 360 0; loop: true; dur: 5000">
</a-entity>
```

---

## 📚 Official Documentation

- **GLTF Models**: https://aframe.io/docs/1.7.0/components/gltf-model.html
- **Asset Items**: https://aframe.io/docs/1.7.0/core/asset-management-system.html

---

<a name="part-7"></a>
# 🛠️ PART 7 — Build Custom 3D Objects

## 🏠 Example 1: Simple House

```html
<a-entity position="0 0 -5">
  <!-- Base -->
  <a-box position="0 1 0" width="3" height="2" depth="3" color="#8B4513"></a-box>
  
  <!-- Roof -->
  <a-cone position="0 2.5 0" radius-bottom="2.2" height="1.5" color="#DC143C"></a-cone>
  
  <!-- Door -->
  <a-box position="0 0.5 1.51" width="0.8" height="1.5" depth="0.1" color="#654321"></a-box>
  
  <!-- Windows -->
  <a-plane position="-0.8 1.2 1.51" width="0.6" height="0.6" color="#87CEEB"></a-plane>
  <a-plane position="0.8 1.2 1.51" width="0.6" height="0.6" color="#87CEEB"></a-plane>
</a-entity>
```

---

## 🌳 Example 2: Tree

```html
<a-entity position="3 0 -4">
  <!-- Trunk -->
  <a-cylinder position="0 0.5 0" radius="0.2" height="2" color="#8B4513"></a-cylinder>
  
  <!-- Leaves -->
  <a-sphere position="0 2 0" radius="1" color="#228B22"></a-sphere>
  <a-sphere position="0.5 1.8 0" radius="0.7" color="#32CD32"></a-sphere>
  <a-sphere position="-0.5 1.8 0" radius="0.7" color="#32CD32"></a-sphere>
</a-entity>
```

---

## 🚗 Example 3: Car

```html
<a-entity position="-3 0.5 -4" class="clickable">
  <!-- Body -->
  <a-box width="2" height="0.5" depth="1" color="#FF0000"></a-box>
  
  <!-- Top -->
  <a-box position="0 0.5 -0.2" width="1.2" height="0.5" depth="0.8" color="#8B0000"></a-box>
  
  <!-- Wheels -->
  <a-cylinder position="0.6 -0.25 0.6" radius="0.25" height="0.1" rotation="0 0 90" color="#000"></a-cylinder>
  <a-cylinder position="0.6 -0.25 -0.6" radius="0.25" height="0.1" rotation="0 0 90" color="#000"></a-cylinder>
  <a-cylinder position="-0.6 -0.25 0.6" radius="0.25" height="0.1" rotation="0 0 90" color="#000"></a-cylinder>
  <a-cylinder position="-0.6 -0.25 -0.6" radius="0.25" height="0.1" rotation="0 0 90" color="#000"></a-cylinder>
</a-entity>
```

---

<a name="part-8"></a>
# 🎬 PART 8 — Animations

```html
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

<!-- Multiple Animations on One Object -->
<a-box 
  position="0 1 -3"
  animation__rotate="property: rotation; to: 0 360 0; loop: true; dur: 3000"
  animation__bounce="property: position; to: 0 2 -3; dir: alternate; loop: true; dur: 1000">
</a-box>
```

## Animation Properties:

| Property | What It Does | Example |
|----------|--------------|---------|
| `property` | What to animate | `rotation`, `position`, `scale`, `color` |
| `to` | End value | `0 360 0`, `0 2 -3` |
| `loop` | Repeat forever? | `true` or `false` |
| `dur` | Duration (milliseconds) | `3000` = 3 seconds |
| `dir` | Direction | `alternate` (back & forth) or `normal` |

---

## 📚 Official Documentation

- **Animations**: https://aframe.io/docs/1.7.0/components/animation.html

---

<a name="part-9"></a>
# 🎯 PART 9 — Complete Workshop Examples

## 🎪 Example A: Textured Scene (Copy-Paste Ready!)

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Textured VR Scene</title>
    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
  </head>
  <body>
    <a-scene>
      
      <!-- Assets -->
      <a-assets>
        <img id="wood" src="https://cdn.aframe.io/a-painter/images/wood.jpg">
        <img id="grass" src="https://cdn.aframe.io/a-painter/images/floor.jpg">
        <img id="city" src="https://cdn.aframe.io/360-image-gallery-boilerplate/img/city.jpg">
      </a-assets>

      <!-- Controllers -->
      <a-entity id="rig">
        <a-entity camera position="0 1.6 0" look-controls></a-entity>
        <a-entity meta-touch-controls="hand: left" laser-controls="hand: left" raycaster="objects: .clickable" line="color: cyan"></a-entity>
        <a-entity meta-touch-controls="hand: right" laser-controls="hand: right" raycaster="objects: .clickable" line="color: magenta"></a-entity>
      </a-entity>

      <!-- Objects -->
      <a-box position="-1 0.5 -3" src="#wood" class="clickable"></a-box>
      <a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E" class="clickable"></a-sphere>
      <a-plane position="0 0 -4" rotation="-90 0 0" width="10" height="10" src="#grass"></a-plane>
      <a-sky src="#city"></a-sky>

      <!-- Interaction -->
      <script>
        AFRAME.registerComponent('click-change-color', {
          init: function () {
            this.el.addEventListener('click', () => {
              this.el.setAttribute('color', '#' + Math.floor(Math.random() * 16777215).toString(16));
            });
          }
        });
        document.addEventListener('DOMContentLoaded', function () {
          document.querySelectorAll('.clickable').forEach(obj => obj.setAttribute('click-change-color', ''));
        });
      </script>

    </a-scene>
  </body>
</html>
```

---

## 🏘️ Example B: Custom Objects Scene

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Custom Objects VR</title>
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

      <!-- House -->
      <a-entity position="-3 0 -5" class="clickable">
        <a-box position="0 1 0" width="3" height="2" depth="3" color="#8B4513"></a-box>
        <a-cone position="0 2.5 0" radius-bottom="2.2" height="1.5" color="#DC143C"></a-cone>
        <a-box position="0 0.5 1.51" width="0.8" height="1.5" depth="0.1" color="#654321"></a-box>
      </a-entity>

      <!-- Tree -->
      <a-entity position="3 0 -4">
        <a-cylinder position="0 0.5 0" radius="0.2" height="2" color="#8B4513"></a-cylinder>
        <a-sphere position="0 2 0" radius="1" color="#228B22"></a-sphere>
      </a-entity>

      <!-- Moving Car -->
      <a-entity position="0 0.5 -3" class="clickable"
        animation="property: position; to: 5 0.5 -3; dur: 5000; dir: alternate; loop: true">
        <a-box width="2" height="0.5" depth="1" color="#FF0000"></a-box>
        <a-box position="0 0.5 -0.2" width="1.2" height="0.5" depth="0.8" color="#8B0000"></a-box>
        <a-cylinder position="0.6 -0.25 0.6" radius="0.25" height="0.1" rotation="0 0 90" color="#000"></a-cylinder>
        <a-cylinder position="0.6 -0.25 -0.6" radius="0.25" height="0.1" rotation="0 0 90" color="#000"></a-cylinder>
        <a-cylinder position="-0.6 -0.25 0.6" radius="0.25" height="0.1" rotation="0 0 90" color="#000"></a-cylinder>
        <a-cylinder position="-0.6 -0.25 -0.6" radius="0.25" height="0.1" rotation="0 0 90" color="#000"></a-cylinder>
      </a-entity>

      <!-- Environment -->
      <a-plane position="0 0 -4" rotation="-90 0 0" width="20" height="20" color="#7BC8A4"></a-plane>
      <a-sky color="#87CEEB"></a-sky>

      <!-- Interaction -->
      <script>
        AFRAME.registerComponent('click-change-color', {
          init: function () {
            this.el.addEventListener('click', () => {
              this.el.setAttribute('color', '#' + Math.floor(Math.random() * 16777215).toString(16));
            });
          }
        });
        document.addEventListener('DOMContentLoaded', function () {
          document.querySelectorAll('.clickable').forEach(obj => obj.setAttribute('click-change-color', ''));
        });
      </script>

    </a-scene>
  </body>
</html>
```

---

# 📌 Quick Troubleshooting

| Problem | Solution |
|---------|----------|
| GitHub Pages not working | Wait 2-5 minutes after enabling |
| No "Enter VR" button | Must be HTTPS (GitHub Pages is) |
| Controllers not showing | Make sure Quest controllers are ON |
| Laser not working | Check `raycaster` code |
| Can't click objects | Add `class="clickable"` |
| Model too big/small | Adjust `scale` attribute |
| Model upside down | Adjust `rotation` attribute |
| Texture not loading | Check URL is HTTPS |

---

# ✅ Workshop Checklist

Before sharing with students:

- [ ] All code chunks tested
- [ ] GitHub Pages enabled
- [ ] TinyURL created
- [ ] Tested in Quest browser
- [ ] Controllers working
- [ ] Laser beams visible
- [ ] Click interaction works
- [ ] All examples load properly

---

# 🎓 Learning Resources

- **A-Frame Documentation**: https://aframe.io/docs/
- **A-Frame School**: https://aframe.io/aframe-school/
- **Free 3D Models**: https://sketchfab.com/
- **Free Textures**: https://polyhaven.com/
- **Tinkercad**: https://www.tinkercad.com/

---

# 🚀 Next Level Features

Once students master basics:

- Thumbstick movement
- Teleport locomotion
- Grab & throw physics
- Sound effects
- Particle systems
- Multi-player networking
- Hand tracking
- VR UI menus

---

# 📞 Workshop Support

If students get stuck:
1. Check browser console (F12) for errors
2. Verify GitHub Pages is enabled
3. Test link in regular browser first
4. Make sure code is exactly copied
5. Check all URLs are HTTPS

---

**Made with ❤️ for VR Workshop 2026**  
**Last Updated:** February 15, 2026
