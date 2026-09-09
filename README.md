# maquette

**Von der Idee zum klickbaren Modell — sieben Markdown-Skills, ein Befehl.**

Version 0.1 · September 2026 · DMBG

## Was ist eine Maquette?

Eine Maquette (französisch, „makett") ist das Modell, das Architekten bauen, bevor sie bauen: klein, greifbar, aus Karton — nicht das Gebäude, aber genau genug, um darum herumzugehen, Proportionen zu prüfen und mit dem Bauherrn zu entscheiden, ob und wie es weitergeht. Hier ist die Maquette der klickbare Prototyp einer Software-Idee: kein Produkt, sondern ein Modell, an dem man die Idee begreift und über den echten Bau entscheidet. Sie ist wertvoll, weil sie billig und vorläufig ist.

## Wie es funktioniert

Der Nutzer tippt `/maquette` und danach nur noch **weiter**, **nochmal** oder **stopp**. Ein Regie-Skill liest den Maquette-Ordner, sagt, wo man steht, und ruft die nächste von sechs Stufen auf:

| Stufe | „Teammitglied" | Ergebnis | Minuten (Workshop) |
| --- | --- | --- | --- |
| 1 sparring | Sparringspartner | `10-seed.md` — Idee geschärft, Scope, drei Richtungen, eine gewählt | 15 |
| 2 plan-board | Review-Board | `20-plan.md` — Anforderungen geprüft, Slices, Freigabe | 20 |
| 3 design-3 | Designer | `30-design.md` + drei HTML-Varianten + Vergleichsseite | 15 |
| 4 build | Bauteam | `40-build.md` + `vcode/` — Scheibe für Scheibe | 60 |
| 5 harden | Qualitätsprüfer | `50-harden.md` — Befunde, Fixes im Budget, Demofähigkeit | 20 |
| 6 brief | Chronist | `60-brief.md` — Demo-Skript, Kann/Kann-nicht, Retrofit-Seed | 10 |

Jede Stufe liest genau eine Eingangsdatei und schreibt genau eine Ergebnisdatei. Alle Ergebnisse liegen in **einem Ordner pro Maquette**, tragen Frontmatter und unterliegen Schreibregeln, die verhindern, dass sich Agents gegenseitig überschreiben (siehe `RULES.md`). Der Ordner ist der Zustand — es gibt nichts außerhalb.

Davor kann unsere Mittelstand-Kette liegen (ki-ideenfindung → Ideenkarte, konzeptskizze → Konzeptskizze; beides wird in Stufe 1 vorgefüllt). Danach kommt das Concept Authoring Manifest: `60-brief.md` enthält den Retrofit-Seed für Phase 1 (Path B).

## Struktur

```
maquette/
  START.md             drei Schritte für den Menschen (Deutsch)
  AGENTS.md            Einstieg für Codex — macht den Agenten zur Regie
  CLAUDE.md            dasselbe für Claude
  VERSION
  README.md            diese Datei
  RULES.md             gemeinsame Regeln aller Stufen — Frontmatter, Schreibregeln, Gesprächsregeln
  ATTRIBUTION.md       übernommene Ideen und ihre Herkunft
  maquettes/           Arbeit der Nutzer, ein Unterordner je Maquette (nicht im Repo)
  templates/           eine Vorlage je Ergebnisdatei (verbindliche Inhaltsdefinition)
  skills/
    maquette/          Regie
    maquette-sparring/
    maquette-plan-board/
    maquette-design-3/
    maquette-build/
    maquette-harden/
    maquette-brief/
```

## Verteilung und Installation

Dieser Ordner ist der **Workspace** — Repo und ZIP haben dieselbe Struktur. Nutzer laden die ZIP eines Releases herunter, entpacken sie, öffnen den Ordner in ihrer KI-App und tippen „start" (Anleitung in `START.md`). `AGENTS.md` (Codex) und `CLAUDE.md` (Claude) werden beim Öffnen automatisch gelesen und machen den Agenten zur Regie — es gibt nichts zu installieren, keine Symlinks, keine globalen Skill-Ordner.

Für Entwickler, die die Skills global haben wollen, geht zusätzlich:

```
ln -s "$PWD/skills/"maquette* ~/.codex/skills/      # oder ~/.claude/skills/
```

**ChatGPT / Mistral** (kein Ordnerzugriff): Regie entfällt. Den Textkörper eines Stufen-Skills (ohne Frontmatter) als System-Prompt einsetzen, `RULES.md` und die passende Vorlage anhängen; `00-maquette.md` pflegt der Mensch von Hand.

Keine Abhängigkeiten, kein Setup-Skript, kein Netzwerkzugriff, keine Telemetrie. `maquettes/` ist per `.gitignore` vom Repo ausgeschlossen — die Arbeit der Nutzer landet nie im öffentlichen Repository.

## Release

Neue Version: `VERSION` anheben, Tag `vX.Y.Z` setzen, GitHub-Release mit angehängter ZIP des Ordners (`maquette-vX.Y.Z.zip`). Nutzer aktualisieren, indem sie den neuen Ordner herunterladen und ihr `maquettes/` hinüberkopieren. Git ist optional: Ist ein Repository vorhanden, wird je Scheibe und je Fix committet; sonst nicht. Die Skills legen nie selbst ein Repository an.

## Modi

- **workshop** (Default): ein halber Tag, Ziel ist eine Demo. Forcing Questions Q1–Q4, Grilling 10 Minuten, Slices S1–S3, Fix-Budget 10 (mit Git) / 5 (ohne).
- **discovery**: zwei bis drei Tage, Ziel ist ein belastbarer Prototyp plus vollständiger Retrofit-Seed. Q1–Q6, Grilling 30 Minuten, alle Slices, doppeltes Fix-Budget.

## Herkunft

Die Stufen kombinieren unsere eigenen Skills (idea-work, ki-ideenfindung, konzeptskizze, Concept Authoring Manifest, CLAUDE.local.md) mit Ideen aus gstack (Garry Tan, MIT): Forcing Questions und Premise Challenge, Review-Board mit Rollen, drei divergente Design-Varianten, Konfidenz-kalibriertes Review, ein Commit je Fix mit Revert bei Regression. Übernommen wurde Methode, kein Code.

## Lizenz

gstack ist © 2026 Garry Tan und steht unter der MIT-Lizenz; der vollständige Lizenztext liegt in `LICENSES/gstack-MIT.txt` und in `ATTRIBUTION.md`, das auch genau auflistet, welche Methode in welche Stufe übernommen wurde. Die Lizenz von maquette selbst steht in `LICENSE`.
