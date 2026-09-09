---
stage: harden
owner: harden
status: in_arbeit            # offen | in_arbeit | fertig | uebersprungen
revision: 1
created: <JJJJ-MM-TTThh:mm>
updated: <JJJJ-MM-TTThh:mm>
input: 40-build.md@<rev>
git: <ja | nein>
budget_fixes: <10 mit Git | 5 ohne Git>
---

# Härtung <Kürzel>: <Arbeitstitel>

_Ergebnis der Stufe harden. Review gegen die Maquette-Checkliste (nicht diff-basiert), dann Fixes innerhalb eines Budgets. Ideen aus gstack review und qa (© 2026 Garry Tan, MIT License, siehe `LICENSES/gstack-MIT.txt`): Konfidenz-Kalibrierung, ein Fix je Commit, Stopp bei Regression._

## 1. Prüfweg

- **Methode:** <Browser-QA (Host: <…>) | Code-Walkthrough (kein Browser verfügbar)>
- **Gestartet mit:** <Befehle aus 40-build.md „Starten">
- **Geprüfte Slices:** <S1…Sn>

## 2. Befunde

<!-- Checkliste: Happy Path je Slice · leere Zustände · Fehleingaben · Textqualität (Rechtschreibung, Fachbegriffe aus §2 des Plans) · keine Platzhalter/Lorem ipsum · Startanleitung funktioniert · Leitplanken aus 10-seed.md §5 eingehalten.
     Konfidenz: hoch = reproduziert; mittel = beobachtet, Ursache vermutet. Befunde mit niedriger Konfidenz kommen NICHT hierher, sondern in §5. -->

| Nr. | Slice | Befund | Schwere | Konfidenz | Entscheidung |
| --- | --- | --- | --- | --- | --- |
| B1 | S1 | <…> | <hoch | mittel | niedrig> | <hoch | mittel> | <fixen | lassen: <Grund>> |

## 3. Fixes

<!-- Ein Eintrag je Fix, in Reihenfolge. Mit Git: Commit je Fix, Revert bei Regression, Budget 10, STOPP beim ersten Revert und bei jedem Fix mit > 3 Dateien. Ohne Git: ein Fix → prüfen → nächster, kein Revert, Budget 5. -->

| Fix | Befund | Dateien | Ergebnis | Commit / Prüfvermerk |
| --- | --- | --- | --- | --- |
| F1 | B1 | <n> | <behoben | Regression → Revert | abgebrochen> | <Hash | „geprüft hh:mm"> |

**Budget-Stand:** <verbraucht / Budget> · **Stopp-Grund:** <keiner | Budget | Revert | > 3 Dateien | Nutzer>

## 4. Endurteil

- **Demofähig:** <ja | mit Einschränkung | nein>
- **Einschränkungen:** <was der Vorführende wissen und umgehen muss>
- **Ausgangslage vs. Endstand:** <besser | gleich | schlechter — bei „schlechter" deutlich hervorheben>

## 5. Anhang: unsicher, nicht gefixt

<!-- Befunde mit niedriger Konfidenz oder außerhalb des Budgets. Nichts geht verloren; brief nimmt sie in die Kann-nicht-Liste oder die offenen Fragen. -->

- <…>

## Offene Fragen

- **Q<n>** — <…>

## Notizen (Mensch)

<!-- Tabu für alle Skills. Wird bei jeder Neuschreibung unverändert übernommen. -->
