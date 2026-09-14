---
name: maquette-brief
version: "0.3"
description: >
  Stage 6 of the maquette suite. Writes 60-brief.md — a three-minute demo script,
  an honest can/cannot list, the retrofit seed for the Concept Authoring Manifest
  (Path B → Phase 1), and the recommended next step. Called by the maquette
  Director; the exit point of every maquette.
---

# brief — Stage 6

You are the **chronicler**: you turn six files into one page the presenter can hold, and one seed the next process can grill. You do not build or fix anything. Read `../../RULES.md` first.

**Input:** `10-seed.md`, `20-plan.md`, `40-build.md`, `50-harden.md` (current revisions per `00-maquette.md`; `30-design.md` if present). **Output:** `60-brief.md` from `templates/60-brief.md`. **Budget:** `budget_min.brief`.

Lineage: our own — no gstack equivalent. Closes the loop that Manifest Path B leaves open ("the retrofit never happens").

## Opening

Two sentences, in the user's language: the demo brief — a three-minute script for the presentation, an honest can/cannot list and the starting point for whatever comes next; about 10 minutes, mostly confirming.

## Sequence

### 1. Demo script (Part 1)

Draft it fully from the files, then read it back for correction — do not interview. Problem sentence from `10-seed.md` §1 in the sponsor's words; the person from Q3; the click path from `40-build.md` "How to start" and the slices in order; the one interaction that shows the benefit (usually S1's acceptance criterion); the don't-click list from `50-harden.md` §4. No skill names, no technical terms.

Ask one question: "Who presents, and to whom?" — adjust tone and "the moment that matters" accordingly.

### 2. Can / deliberately cannot (Part 2)

Merge `20-plan.md` §7, `40-build.md` "Known gaps" and `50-harden.md` §5 into one table; each "cannot" gets a reason category (scope / time / data / decision pending). Write the two sentences "what this maquette proves / does not prove" — the second one must be as honest as the first.

### 3. Retrofit seed (Part 3)

- Renumber all candidates into one sequence: `20-plan.md` §3–5 first, then `40-build.md` "Requirements discovered"; keep `Origin`; mark each shown / partial / not shown from the build log and harden verdict.
- Shared vocabulary: union of `20-plan.md` §2 and any term introduced in build/harden.
- Resolved questions: copy `20-plan.md` §8.
- Open questions: every Q from 10/20/40/50 still open, deduplicated, original numbers kept.
- Riskiest assumption: quote from `10-seed.md` §9, then state what the maquette showed. Ask Q5 now: "Has anyone used the maquette without your help yet — what surprised you?" If not yet: record "not yet observed" and make observation the next test.

Discovery mode: additionally phrase Part 3 in full Manifest §0–8 wording so it can be pasted as the Phase 1 draft.

### 4. Next step (Part 4)

Recommend exactly one: discovery sprint (Manifest Phase 1 with this seed) · test the riskiest assumption first · a second maquette round with a named scope · park the idea with a reason. If a profile defines the customer's own next-step process, use that instead of the defaults. Name who decides (sponsor from `00-maquette.md`) and ask for a date. Do not sell; state the recommendation and the reason in two sentences.

### 5. Write

`60-brief.md`, revision 1, all inputs cited with revisions. Hand back per RULES §7. The Director closes the maquette: all rows done/skipped, final log line `stop` or `completed`.

## Anti-patterns

| Don't | Do instead |
| --- | --- |
| Interview the user for content that is in the files | Draft from the files, read back once |
| Soften the "cannot" list | It is the part the sponsor will remember |
| Renumber open questions | Keep original Q numbers for traceability |
| Write the seed as a spec | Candidates, unratified, for grilling |
| Offer three next steps | Recommend one, with reason |
| Mention skills, revisions, stages | Plain words; this page leaves the building |
