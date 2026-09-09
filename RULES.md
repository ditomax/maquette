# maquette — Shared Rules for All Stage Skills

**Version 1.** Every stage skill reads this file before doing anything. The Regie (`maquette`) enforces it. If a stage skill and this file disagree, this file wins.

## 1. Vocabulary

- **Maquette** — a folder containing one clickable model and its documents. Named after the scale model architects build before building.
- **Stage** — one of: sparring → plan-board → design-3 → build → harden → brief. Each stage has exactly one owner skill, one input, one result file.
- **Result file** — `NN-<stage>.md` in the maquette folder, filled from the matching template in `templates/`.
- **Regie** — the `maquette` skill. Reads the folder, tells the user where they are, calls the stage skill, updates `00-maquette.md`.
- **Human notes** — the section `## Notizen (Mensch)` at the end of every result file.

## 2. Folder is the state

There is no state outside the maquette folder — no `~/.something`, no environment variables, no memory across maquettes. A skill learns everything it needs by reading `00-maquette.md` and its input file. A skill that needs something else asks the user.

```
<maquette folder>/
  00-maquette.md      Regie          control
  10-seed.md          sparring       seed
  20-plan.md          plan-board     plan
  30-design.md        design-3       design   (+ 30-design-a/b/c.html, 30-vergleich.html)
  40-build.md         build          build    (+ vcode/)
  50-harden.md        harden         harden
  60-brief.md         brief          brief
```

## 3. Frontmatter

Every result file starts with:

```yaml
---
stage: <control|seed|plan|design|build|harden|brief>
owner: <skill name>
status: <offen|in_arbeit|fertig|uebersprungen>
revision: <integer, starts at 1>
created: <ISO timestamp, minutes>
updated: <ISO timestamp, minutes>
input: <file>@<revision>[, <file>@<revision>]
---
```

`00-maquette.md` additionally carries `titel`, `kuerzel`, `modus`, `git`, `sprache`, `budget_min`. Stage skills read those; only the Regie writes them. A template may add stage-specific fields (`40-build.md`: `git`; `50-harden.md`: `git`, `budget_fixes`) — copied from `00-maquette.md`, never invented.

## 4. Write rules

1. **One owner per file.** Write only the file whose `owner` is your skill name. Read anything. If you believe another file is wrong, say so to the user and record it under "Offene Fragen" in *your* file.
2. **Fertig is frozen.** Never modify a file whose `status` is `fertig`. A rerun ("nochmal") writes `NN-<stage>.v2.md` (then `.v3.md` …) with `revision: 1` in the new file. The Regie records which version is current in `00-maquette.md`.
3. **Findings flow forward, never backward.** New requirements discovered in build go into `40-build.md`, not into `10-seed.md` or `20-plan.md`. Only `60-brief.md` consolidates.
4. **Optimistic locking.** Before writing: read the file, note `revision`. When writing: set `revision + 1` and `updated`. If the file's `revision` on disk is no longer what you read, do not overwrite — write `NN-<stage>.conflict.md` with your content and tell the user in one sentence.
5. **Human notes are untouchable.** When rewriting a file, copy `## Notizen (Mensch)` verbatim from the existing file. Never edit, reorder, summarise or delete it. If the human wrote something there that changes your work, treat it as user input — act on it in your sections, leave theirs alone.
6. **Cite your input.** `input` names the file(s) and revision(s) you read. If the Regie marks your file `veraltet` (the input changed), you do nothing until the user says "nochmal".
7. **Templates are the definition.** Fill the template from `templates/NN-<stage>.md`. Keep every section heading, in order. A section that does not apply gets the line „für die Maquette nicht relevant" — never delete it. Remove the `<!-- -->` guidance comments and the `<…>` placeholders in the finished file.

## 5. Conversation rules (inherited from ki-ideenfindung / konzeptskizze / idea-work)

- **One question at a time.** Never stack questions.
- **Language.** Skill text is English. Talk to the user in the language they use (German: informal „du"). Write result files in the language given by `sprache` in `00-maquette.md`.
- **Opening line.** Each stage starts with two sentences: what this stage produces and roughly how long it takes. No lecture.
- **Evidence marks.** Facts the user gives are tagged `[belegt]`, `[geschätzt]` or `[unbekannt]`. Never fill a gap with your own guess; `[unbekannt]` is a valid answer.
- **Opportunity language.** Say „noch offen" / „wäre zu klären", never „schlecht" / „unrealistisch".
- **Stop anytime.** On „stopp", „reicht", „abbrechen": write the file with whatever exists, mark unfinished sections „offen", set `status: in_arbeit`, hand back to the Regie. Never argue for continuing.
- **Time budget.** `budget_min` in `00-maquette.md` gives your minutes. When you reach it, say so and offer to close with the current state. Do not silently run over.
- **Inline first, file last.** Show interim results as formatted text in the chat. Write the result file once at the end of the stage (or on stop) — not continuously.
- **No confidentiality promises.** Never claim the platform keeps no logs.
- **No hidden actions.** Say what you are about to write or run before you do it. No commits, installs or file writes the user did not hear about.

## 6. Git

`git` in `00-maquette.md` is `ja` only if the maquette folder (or a parent) is a git repository at start. Skills never run `git init`. With `git: nein`, all commit/revert steps in build and harden are skipped and the result file records „— (kein Git)".

## 7. Handing back to the Regie

At the end of a stage, the stage skill reports in one short block: file written (name, revision), status (`fertig` proposed / `in_arbeit`), minutes used, open questions count. Only the Regie sets `status: fertig` and updates the stage table in `00-maquette.md`.
