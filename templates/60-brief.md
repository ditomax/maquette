---
stage: brief
owner: brief
status: in_progress          # open | in_progress | done | skipped
revision: 1
created: <YYYY-MM-DDThh:mm>
updated: <YYYY-MM-DDThh:mm>
input: 10-seed.md@<rev>, 20-plan.md@<rev>, 40-build.md@<rev>, 50-harden.md@<rev>
---

# Brief <code>: <title>

_Result of the brief stage and exit point of the maquette. Part 1 is for the presentation, Part 2 for the decision afterwards, Part 3 the retrofit seed for the Concept Authoring Manifest (Path B → Phase 1)._

## Part 1 — Demo script (3 minutes)

<!-- For the person presenting. No technology, no skill names. -->

- **The problem in one sentence:** <from 10-seed.md §1, in the sponsor's words>
- **For whom:** <the specific person from Q3>
- **Click path:**
  1. <start: command/address from 40-build.md>
  2. <step — what you see — what you say>
  3. <…>
- **The moment that matters:** <the one interaction that shows the benefit>
- **What not to click:** <limitations from 50-harden.md §4>

## Part 2 — Can / deliberately cannot

| Can | Deliberately cannot | Why not |
| --- | --- | --- |
| <…> | <from 20-plan.md §7, 40-build.md "Known gaps", 50-harden.md §5> | <scope | time | data | decision pending> |

**What this maquette proves:** <one sentence>
**What it does not prove:** <one sentence — honest, so nobody mistakes a prototype for a product>

## Part 3 — Retrofit seed

<!-- The handover point into the Manifest. Everything 10, 20, 40, 50 taught, consolidated. Candidates stay unratified; Phase 1 (grilling) ratifies and renumbers. -->

### Updated candidate requirements

<!-- From 20-plan.md §3–5 plus 40-build.md "Requirements discovered", renumbered into one sequence. Column "Status in maquette": shown | partial | not shown. -->

| ID | Requirement | Origin | Status in maquette |
| --- | --- | --- | --- |
| cF-1 | <…> | seed | shown |
| cF-<n> | <…> | build | partial |

### Shared vocabulary

<from 20-plan.md §2, extended with terms from build/harden — starting point for CONTEXT.md>

### Resolved questions

<from 20-plan.md §8 — kept as ADR seeds>

### Open questions

<!-- Every Q from 10, 20, 40, 50 still open, deduplicated, original numbers kept. This is the grilling session's starting ammunition. -->

- **Q<n>** — <…>

### Riskiest assumption — state after the maquette

- **Assumption (from 10-seed.md §9):** <…>
- **What the maquette showed:** <confirmed | weakened | untouched — with observation>
- **Q5 Observation:** <Has anyone used the maquette without help? What surprised you? — or "not yet observed: next test">

## Part 4 — Next step

- **Recommendation:** <discovery sprint (Manifest Phase 1 with this seed) | test the riskiest assumption first | second maquette round with scope <…> | stop — idea parked because <…>>
- **Who decides:** <sponsor from 00-maquette.md>
- **When:** <…>

## Notes (human)

<!-- Off limits for all skills. Copied verbatim on every rewrite. -->
