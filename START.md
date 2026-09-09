# maquette — Start in drei Schritten

maquette macht aus einer Idee ein klickbares Modell: etwas, das man in der Hand hat, bevor man entscheidet, ob man es wirklich baut. Sie brauchen dafür keine Technikkenntnisse — Sie beantworten Fragen, die KI erledigt den Rest und legt alles als lesbare Textdateien in diesem Ordner ab.

**Dieser Ordner enthält nur Textdateien. Keine Programme, keine Installation, kein Internetzugriff.**

## 1. Ordner ablegen

Entpacken Sie die ZIP-Datei und legen Sie den Ordner `maquette` dorthin, wo Sie ihn wiederfinden — zum Beispiel in Ihre Dokumente. Nicht umbenennen, nichts darin löschen.

## 2. Ordner in der KI-App öffnen

- **ChatGPT-App (Codex):** Codex-Modus wählen → „Projekt öffnen" → diesen Ordner auswählen.
- **Claude (Cowork):** Neue Aufgabe → Ordner verbinden → diesen Ordner auswählen.
- **Claude Code / Codex im Terminal:** in den Ordner wechseln und das Programm starten.

Die App liest beim Öffnen automatisch die Spielregeln aus diesem Ordner.

## 3. „start" tippen

Schreiben Sie **start** — oder einfach Ihre Idee in zwei Sätzen. Ab dann führt die KI Sie durch sechs Stationen und fragt jeweils nach: **weiter**, **nochmal** oder **stopp**. Mehr Befehle gibt es nicht.

| Station | Wer | Was Sie bekommen | etwa |
| --- | --- | --- | --- |
| 1 | Sparringspartner | Ihre Idee geschärft, mit klarem Ziel für das Modell | 15 min |
| 2 | Review-Board | Ein Plan in drei bis fünf Scheiben | 20 min |
| 3 | Designer | Drei Entwürfe nebeneinander im Browser, Sie wählen | 15 min |
| 4 | Bauteam | Das klickbare Modell, Scheibe für Scheibe | 60 min |
| 5 | Qualitätsprüfer | Geprüft und repariert, mit ehrlichem Urteil | 20 min |
| 6 | Demo-Brief | Drei-Minuten-Skript für die Vorführung und der nächste Schritt | 10 min |

Sie können jederzeit stoppen. Was bis dahin entstanden ist, bleibt im Ordner `maquettes/` und lässt sich beim nächsten Mal mit **weiter** fortsetzen.

## Wo liegt was?

Jedes Modell bekommt einen eigenen Unterordner in `maquettes/`, zum Beispiel `maquettes/WST-weltstahl-dashboard/`. Darin liegen nummerierte Textdateien — `10-seed.md`, `20-plan.md` … `60-brief.md` — und das Modell selbst im Unterordner `vcode/`. Alles ist mit jedem Texteditor lesbar. Am Ende jeder Datei gibt es einen Abschnitt **Notizen (Mensch)**: Dort können Sie eigene Anmerkungen hinterlassen, die KI lässt ihn unangetastet.

## Wenn etwas nicht klappt

- Die KI reagiert nicht auf „start"? Schreiben Sie: „Lies AGENTS.md und beginne."
- Sie wollen ein zweites Modell? Schreiben Sie: „Neue Maquette." Das erste bleibt erhalten.
- Neue Version von maquette? Neuen Ordner herunterladen, Ihren Unterordner `maquettes/` hinüberkopieren, fertig.

Version: siehe Datei `VERSION`. Fragen und Rückmeldungen: dietmar@millinger.at
