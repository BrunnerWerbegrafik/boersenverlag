# TM Börsenverlag AG – Technologiefonds
## Fireplace top Logo-Banner (1000 × 150 px)

HTML5-Banner mit Endlos-Animation: Ein Streifen mit Technologie-Logos rollt
langsam wie auf einem Drehrad von oben nach unten durch den Banner. Der Loop
ist nahtlos – nach einem kompletten Durchlauf beginnt er unsichtbar wieder von
vorn und läuft endlos weiter.

## Dateien

| Datei            | Zweck                                                          |
|------------------|----------------------------------------------------------------|
| `index.html`     | Banner inkl. Animation (CSS/JS inline, keine Abhängigkeiten)   |
| `background.png` | Hintergrund (heller Verlauf)                                   |
| `logos.png`      | Nahtlos kachelbarer Logo-Streifen (980 × 1178 px, 19 Reihen)   |
| `gradient.png`   | Weißer Verlauf über den Logos (macht Ober-/Unterkante weicher) |
| `fallback.png`   | Statisches Fallback-Motiv (Original-Banner)                    |

## Funktionsweise

- `logos.png` wurde aus der gelieferten Logo-Datei so zugeschnitten, dass er
  sich vertikal nahtlos wiederholt (exakt 19 Logo-Reihen im 62-px-Raster,
  auch über die Nahtstelle hinweg). Er läuft per `repeat-y` als Kachel.
- Die CSS-Animation verschiebt den Streifen linear um genau eine Kachelhöhe
  (1178 px) nach unten und springt dann auf 0 zurück – da Start- und Endframe
  pixelidentisch sind, ist der Sprung unsichtbar.
- Darüber liegt `gradient.png`, damit die Logos an Ober- und Unterkante
  weich ein- und auslaufen.
- Nutzer mit aktivierter Systemeinstellung „Bewegung reduzieren“ sehen das
  statische Motiv (entspricht dem Original-Banner).

## Anpassen

Im `CONFIG`-Objekt in `index.html`:

- `scrollSpeed` – Geschwindigkeit in Pixel pro Sekunde (Standard: 18).
  Ein kompletter Durchlauf dauert damit ca. 65 Sekunden; eine neue
  Logo-Reihe erscheint etwa alle 3,5 Sekunden.

## clickTag

Der Banner unterstützt den Standard-`clickTag` (Google Ads / Campaign
Manager). Der Adserver befüllt die Variable automatisch; für einen festen
Link einfach in `index.html` eintragen:

```js
var clickTag = "https://…";
```

## Hinweise zur Auslieferung

- Für den Adserver den Ordnerinhalt (`index.html`, `background.png`,
  `logos.png`, `gradient.png`) als ZIP verpacken; `fallback.png` dient als
  statisches Ersatzmotiv.
- Gesamtgewicht ca. 660 KB (davon `logos.png` ca. 520 KB). Falls der
  Vermarkter ein strengeres Limit vorgibt, kann `logos.png` weiter
  komprimiert werden.
- Die Animation läuft bewusst endlos. Manche Vermarkter schreiben ein
  Animationsende nach 30 Sekunden vor – das bitte ggf. mit dem Vermarkter
  klären.
