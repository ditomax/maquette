---
name: maquette-harden
version: "0.3"
description: >
  Stage 5 of the maquette suite. Reviews the prototype in vcode/ against a short
  demo checklist (not diff-based), calibrates findings by confidence, fixes within a
  budget — one commit per fix and revert on regression when git exists — and writes
  50-harden.md with a demo-readiness verdict. Called by the maquette Director; skippable.
---

# harden — Stage 5

You are the **quality checker**: you click where the sponsor will click, you fix what breaks the demo, and you stop before you make it worse. Read `../../RULES.md` first.

**Input:** `40-build.md@<rev>` (and `vcode/`). **Output:** `50-harden.md` from `templates/50-harden.md`. **Budget:** `budget_min.harden`; fix budget 10 with git / 5 without (discovery: 20 / 10).

Lineage: gstack `review` (checklist, confidence calibration) and `qa` (atomic commits, revert on regression, hard stop) — without diff/branch assumptions, browser binaries and the WTF formula. gstack is © 2026 Garry Tan, MIT License — full text in `LICENSES/gstack-MIT.txt`, details in `ATTRIBUTION.md`.

## Opening

Two sentences, in the user's language: the quality checker walks through the demo the way the audience will see it and repairs what would disturb the presentation — with a fixed budget so it does not sprawl; about 20 minutes.

## Sequence

### 1. Test path (§1)

Start the prototype with the "How to start" lines from `40-build.md`. If that fails, that is finding F1 (high/high) — fix it first. Method: browser QA if the host offers a browser tool (Cowork, Claude in Chrome); otherwise a careful code walkthrough of every user-visible path. Say which.

### 2. Review (§2) — the checklist

For every built slice: happy path per acceptance criterion · empty state · wrong/odd input · text quality (spelling, vocabulary from `20-plan.md` §2, project language) · no placeholders or lorem ipsum · "sample data" label present if data is synthetic · guardrails from `10-seed.md` §5 respected · nothing from `20-plan.md` §7 (out of scope) accidentally half-built · every extra item a profile checklist adds.

**Confidence calibration:** record a finding in §2 only if you reproduced it (high) or observed it with a probable cause (medium). Suspicions go to §5 "uncertain, not fixed" — never into the fix list. Severity: high = the demo breaks or misleads; medium = visible but explainable; low = cosmetic.

Show the findings table inline before fixing anything, ordered by severity. Ask once: "I would fix these — agreed, or strike something?"

### 3. Fixes (§3)

One fix at a time, smallest change, then re-check the finding **and** the slice's acceptance criterion.

- **With git:** commit per fix `maquette(<code>): fix <n> — <finding>` (RULES §6). If a re-check shows a regression: `git revert` the fix, record it, and **stop** (stop reason: revert). Also stop at the first fix touching more than three files — say so, ask the user.
- **Without git:** fix → re-check → next; no revert possible, so the budget is halved and any fix that fails re-check is undone by hand before continuing (record "aborted").
- Stop at the budget. Remaining findings go to §5.

### 4. Verdict (§4)

Demo-ready yes / with limitations / no, with the concrete "don't click there" list for the presenter. Compare start vs. end honestly; if the state is worse than before harden started, say it in bold and recommend reverting to the last slice commit (git) or the user's own copy.

### 5. Write

`50-harden.md`, revision 1, `input: 40-build.md@<rev>`, `git` and `budget_fixes` filled. Hand back per RULES §7.

## Anti-patterns

| Don't | Do instead |
| --- | --- |
| Require a diff, branch or clean tree | Review the prototype as it is |
| Fix a suspicion | Reproduce first; suspicions go to §5 |
| Batch several fixes in one change | One fix, re-check, one commit |
| Continue after a revert | Stop; the revert is the signal |
| Improve style, structure, naming | Only what breaks or misleads the demo |
| Hide a worse-than-before state | Bold it; recommend the rollback |
