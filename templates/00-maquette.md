---
stage: control
owner: maquette
status: in_arbeit            # offen | in_arbeit | fertig | uebersprungen
revision: 1
created: <JJJJ-MM-TTThh:mm>
updated: <JJJJ-MM-TTThh:mm>
input: —
# --- nur in 00-maquette.md ---
titel: <Arbeitstitel der Maquette>
kuerzel: <2–4 Buchstaben, z. B. WST>
modus: workshop              # workshop | discovery
git: nein                    # ja | nein — von der Regie beim Start geprüft
sprache: de                  # Sprache der Ergebnisdateien
budget_min: {sparring: 15, plan: 20, design: 15, build: 60, harden: 20, brief: 10}
---

# Maquette <Kürzel>: <Arbeitstitel>

<!-- Diese Datei gehört der Regie. Kein anderer Skill schreibt hier. -->

## Ausgangspunkt

- **Eingang:** <Idee in zwei Sätzen | Ideenkarte <ID> | Konzeptskizze <ID>-K>
- **Auftraggeber / Sponsor:** <Rolle, falls bekannt>
- **Ziel der Maquette:** <ein Satz: was soll nach der Demo entschieden werden können?>

## Stufen

| Stufe | Skill | Datei | Status | Gültige Revision | Begonnen | Beendet | Minuten |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | sparring | 10-seed.md | offen | — | | | |
| 2 | plan-board | 20-plan.md | offen | — | | | |
| 3 | design-3 | 30-design.md | offen | — | | | |
| 4 | build | 40-build.md | offen | — | | | |
| 5 | harden | 50-harden.md | offen | — | | | |
| 6 | brief | 60-brief.md | offen | — | | | |

<!-- Status-Werte: offen | in_arbeit | fertig | uebersprungen | veraltet (Eingang hat sich geändert, siehe Schreibregel 6).
     „Gültige Revision" nennt die Datei, die die Folgestufe lesen soll, z. B. 20-plan.v2.md. -->

## Entscheidungslog

| Zeit | Stufe | Entscheidung | Bemerkung |
| --- | --- | --- | --- |
| <hh:mm> | — | start | Modus <workshop>, Git <nein> |

<!-- Erlaubte Entscheidungen: start · weiter · nochmal · stopp · ueberspringen · budget_ueberzogen (mit Nutzerantwort) -->

## Offene Punkte für die Regie

<!-- Dinge, die die Regie beim nächsten Aufruf ansprechen muss: überzogenes Budget, Konfliktdateien, veraltete Folgedateien, ausstehende Nutzerentscheidungen. Leer = nichts offen. -->

- —

## Notizen (Mensch)

<!-- Tabu für alle Skills. Hier korrigiert, ergänzt und kommentiert der Mensch. Wird bei jeder Neuschreibung unverändert übernommen. -->
