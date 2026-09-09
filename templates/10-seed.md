---
stage: seed
owner: sparring
status: in_arbeit            # offen | in_arbeit | fertig | uebersprungen
revision: 1
created: <JJJJ-MM-TTThh:mm>
updated: <JJJJ-MM-TTThh:mm>
input: 00-maquette.md@1      # Ausgangspunkt; bei Ideenkarte/Konzeptskizze zusätzlich deren ID im Abschnitt „Eingang"
---

# Seed <Kürzel>: <Arbeitstitel>

_Concept Seed light — Ergebnis der Stufe sparring. Kandidaten-Anforderungen (`cF-` / `cU-` / `cNF-`) sind **unratifiziert**: Sie dienen der Maquette als Leitplanke und dem späteren Retrofit (Manifest Phase 1) als Ausgangsmaterial, nicht als Spezifikation._

## Eingang

- **Quelle:** <Idee in zwei Sätzen | Ideenkarte <ID> | Konzeptskizze <ID>-K>
- **Vorgefüllt aus der Quelle:** <welche Felder übernommen und vom Nutzer bestätigt wurden, oder „nichts — Cold Start">

## Feld der Anwendung

<eine Zeile: z. B. „Web-App, intern" / „Dashboard auf öffentlichen Daten" / „Dokumenten-Assistent">
<!-- Vom Nutzer bestätigt. Legt die Standardanliegen fest, die als offene Fragen auftauchen müssen (Web → Datenschutz, Zugriff, Deployment). -->

## 1. Zweck

<Das gerahmte Problem und das eigentliche Ziel dahinter (Laddering: „warum ist das wichtig?"). Woran erkennt man Erfolg?>

## 2. Forcing Questions

<!-- Aus gstack office-hours (© 2026 Garry Tan, MIT License, siehe `LICENSES/gstack-MIT.txt`), eingeordnet nach Konzept §5. Jede Antwort mit Evidenzmarke [belegt|geschätzt|unbekannt].
     Q2 und Q3 werden bei vorhandener Ideenkarte vorgefüllt und nur bestätigt. Q5 und Q6 sind hier bewusst NICHT enthalten (Q5 → 60-brief, Q6 → nur Discovery-Modus). -->

- **Q1 Nachfrage-Realität** — Wer wäre spürbar betroffen, wenn es diese Lösung morgen nicht gäbe, und woran sieht man das? <…> [belegt|geschätzt|unbekannt]
- **Q2 Status quo** — Was tun die Betroffenen heute stattdessen, und was kostet dieser Umweg (Häufigkeit × Aufwand)? <…> [belegt|geschätzt|unbekannt]
- **Q3 Der konkrete Mensch** — Wer genau braucht das am dringendsten: Rolle, Situation, Konsequenz, wenn es nicht gelöst wird? <…> [belegt|geschätzt|unbekannt]
- **Q4 Kleinste Demo** — Was ist die kleinste Version, mit der der Sponsor grünes Licht gibt? <…> [belegt|geschätzt|unbekannt]
  → **Scope der Maquette:** <ein Satz; wird Slice S1 in 20-plan.md>

## 3. Prämissen-Check

<!-- Premise Challenge: Was müsste wahr sein, damit das Problem überhaupt existiert und diese Lösungsrichtung trägt? Eine Zeile je Prämisse, mit Einschätzung. -->

| Prämisse | Wahr, wenn … | Einschätzung |
| --- | --- | --- |
| <…> | <…> | <belegt | plausibel | offen> |

## 4. Gemeinsame Sprache

<!-- Begriffe, die im Gespräch entstanden sind, in den Worten des Nutzers. Wird zu CONTEXT.md im Retrofit. -->

| Begriff | Bedeutung |
| --- | --- |
| <…> | <…> |

## 5. Leitplanken

<!-- Nicht verhandelbare Grenzen für die Maquette: Must-nots, Datenschutz-/Sicherheitsflags aus dem Feld der Anwendung, Dinge, die der Prototyp bewusst nicht zeigen darf. -->

- **LP-1** — <…>

## 6. Gewählte Richtung und Alternativen

<!-- Harter Stopp in sparring: Der Nutzer hat drei Richtungen gesehen, bevor er eine gewählt hat. Verworfene Alternativen bleiben mit Grund erhalten (ADR-Seeds). -->

- **Gewählt:** <Richtung in zwei Sätzen> — **weil:** <…>
- **Verworfen A:** <…> — **weil:** <…>
- **Verworfen B:** <…> — **weil:** <…>

## 7. Kandidaten-Anforderungen (unratifiziert)

<!-- 5–8 Stück gesamt. Nur was die Maquette zeigen soll. Testbar formuliert, wo möglich. -->

### Funktional
| ID | Anforderung |
| --- | --- |
| cF-1 | <…> |

### Nutzerinteraktion
| ID | Anforderung |
| --- | --- |
| cU-1 | <…> |

### Nicht-funktional
| ID | Anforderung |
| --- | --- |
| cNF-1 | <…> |

## 8. Offene Fragen

<!-- Alles Ungeklärte, inkl. der Standardanliegen des Anwendungsfelds. Nummerierung Q1… läuft in 40/50/60 weiter, wird nie neu begonnen. -->

- **Q1** — <…>

## 9. Riskanteste Annahme

- **Annahme:** <ein Satz — aus Mini-Pre-Mortem: „die Maquette ist gezeigt worden und hat nicht überzeugt — woran lag es?">
- **Wenn falsch:** <Konsequenz>
- **Billigster Test:** <der kleinste Versuch, der sie bestätigt oder kippt; wird in 60-brief.md wieder aufgegriffen>

## Notizen (Mensch)

<!-- Tabu für alle Skills. Wird bei jeder Neuschreibung unverändert übernommen. -->
