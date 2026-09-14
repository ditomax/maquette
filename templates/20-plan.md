---
stage: plan
owner: plan-board
status: in_progress          # open | in_progress | done | skipped
revision: 1
created: <YYYY-MM-DDThh:mm>
updated: <YYYY-MM-DDThh:mm>
input: 10-seed.md@<rev>
---

# Plan <code>: <title>

_Result of the plan-board stage. The structure follows the Concept Authoring Manifest §0–8 in model depth: sections that do not apply to the maquette stay in place and carry the line "not relevant for this maquette" — so the later retrofit is a diff, not a restart._

## 0. Synthesis context

- **Path:** B (retrofit) — the maquette is built first, the concept extracted afterwards
- **Dependencies:** <other documents/systems the prototype relies on, or "none">
- **Scope of synthesis:** <what can be built from this plan alone>

## 1. Purpose

<from 10-seed.md §1, sharpened in grilling-light>

## 2. Shared vocabulary

<from 10-seed.md §4, extended with terms from the grilling>

## 3. Functional requirements (cF)

<!-- Taken from 10-seed.md §7 and checked in grilling-light: struck, sharpened, added. IDs stay stable; new IDs continue the sequence (cF-9 …). Each row names the slice that shows it. -->

| ID | Requirement | Slice |
| --- | --- | --- |
| cF-1 | <…> | S1 |

## 4. User interaction (cU)

| ID | Requirement | Slice |
| --- | --- | --- |
| cU-1 | <…> | S1 |

## 5. Non-functional requirements (cNF)

| ID | Requirement | Slice |
| --- | --- | --- |
| cNF-1 | <…> | — |

## 6. Integration points

<data sources, files, APIs the prototype really touches — or "not relevant for this maquette: everything synthetic">

## 7. Out of scope

<!-- Explicit, so build does not drift and brief has its cannot-list. Includes the non-cases (empty / many / error) deliberately left out. -->

- <…>

## 8. Resolved questions

<!-- From 10-seed.md §8 and grilling-light. Each Q gets a one-line decision. Questions that stay open move unchanged to §11. -->

| Question | Decision | Reason |
| --- | --- | --- |
| Q1 | <…> | <…> |

## 9. Review board

<!-- Three roles read in sequence. Each role: small decisions taken on its own (list), real forks put to the user (question → answer). Idea from gstack autoplan (© 2026 Garry Tan, MIT License, see `LICENSES/gstack-MIT.txt`), without the DX role and without unbounded depth. -->

### Product
- **Decided on its own:** <…>
- **Fork put to the user:** <question> → <the user's answer>

### Design
- **Decided on its own:** <…>
- **Fork put to the user:** <…>

### Engineering
- **Decided on its own:** <stack, data handling, start command — as simple as possible>
- **Fork put to the user:** <…>

## 10. Slices

<!-- 3–5 vertical slices, each demonstrable on its own. S1 is the scope sentence from 10-seed.md §2 Q4. Flow comes from the walk-through in 10-seed.md §7. Each slice has exactly one acceptance criterion that build checks with a smoke test. -->

| Slice | Shows | Flow | Acceptance criterion | Requirements |
| --- | --- | --- | --- | --- |
| S1 | <…> | <step → step → result> | <one sentence, checkable by clicking> | cF-1, cU-1 |
| S2 | <…> | <…> | <…> | <…> |

**Technical essentials:** <stack, start command, data source — three lines, no architecture chapter>

## 11. Open questions

<!-- Numbering continues from 10-seed.md. -->

- **Q<n>** — <…>

## 12. Gate

- **Approved by the user:** <yes, at <hh:mm> | with changes: <…> | no — redo>
- **Rework rounds:** <0 | 1>

## Notes (human)

<!-- Off limits for all skills. Copied verbatim on every rewrite. -->
