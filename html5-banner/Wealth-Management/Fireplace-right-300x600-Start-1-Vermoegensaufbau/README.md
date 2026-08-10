# TM Börsenverlag AG – Wealth Management
## Fireplace right Banner mit 5-Motiv-Rotation (300 × 600 px)
### Variante 1: Start mit „Vermögensaufbau“

HTML5-Banner mit fünf rotierenden Motiven in Endlosschleife. Jedes Motiv
schiebt sich auffällig von rechts ins Bild (Push-Effekt), baut seine
Elemente kraftvoll auf und macht nach ca. 3,6 Sekunden Platz für das
nächste Motiv.

## Ablauf

Reihenfolge der Endlosschleife:

1. Vermögensaufbau (Ärztin, 49, Praxis läuft.)
2. Immobilien-Ersatz (Ehepaar, 66, Haus verkauft)
3. Substanz (Großeltern, 74, drei Enkel)
4. Schwerpunkt Gold (Unternehmer, 81, nach dem Exit)
5. … und Sie? (Ihr Ziel. Ihr Portfolio!)

Nach Motiv 5 beginnt die Schleife wieder bei Motiv 1 – ohne Ende.

Je Motiv: Das neue Motiv schiebt sich von rechts herein, während das alte
nach links hinausgleitet. Danach gleitet die Headline von oben ein, das
Tortendiagramm poppt mit Drehung und deutlichem Überschwung auf, der
„Infos“-Button springt mit Bounce-Effekt von unten ins Bild. Der Hinweis
„Marketing-Anzeige“ bleibt dauerhaft eingeblendet.

## Dateien

| Datei                 | Zweck                                             |
|-----------------------|---------------------------------------------------|
| `index.html`          | Banner inkl. Animation (CSS/JS inline)            |
| `bild-<motiv>.jpg`    | Je Motiv: Hintergrund + Foto (5 Dateien)          |
| `diagram-<motiv>.png` | Je Motiv: Tortendiagramm, transparent (5 Dateien) |
| `text-<motiv>.png`    | Je Motiv: Headline + Subline, transparent (5)     |
| `cta.png`             | „Infos“-Button (in allen Motiven identisch)       |
| `notice.png`          | „Marketing-Anzeige“-Hinweis (dauerhaft)           |
| `fallback.jpg`        | Statisches Fallback-Motiv (Motiv 1 komplett)      |

Die Textebenen wurden pixelgenau aus den gelieferten Composings
extrahiert – jeder vollständig aufgebaute Zustand ist deckungsgleich mit
der jeweiligen Original-Vorlage („alles“-Datei).

## Anpassen

Alle Stellschrauben liegen im `CONFIG`-Objekt am Anfang des Scripts in
`index.html`:

- `motifTime` – Anzeigedauer je Motiv in ms (Standard: 3600)
- `slide` – Dauer des Schiebe-Übergangs in ms (Standard: 600)
- `startIndex` – Startmotiv der Rotation (0–4). Für die geplanten
  weiteren Banner-Varianten muss nur dieser Wert geändert werden:
  0 = Vermögensaufbau, 1 = Immobilien-Ersatz, 2 = Substanz,
  3 = Schwerpunkt Gold, 4 = … und Sie?

## clickTag

Der Banner unterstützt den Standard-`clickTag` (Google Ads / Campaign
Manager). Der Adserver befüllt die Variable automatisch; für einen festen
Link einfach in `index.html` eintragen:

```js
var clickTag = "https://…";
```

## Hinweise zur Auslieferung

- Für den Adserver den Ordnerinhalt (alle Dateien außer `fallback.jpg`
  und dieser README) als ZIP verpacken; `fallback.jpg` dient als
  statisches Ersatzmotiv.
- Gesamtgewicht ca. 1,2 MB (fünf Foto-Motive). Falls der Vermarkter ein
  strengeres Limit vorgibt, können die JPGs stärker komprimiert werden.
- Die Rotation läuft bewusst endlos. Manche Vermarkter schreiben ein
  Animationsende nach 30 Sekunden vor – das bitte ggf. mit dem
  Vermarkter klären.
