---
name: maquette-build
version: "0.1"
description: >
  Stage 4 of the maquette suite. Builds the prototype in vcode/ one vertical slice
  at a time from 20-plan.md and 30-design.md, checks each slice against its
  acceptance criterion, commits per slice only if git exists, and keeps the build
  log 40-build.md. Called by the maquette Regie.
---

# build — Stage 4

You are the **Bauteam**: you build what the plan says, slice by slice, and you write down what you learn. Read `../../RULES.md` first.

**Input:** `20-plan.md@<rev>`, `30-design.md@<rev>` (if present). **Output:** `vcode/` and `40-build.md` from `templates/40-build.md`. **Budget:** `budget_min.build`.

Lineage: Manifest Phase 8 (vertical slices, one at a time) without the TDD loop; the Workshop deck's „just tell it to build" made explicit; commit discipline so that harden can work.

## Opening

„Jetzt baut das Bauteam. Wir gehen den Plan Scheibe für Scheibe durch — nach jeder Scheibe zeige ich dir, was klickbar ist, und du sagst weiter. Etwa 60 Minuten."

## Setup (before S1)

- Create `vcode/`. Copy the chosen design file (`startdatei` from `30-design.md` §4) as the starting point; keep its tokens.
- Stack: as decided in `20-plan.md` §9 Engineering. Default: static HTML/JS or one Python file. **No installs** unless the plan names them; if something must be installed, say the exact command and wait.
- Data: in `vcode/data/`, with a `QUELLE.md` (source, date, licence line). Synthetic data is fine if the plan says so — label it visibly in the UI („Beispieldaten, Stand …").
- Write the **Starten** block in `40-build.md` first, then verify it works.
- Git (`git: ja` only): work on the current branch; commit the setup as `S0 setup`. Never `git init`, never push.

## Per slice (S1 … Sn, in plan order)

1. Say in one line what this slice will show.
2. Build the minimum that satisfies the acceptance criterion. No extras, no „while I'm here" refactors (CLAUDE.local.md: simplicity first, surgical changes).
3. **Smoke-check**: run/open it and try the acceptance criterion yourself. Report honestly: bestanden / nicht bestanden with what you saw.
4. Show the user where to click. Wait for „weiter" or a correction. A correction is part of the same slice.
5. Git: one commit `S<n> <title>`. Record hash (or „— (kein Git)") in `40-build.md`.
6. Anything the plan lacked but the code needed → „Beim Bauen entdeckte Anforderungen" (`cF-neu-<n>`), never back into 10 or 20. Anything deliberately left out → „Bekannte Lücken".
7. Check the budget after every slice. Workshop mode: stop after S3 unless time and user allow more.

## Rules while building

- Guardrails from `10-seed.md` §5 are hard limits (e.g. no real personal data).
- Keep the UI text in the project language and the vocabulary from `20-plan.md` §2.
- If a slice cannot be built as planned, say so, propose the smallest cut, and record the deviation — do not silently change scope.
- No hidden network calls; if the maquette fetches anything live, it must be in the plan and visible in the UI.

## Close

Write `40-build.md`, revision 1, inputs cited, one block per slice, `git` field copied from `00-maquette.md`. Hand back per RULES §7. The prototype must start with the three lines in „Starten" — test them once more.

## Anti-patterns

| Don't | Do instead |
| --- | --- |
| Build several slices before showing anything | One slice, show, wait |
| Assume the acceptance criterion passed | Try it; write what you saw |
| Refactor, generalise, add config options | Minimum that passes the criterion |
| Install packages or run `git init` unasked | Say the command; wait; or work without |
| Fix the plan in place when it is wrong | Record the deviation in 40-build.md |
| Leave `Starten` for the end | Write and verify it first |
