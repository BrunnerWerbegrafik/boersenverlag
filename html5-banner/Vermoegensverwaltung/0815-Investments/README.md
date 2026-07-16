# TM Börsenverlag AG – Vermögensverwaltung – 08/15-Investments
## Fireplace left Sloganbanner (300 × 600 px)

HTML5-Banner mit Tipp-Animation: Die beiden Textblöcke im oberen Bereich werden
Zeichen für Zeichen „getippt“, begleitet von einem blinkenden Block-Cursor in
Textfarbe (wie in alten Texteingabeprogrammen).

## Dateien

| Datei            | Zweck                                                        |
|------------------|--------------------------------------------------------------|
| `index.html`     | Banner inkl. Animation (CSS/JS inline, keine Abhängigkeiten) |
| `background.png` | Hintergrund ohne Text                                        |
| `fallback.png`   | Statisches Fallback-Motiv mit Text                           |

## Getippter Text

1. Absatz: „Keine Lust mehr auf 08/15-Investments?“
2. Absatz: „Vermögensverwaltung geht auch transparent, regelbasiert und innovativ!“

Die Zeilenumbrüche sind fest hinterlegt und entsprechen exakt dem
Original-Layout. Nutzer mit aktivierter Systemeinstellung „Bewegung
reduzieren“ sehen sofort den fertigen Text.

## Ablauf der Animation

1. Cursor blinkt kurz an der Startposition.
2. Absatz 1 wird mit leicht variierendem Tempo getippt.
3. Kurze Pause, dann wird Absatz 2 getippt.
4. Der Cursor blinkt noch einige Sekunden und verschwindet dann –
   der Endframe zeigt den vollständigen Text (Ad-Spec-konform, Animation endet).

## Anpassen

Alle Stellschrauben liegen im `CONFIG`-Objekt am Anfang des Scripts in
`index.html`:

- `typeSpeed` / `typeJitter` – Tippgeschwindigkeit
- `startDelay`, `paragraphPause`, `endBlinkTime` – Pausen
- `loops` – Anzahl kompletter Durchläufe (Standard: 1)

## clickTag

Der Banner unterstützt den Standard-`clickTag` (Google Ads / Campaign
Manager). Der Adserver befüllt die Variable automatisch; für einen festen
Link einfach in `index.html` eintragen:

```js
var clickTag = "https://…";
```

## Auslieferung

Für den Adserver den Ordnerinhalt (`index.html`, `background.png`) als
ZIP verpacken; `fallback.png` dient als statisches Ersatzmotiv.
