# TM Börsenverlag AG – Vermögensaufbau / Immobilien-Ersatz
## Fireplace right Banner mit Motivwechsel (300 × 600 px)

HTML5-Banner mit zwei rotierenden Motiven. Jedes Motiv baut sich elegant aus
seinen Einzelebenen auf, bleibt gut lesbar stehen und blendet dann weich zum
nächsten Motiv über.

## Ablauf

1. Motiv „Vermögensaufbau“ (Ärztin, 49): Foto steht sofort, die Headline
   gleitet von oben ein, das Tortendiagramm poppt mit leichtem Überschwung
   auf, der „Infos“-Button schiebt sich von unten ins Bild.
2. Nach ca. 3,5 Sekunden weicher Crossfade zum Motiv „Immobilien-Ersatz“
   (Ehepaar, 66), das sich auf dieselbe Weise aufbaut.
3. Die Motive wechseln insgesamt viermal ab (jedes Motiv zweimal), danach
   endet die Animation auf dem vollständigen zweiten Motiv (Ad-Spec-konform).

Der Hinweis „Marketing-Anzeige“ bleibt dauerhaft eingeblendet.

## Dateien

| Datei                          | Zweck                                        |
|--------------------------------|----------------------------------------------|
| `index.html`                   | Banner inkl. Animation (CSS/JS inline)       |
| `bild-vermoegensaufbau.jpg`    | Motiv 1: Hintergrund + Foto                  |
| `diagram-vermoegensaufbau.png` | Motiv 1: Tortendiagramm (transparent)        |
| `text-vermoegensaufbau.png`    | Motiv 1: Headline + Subline (transparent)    |
| `bild-immobilien-ersatz.jpg`   | Motiv 2: Hintergrund + Foto                  |
| `diagram-immobilien-ersatz.png`| Motiv 2: Tortendiagramm (transparent)        |
| `text-immobilien-ersatz.png`   | Motiv 2: Headline + Subline (transparent)    |
| `cta.png`                      | „Infos“-Button (in beiden Motiven identisch) |
| `notice.png`                   | „Marketing-Anzeige“-Hinweis (dauerhaft)      |
| `fallback.jpg`                 | Statisches Fallback-Motiv (Motiv 1 komplett) |

Die Textebenen wurden pixelgenau aus den gelieferten Composings extrahiert –
der jeweils vollständig aufgebaute Zustand ist deckungsgleich mit den
Original-Vorlagen („alles“-Dateien).

## Anpassen

Alle Stellschrauben liegen im `CONFIG`-Objekt am Anfang des Scripts in
`index.html`:

- `motifTime` – Anzeigedauer je Motiv in ms (Standard: 3500)
- `crossfade` – Überblenddauer in ms (Standard: 600)
- `showings` – Anzahl der Motiv-Einblendungen gesamt (Standard: 4;
  höher = längere Rotation, das letzte Motiv bleibt stehen)

## clickTag

Der Banner unterstützt den Standard-`clickTag` (Google Ads / Campaign
Manager). Der Adserver befüllt die Variable automatisch; für einen festen
Link einfach in `index.html` eintragen:

```js
var clickTag = "https://…";
```

## Auslieferung

Für den Adserver den Ordnerinhalt (alle Dateien außer `fallback.jpg` und
dieser README) als ZIP verpacken; `fallback.jpg` dient als statisches
Ersatzmotiv. Gesamtgewicht ca. 400 KB.
