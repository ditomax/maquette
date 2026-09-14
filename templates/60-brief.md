---
stage: brief
owner: brief
status: in_progress          # open | in_progress | done | skipped
revision: 1
created: <YYYY-MM-DDThh:mm>
updated: <YYYY-MM-DDThh:mm>
input: 10-seed.md@<rev>, 20-plan.md@<rev>, 40-build.md@<rev>, 50-harden.md@<rev>
contract: H2/1               # handover contract version read by build ≥ 0.1.0
---

# Brief <code>: <title>

_Result of the brief stage and exit point of the maquette. Part 1 is for the presentation, Part 2 for the decision afterwards, Part 3 is **contract H2** — the handover to build. Build intake reads Part 3 and `vcode/` (read-only) and runs Path B (extract what the prototype already answers) before Path A (grill what it does not)._

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

## Part 3 — Handover to build

<!-- Everything 10, 20, 40, 50 taught, consolidated. Candidates stay unratified; build's grilling ratifies and renumbers. Nothing here is edited after `done` — build writes its findings into planning/build/, never back into this file. -->

### Field of application

<one line, from 10-seed.md — build derives its standard concerns from it (web → data protection, access, deployment)>

### Updated candidate requirements

<!-- From 20-plan.md §3–5 plus 40-build.md "Requirements discovered", renumbered into one sequence. Column "Status in maquette": shown | partial | not shown. "not shown" rows are Path A material; "shown" rows are Path B material. -->

| ID | Requirement | Origin | Status in maquette |
| --- | --- | --- | --- |
| cF-1 | <…> | seed | shown |
| cF-<n> | <…> | build | partial |

### Shared vocabulary

<from 20-plan.md §2, extended with terms from build/harden — becomes CONTEXT.md in build>

### Resolved questions

<from 20-plan.md §8 — become ADR seeds in planning/build/decisions/>

### Open questions

<!-- Every Q from 10, 20, 40, 50 still open, deduplicated, original numbers kept, plus every waiver that came in from the shortlist. This is the grilling agenda for Path A. -->

- **Q<n>** — <…>

### Riskiest assumption — state after the maquette

- **Assumption (from 10-seed.md §9):** <…>
- **What the maquette showed:** <confirmed | weakened | untouched — with observation>
- **Q5 Observation:** <Has anyone used the maquette without help? What surprised you? — or "not yet observed: next test">

### Prototype facts (for Path B)

<!-- What build intake needs to read vcode/ correctly. Facts, not judgement. vcode/ stays in this maquette folder, frozen; build reads it for inspiration (requirements, data shapes, CI) and never edits it. -->

- **Stack and entry point:** <languages, frameworks, how to start — from 40-build.md>
- **Real vs. faked:** <which behaviours are implemented, which are stubbed, hard-coded or scripted — one line each>
- **Data:** <which data is real, which is mock or synthetic, where it lives>
- **Shortcuts taken:** <from 50-harden.md — what was deliberately not fixed and why>
- **Worth keeping:** <parts of vcode/ the build team suggested reusing as-is, or "nothing — rebuild from concept">
- **Not worth keeping:** <parts that only exist to make the demo run>

## Part 4 — Next step

- **Recommendation:** <build intake (Path B, then Path A grilling) | test the riskiest assumption first | second maquette round with scope <…> | stop — idea parked because <…>>
- **Who decides:** <sponsor from 00-maquette.md>
- **When:** <…>

## Notes (human)

<!-- Off limits for all skills. Copied verbatim on every rewrite. -->
