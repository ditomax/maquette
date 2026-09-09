---
stage: design
owner: design-3
status: in_arbeit            # offen | in_arbeit | fertig | uebersprungen
revision: 1
created: <JJJJ-MM-TTThh:mm>
updated: <JJJJ-MM-TTThh:mm>
input: 20-plan.md@<rev>
---

# Design <Kürzel>: <Arbeitstitel>

_Ergebnis der Stufe design-3. Drei bewusst verschiedene Varianten als eigenständige HTML-Dateien (`30-design-a.html`, `-b.html`, `-c.html`), Vergleich in `30-vergleich.html`. Idee aus gstack design-shotgun (© 2026 Garry Tan, MIT License, siehe `LICENSES/gstack-MIT.txt`), ohne Server, Screenshots und Geschmacksprofil._

## 1. Kontext

<!-- Fünf Fragen, eine nach der anderen. Antworten in den Worten des Nutzers. Aus 20-plan.md vorfüllen, wo möglich, und bestätigen lassen. -->

- **Wer benutzt es:** <Rolle, Situation, Gerät>
- **Job-to-be-done:** <der eine Satz, warum jemand die Seite öffnet>
- **Bestehendes:** <Corporate Design, Vorbild-Tools, Verbote — oder „frei">
- **User-Flow von S1:** <Schritt → Schritt → Ergebnis>
- **Edge-Cases:** <leer, viel, Fehler, langsam>

## 2. Varianten

<!-- Anti-Konvergenz-Gebot: Die drei Varianten MÜSSEN sich in Schrift, Farbwelt und Layout unterscheiden. Eine Zeile Begründung, warum diese Variante zu §1 passt. -->

| Variante | Charakter | Schrift | Farbwelt | Layout | Passt, weil |
| --- | --- | --- | --- | --- | --- |
| A | <z. B. „nüchtern, Tabelle zuerst"> | <…> | <…> | <…> | <…> |
| B | <z. B. „visuell, Karte zuerst"> | <…> | <…> | <…> | <…> |
| C | <z. B. „geführt, ein Schritt je Bildschirm"> | <…> | <…> | <…> | <…> |

**Alle drei zeigen denselben Inhalt:** Slice S1 mit realistischen Beispieldaten, keine Lorem-ipsum-Texte.

## 3. Entscheidung

- **Gewählt:** <A | B | C | Mischung: <…>> — **weil:** <Begründung des Nutzers, in seinen Worten>
- **Übernehmen aus den anderen:** <konkrete Elemente, oder „nichts">
- **Verworfen:** <die anderen zwei, je ein Satz>

## 4. Design-Tokens für den Build

<!-- Das, was build aus der gewählten HTML-Datei übernimmt. Kurz, maschinenlesbar. -->

```yaml
schrift: <Familie, Fallback>
farben: {hintergrund: "#…", text: "#…", akzent: "#…", warnung: "#…"}
layout: <Raster/Spalten in einem Satz>
abstaende: <Basiseinheit>
startdatei: 30-design-<x>.html
```

## Notizen (Mensch)

<!-- Tabu für alle Skills. Wird bei jeder Neuschreibung unverändert übernommen. -->
