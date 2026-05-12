# 🥽 A-Frame VR Workshop — Kid-Friendly Guide (Ages 13–16)

> **Made for teens:** short steps, simple words, and lots of real-life examples.  
> **Use with:** [Code Chunks.md](Code%20Chunks.md) (copy-paste code)  
> **Want the full version?** See [COMPLETE-WORKSHOP-GUIDE.md](COMPLETE-WORKSHOP-GUIDE.md)

---

## ✅ What You Need

- A laptop or desktop (Chrome works best)
- Internet connection
- This repo opened on your computer
- (Optional) A Meta Quest 3s headset

---

## 🧭 How This Guide Works

- **🟢 Easy:** just HTML tags (no JavaScript)
- **🟡 Medium:** combining shapes or loading models
- **🔴 Advanced:** controllers + interactions

> **Tip:** Go in order. Each part builds the next part.

---

## 📚 Table of Contents

1. [Put Your VR World Online](#part-1)
2. [Start Your Scene](#part-2)
3. [Add Basic Shapes](#part-3)
4. [Add Textures (Skins)](#part-4)
5. [Add Floor + Sky](#part-5)
6. [Add Lights](#part-6)
7. [Add Text Labels](#part-7)
8. [Add Animations](#part-8)
9. [Add Sounds](#part-9)
10. [Build Custom Objects](#part-10)
11. [Import 3D Models (Tinkercad)](#part-11)
12. [Add Quest Controllers](#part-12)
13. [Make Objects Clickable](#part-13)
14. [Deploy to Quest](#part-14)
15. [Quick Troubleshooting](#part-15)

---

<a name="part-1"></a>
## 🌐 1 — Put Your VR World Online (🟢)

**Goal:** Get your scene on the internet so others can open it.

**Real-life example:** This is like uploading a TikTok so anyone can watch it.

**Steps:**
1. Make sure your file is named **`index.html`**
2. Upload to GitHub
3. Turn on **GitHub Pages**
4. Share the link (TinyURL helps)

> Full steps are in Part 14 of the main guide.

---

<a name="part-2"></a>
## 🧱 2 — Start Your Scene (🟢)

**Goal:** Create the empty VR room.

**Real-life example:** This is like opening a blank Minecraft world.

**Use Code Chunk:** **#1 Starter Template** in [Code Chunks.md](Code%20Chunks.md)

Simplest template (copy first):

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My VR Scene</title>
    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
  </head>
  <body>
    <a-scene></a-scene>
  </body>
</html>
```

What to do using this template:
1. Save the file as **`index.html`**
2. Open it in Chrome to make sure the scene loads
3. Add shapes inside `<a-scene>` (see Part 3)
4. Change colors, positions, and sizes to make it yours

Quick starter (copy once):

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My VR Scene</title>
    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
  </head>
  <body>
    <a-scene>
      <!-- Your objects go here -->
    </a-scene>
  </body>
</html>
```

Simpler explained version (with comments):

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My VR Scene</title>
    <!-- Loads the A-Frame engine (so VR tags work) -->
    <script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
  </head>
  <body>
    <!-- This is the VR room -->
    <a-scene>
      <!-- Put your shapes here -->
    </a-scene>
  </body>
</html>
```

---

<a name="part-3"></a>
## 🧊 3 — Add Basic Shapes (🟢)

**Goal:** Place boxes, balls, and cylinders in your world.

**Real-life example:** These are like LEGO pieces you can stack and move.

**Use Code Chunk:** **#6 Basic Shapes**

Try a few and change the colors:

```html
<a-box position="-1 0.5 -3" color="#4CC3D9"></a-box>
<a-sphere position="0 1.25 -4" radius="1.25" color="#EF2D5E"></a-sphere>
<a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color="#FFC65D"></a-cylinder>
```

Simpler explained version (with comments):

```html
<!-- A cube floating in front of you -->
<a-box position="-1 0.5 -3" color="#4CC3D9"></a-box>

<!-- A ball a little higher up -->
<a-sphere position="0 1.25 -4" radius="1.25" color="#EF2D5E"></a-sphere>

<!-- A tall can on the right -->
<a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color="#FFC65D"></a-cylinder>
```

---

<a name="part-4"></a>
## 🎨 4 — Add Textures (Skins) (🟢)

**Goal:** Put images on shapes so they look real.

**Real-life example:** Like changing a phone case or wrapping a gift.

**Use Code Chunk:** **#2 Assets** and **#7 Textured Objects**

Tip: textures are just images that “paint” your shapes.

Simpler explained version (with comments):

```html
<!-- Load a texture image first -->
<a-assets>
  <img id="wood" src="https://cdn.aframe.io/a-painter/images/wood.jpg">
</a-assets>

<!-- Use the texture on a box -->
<a-box position="0 1 -3" src="#wood"></a-box>
```

---

<a name="part-5"></a>
## 🌤️ 5 — Add Floor + Sky (🟢)

**Goal:** Give your world a ground and a background.

**Real-life example:** Like setting a wallpaper and a floor in your room.

**Use Code Chunk:** **#8 Floor + Sky**

Simpler explained version (with comments):

```html
<!-- The ground you stand on -->
<a-plane position="0 0 -4" rotation="-90 0 0" width="8" height="8" color="#7BC8A4"></a-plane>

<!-- The background color of the world -->
<a-sky color="#CCE7FF"></a-sky>
```

---

<a name="part-6"></a>
## 💡 6 — Add Lights (🟢)

**Goal:** Make your scene look less flat.

**Real-life example:** A flashlight makes things look brighter and shows shadows.

**Use Code Chunk:** **#5 Lights**

Try changing light color to match a mood (blue = night, orange = sunset).

Simpler explained version (with comments):

```html
<!-- Soft light everywhere -->
<a-light type="ambient" color="#FFFFFF" intensity="0.5"></a-light>

<!-- Sunlight from above -->
<a-light type="directional" color="#FFF6D6" intensity="0.8" position="1 3 2"></a-light>
```

---

<a name="part-7"></a>
## ✏️ 7 — Add Text Labels (🟢)

**Goal:** Put signs or titles inside your world.

**Real-life example:** Like labels in a museum or a scoreboard in a game.

**Use Code Chunk:** **#9 Text Labels**

Simpler explained version (with comments):

```html
<!-- Floating text sign -->
<a-text value="Welcome to my VR world!" position="0 2 -3" align="center" color="#FFFFFF"></a-text>
```

---

<a name="part-8"></a>
## 🌀 8 — Add Animations (🟢)

**Goal:** Make objects move or spin.

**Real-life example:** A fidget spinner, bouncing ball, or blinking neon sign.

**Use Code Chunk:** **#11 Animations**

Simpler explained version (with comments):

```html
<!-- Spin a box forever -->
<a-box position="0 1 -3" color="#4CC3D9"
  animation="property: rotation; to: 0 360 0; loop: true; dur: 3000">
</a-box>
```

---

<a name="part-9"></a>
## 🔊 9 — Add Sounds (🟡)

**Goal:** Play audio when you click or load the scene.

**Real-life example:** Games play a “click” sound when you press a button.

**Use Code Chunk:** **#14 Click to Play Sound**

Simpler explained version (with comments):

```html
<!-- Background sound that starts on load -->
<a-entity sound="src: url(https://cdn.aframe.io/basic-guide/audio/backgroundnoise.wav); autoplay: true; loop: true; volume: 0.3"></a-entity>
```

---

<a name="part-10"></a>
## 🧩 10 — Build Custom Objects (🟡)

**Goal:** Combine shapes to build bigger things.

**Real-life example:** Build a snowman by stacking snowballs.

Try this idea:
- A house = box + triangle roof  
- A tree = cylinder trunk + sphere leaves

> See Part 9 in the main guide for full examples.

---

<a name="part-11"></a>
## 🧱 11 — Import 3D Models (Tinkercad) (🟡)

**Goal:** Bring in models you design.

**Real-life example:** Draw a toy in a 3D app, then place it in your game world.

**Use Code Chunk:** **#12 3D Models from Tinkercad**

Quick steps:
1. Build in **Tinkercad**
2. Export as **GLB**
3. Upload to GitHub
4. Load it into your scene

---

<a name="part-12"></a>
## 🎮 12 — Add Quest Controllers (🔴)

**Goal:** Use VR hand controllers with laser pointers.

**Real-life example:** Like using a TV remote to point and click.

**Use Code Chunk:** **#4 Meta Quest VR Controllers**

---

<a name="part-13"></a>
## 🖱️ 13 — Make Objects Clickable (🔴)

**Goal:** Click an object to make it react.

**Real-life example:** Touch buttons on your phone and the color changes.

**Use Code Chunks:**  
- **#13 Click-to-Change-Color Script**  
- Add `class="clickable"` to any object you want to click

---

<a name="part-14"></a>
## 🚀 14 — Deploy to Quest (🟢)

**Goal:** Open your scene on a headset.

**Real-life example:** Opening a website on a phone, but inside VR.

Steps:
1. Enable **GitHub Pages**
2. Copy the link
3. Open the link in the **Meta Quest Browser**

> Full steps are in Part 14 of the main guide.

---

<a name="part-15"></a>
## 🧰 15 — Quick Troubleshooting (🔧)

- **Nothing shows up?** Check that your tags are inside `<a-scene>`.
- **Scene won’t load?** Make sure the file name is **index.html**.
- **Textures are missing?** Check the image URL.
- **Click doesn’t work?** Add `class="clickable"` and the click script.

---

## 🎯 Mini Challenges (Fun Practice)

1. Make a **space scene** with dark sky, bright stars, and a spinning planet.
2. Build a **school hallway** with signs for classrooms.
3. Create a **mini game**: click 3 objects to turn them all green.

---

## 🤖 Go Further with Copilot or Anti Gravity AI

If your class provides **Copilot** or **Anti Gravity AI** (an AI helper), use them to get ideas and speed up changes. If you’re not sure how to access them, ask your instructor.

- Ask for **new object ideas** (e.g., “Give me a simple tree made of shapes”)
- Ask for **color palettes** or themes (space, underwater, neon city)
- Ask for **small code chunks** (like a spinning sign or glowing orb)

Always paste the result into your `index.html` and **test in the browser** to make sure it works.

---

## ✅ You Did It

You now have a working VR world. Keep testing, changing colors, and adding objects.  
The more you play with it, the better it gets!
