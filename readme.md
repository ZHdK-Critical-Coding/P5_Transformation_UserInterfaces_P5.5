# P5.js: P5.5 Interface

[Deutsch](README_DE.md)

Example for p5.5.js by Kris Heyse, a p5 plugin that adds a UI, panning and
zooming and PNG export. You work in real-world units (millimetres) with
`mmpx()`: the sketch draws random coloured lines on a 200 × 100 mm canvas
that has the right physical size on screen and can be exported at print
resolution.

## Installation

Requirements: a current browser, browser zoom at 100 %.

Adjust `p5.initMetrics()` at the top of `sketch.js` to your display.
`p5.initMetrics(displayDiagonalInInches, exportPPI)`: the first value is
the diagonal of your screen in inches, the second the resolution of the
exported image (0 = screen resolution). The example uses `31.5, 300`.

Libraries (in `libraries/`): p5.js 1.10.0, p5.5.js 0.1.0, p5.sound 1.0.1
(included, not loaded).

## How to Run

1. Open the folder in Visual Studio Code and start Live Server (click
   **Go Live** in the status bar).
2. Use the mouse buttons and mouse wheel to pan and zoom.

Keyboard shortcuts (p5.5 defaults): **F** zoom to fit, **O** zoom 1:1,
**M** max zoom, **E** export PNG, **L** toggle loop, **+** single step,
**Tab** show/hide the panel, **Shift+F** fullscreen.

## Coding Help

- **`sketch.js` → `p5.initMetrics()`**: must be called before the sketch
  starts; this is where you set the display diagonal and export PPI.
- **Variables**: `lineWeightInMillimeters` and `textSizeInMillimeters` –
  sizes in mm, converted to pixels with `mmpx()`.
- **`setup()`**: `createCanvas(mmpx(200), mmpx(100), { seed: 1234 })`
  sets the canvas size in mm; the `seed` option (from p5.5) makes the
  random values repeatable. Then the help text is written onto the canvas.
- **`draw()`**: draws one line per frame with random position and colour
  and a stroke weight of `mmpx(lineWeightInMillimeters)`.
- **`index.html`**: loads p5.js, p5.5.js and `sketch.js` with `defer`.
