# P5.js: P5.5 Interface

[English](readme.md)

Beispiel für p5.5.js von Kris Heyse, ein p5-Plugin, das eine Oberfläche,
Verschieben und Zoomen sowie PNG-Export hinzufügt. Gearbeitet wird in
realen Einheiten (Millimeter) mit `mmpx()`: Der Sketch zeichnet zufällige
farbige Linien auf eine 200 × 100 mm grosse Zeichenfläche, die am
Bildschirm die richtige physische Grösse hat und in Druckauflösung
exportiert werden kann.

## Installation

Voraussetzungen: ein aktueller Browser, Browser-Zoom auf 100 %.

`p5.initMetrics()` zuoberst in `sketch.js` an den eigenen Bildschirm
anpassen. `p5.initMetrics(displayDiagonalInInches, exportPPI)`: Der erste
Wert ist die Bildschirmdiagonale in Zoll, der zweite die Auflösung des
exportierten Bildes (0 = Bildschirmauflösung). Das Beispiel verwendet
`31.5, 300`.

Bibliotheken (in `libraries/`): p5.js 1.10.0, p5.5.js 0.1.0, p5.sound
1.0.1 (vorhanden, nicht geladen).

## Ausführen

1. Den Ordner in Visual Studio Code öffnen und Live Server starten (in der
   Statusleiste auf **Go Live** klicken).
2. Mit den Maustasten und dem Mausrad verschieben und zoomen.

Tastenkürzel (p5.5-Standard): **F** einpassen, **O** Zoom 1:1, **M**
maximaler Zoom, **E** PNG exportieren, **L** Loop ein/aus, **+** einzelner
Schritt, **Tab** Panel ein-/ausblenden, **Shift+F** Vollbild.

## Coding-Hilfe

- **`sketch.js` → `p5.initMetrics()`**: muss vor dem Start des Sketches
  aufgerufen werden; hier werden Bildschirmdiagonale und Export-PPI
  gesetzt.
- **Variablen**: `lineWeightInMillimeters` und `textSizeInMillimeters` –
  Grössen in mm, die mit `mmpx()` in Pixel umgerechnet werden.
- **`setup()`**: `createCanvas(mmpx(200), mmpx(100), { seed: 1234 })`
  setzt die Grösse der Zeichenfläche in mm; die Option `seed` (von p5.5)
  macht die Zufallswerte wiederholbar. Danach wird der Hilfetext auf die
  Zeichenfläche geschrieben.
- **`draw()`**: zeichnet pro Frame eine Linie mit zufälliger Position und
  Farbe und der Strichstärke `mmpx(lineWeightInMillimeters)`.
- **`index.html`**: lädt p5.js, p5.5.js und `sketch.js` mit `defer`.
