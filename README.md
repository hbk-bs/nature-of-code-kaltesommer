# Nature of Code

This project is about observing **patterns, behaviors, and systems in nature** and translating them into a digital sketch.  
I focused on **tree rings**: each ring represents a year in the tree’s life.  
The result is a short animation built with **p5.js**.

---

## Preview

![Tree Rings](Tree+rings-+LaurieKehler.jpg)  
![Child Holding Ring](kid-ring.jpg)

---

## How it works

1. **Setup**  
   - `rings`: list of all generated tree rings  
   - `numRings`: number of rings to draw  
   - `maxRadius`: size of the outermost ring  
   - `currentRing`: keeps track of which ring is drawn  
   - `hasStarted`: controls whether the sketch has started  

   In `setup()` the canvas is created and initialized.  
   `noLoop()` ensures the sketch doesn’t redraw continuously.  
   A **Start button** allows the user to trigger the animation.

2. **draw() – Growing rings**  
   When the button is clicked, `hasStarted` becomes `true`.  
   Each frame creates a new ring shaped with **Perlin Noise** for irregular, organic growth.  
   Previously drawn rings remain visible, so the growth accumulates naturally.

3. **Stopping the loop**  
   Once all rings are drawn, the loop stops.  
   At the edge of the outer ring, the recursive function `drawTree()` draws branching structures.

4. **The Ring class**  
   Each ring is an instance of the `Ring` class.  
   A circle is generated with its radius distorted by **Perlin Noise**, making it look natural and irregular like real tree rings.

5. **drawTree(): Fractal growth**  
   This recursive function draws a main branch, then two smaller angled branches.  
   Repeated over several iterations, this produces **fractal growth** similar to real trees.

6. **Responsiveness**  
   On window resize or reload, the canvas automatically adjusts.  
   This ensures good visibility across devices.

---

## Run the Sketch

Open the result here:  
👉 [zum Ergebnis](rings.html)

---

## Tech Stack

- [p5.js](https://p5js.org/)  
- HTML5 / CSS3  

---

## Author

Project created as part of a study assignment on **digital communication & creative coding**.
