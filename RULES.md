# maquette — Shared Rules for All Stage Skills

**Version 2.** Every stage skill reads this file before doing anything. The Director (`maquette`) enforces it. If a stage skill and this file disagree, this file wins.

## 1. Vocabulary

- **Maquette** — a folder containing one clickable model and its documents. Named after the scale model architects build before building.
- **Stage** — one of: sparring → plan-board → design-3 → build → harden → brief. Each stage has exactly one owner skill, one input, one result file.
- **Result file** — `NN-<stage>.md` in the maquette folder, filled from the matching template in `templates/`.
- **Director** — the `maquette` skill. Reads the folder, tells the user where they are, calls the stage skill, updates `00-maquette.md`.
- **Human notes** — the section `## Notes (human)` at the end of every result file.
- **Profile** — an optional `profile/` folder in the workspace with customer-specific constraints (reserved; see §8).

## 2. Folder is the state

There is no state outside the maquette folder — no `~/.something`, no environment variables, no memory across maquettes. A skill learns everything it needs by reading `00-maquette.md`, its input file and (if present) the profile. A skill that needs something else asks the user.

```
<maquette folder>/
  00-maquette.md      Director       control
  10-seed.md          sparring       seed
  20-plan.md          plan-board     plan
  30-design.md        design-3       design   (+ 30-design-a/b/c.html, 30-compare.html)
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
status: <open|in_progress|done|skipped>
revision: <integer, starts at 1>
created: <ISO timestamp, minutes>
updated: <ISO timestamp, minutes>
input: <file>@<revision>[, <file>@<revision>]
---
```

`00-maquette.md` additionally carries `title`, `code`, `mode`, `git`, `language`, `budget_min`. Stage skills read those; only the Director writes them. A template may add stage-specific fields (`40-build.md`: `git`; `50-harden.md`: `git`, `budget_fixes`) — copied from `00-maquette.md`, never invented.

## 4. Write rules

1. **One owner per file.** Write only the file whose `owner` is your skill name. Read anything. If you believe another file is wrong, say so to the user and record it under "Open questions" in *your* file.
2. **Done is frozen.** Never modify a file whose `status` is `done`. A rerun ("redo") writes `NN-<stage>.v2.md` (then `.v3.md` …) with `revision: 1` in the new file. The Director records which version is current in `00-maquette.md`.
3. **Findings flow forward, never backward.** New requirements discovered in build go into `40-build.md`, not into `10-seed.md` or `20-plan.md`. Only `60-brief.md` consolidates.
4. **Optimistic locking.** Before writing: read the file, note `revision`. When writing: set `revision + 1` and `updated`. If the file's `revision` on disk is no longer what you read, do not overwrite — write `NN-<stage>.conflict.md` with your content and tell the user in one sentence.
5. **Human notes are untouchable.** When rewriting a file, copy `## Notes (human)` verbatim from the existing file. Never edit, reorder, summarise or delete it. If the human wrote something there that changes your work, treat it as user input — act on it in your sections, leave theirs alone.
6. **Cite your input.** `input` names the file(s) and revision(s) you read. If the Director marks your file `stale` (the input changed), you do nothing until the user says "redo".
7. **Templates are the definition.** Fill the template from `templates/NN-<stage>.md`. Keep every section heading, in order. A section that does not apply gets the line "not relevant for this maquette" — never delete it. Remove the `<!-- -->` guidance comments and the `<…>` placeholders in the finished file.

## 5. Conversation rules (inherited from ki-ideenfindung / konzeptskizze / idea-work)

- **One question at a time.** Never stack questions.
- **Language.** Skill text is English. Talk to the user in the language they use (German: informal "du"). Write result files in the language given by `language` in `00-maquette.md`; keep the template's section headings as they are (English) so the Director can verify completeness — translate only the content.
- **Opening line.** Each stage starts with two sentences: what this stage produces and roughly how long it takes. No lecture.
- **Evidence marks.** Facts the user gives are tagged `[evidenced]`, `[estimated]` or `[unknown]`. Never fill a gap with your own guess; `[unknown]` is a valid answer.
- **Opportunity language.** Say "still open" / "to be clarified", never "bad" / "unrealistic".
- **Stop anytime.** On "stop", "enough", "abort" (or their equivalents in the user's language): write the file with whatever exists, mark unfinished sections "open", set `status: in_progress`, hand back to the Director. Never argue for continuing.
- **Time budget.** `budget_min` in `00-maquette.md` gives your minutes. When you reach it, say so and offer to close with the current state. Do not silently run over.
- **Inline first, file last.** Show interim results as formatted text in the chat. Write the result file once at the end of the stage (or on stop) — not continuously.
- **No confidentiality promises.** Never claim the platform keeps no logs.
- **No hidden actions.** Say what you are about to write or run before you do it. No commits, installs or file writes the user did not hear about.

## 6. Git

`git` in `00-maquette.md` is `yes` only if the maquette folder (or a parent) is a git repository at start. Skills never run `git init`. With `git: no`, all commit/revert steps in build and harden are skipped and the result file records "— (no git)".

## 7. Handing back to the Director

At the end of a stage, the stage skill reports in one short block: file written (name, revision), status (`done` proposed / `in_progress`), minutes used, open questions count. Only the Director sets `status: done` and updates the stage table in `00-maquette.md`.

## 8. Profile (reserved)

A workspace may contain a `profile/` folder with customer-specific constraints (allowed topics, IT rules, corporate design, extra checklist items, the customer's own next-step process). When it exists, the Director reads it at start and passes the relevant parts to each stage. **A profile may restrict, never loosen:** write rules, git behaviour and "nothing outside the folder" stay as defined here. The profile format is defined in `profile/README.md` once the first profile exists; until then an absent or empty `profile/` means "core defaults".
