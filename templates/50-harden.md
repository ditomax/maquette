---
stage: harden
owner: harden
status: in_progress          # open | in_progress | done | skipped
revision: 1
created: <YYYY-MM-DDThh:mm>
updated: <YYYY-MM-DDThh:mm>
input: 40-build.md@<rev>
git: <yes | no>
budget_fixes: <10 with git | 5 without git>
---

# Hardening <code>: <title>

_Result of the harden stage. Review against the maquette checklist (not diff-based), then fixes within a budget. Ideas from gstack review and qa (© 2026 Garry Tan, MIT License, see `LICENSES/gstack-MIT.txt`): confidence calibration, one fix per commit, stop on regression._

## 1. Test path

- **Method:** <browser QA (host: <…>) | code walkthrough (no browser available)>
- **Started with:** <commands from 40-build.md "How to start">
- **Slices checked:** <S1…Sn>

## 2. Findings

<!-- Checklist: happy path per slice · empty states · wrong input · text quality (spelling, vocabulary from plan §2) · no placeholders / lorem ipsum · "sample data" label present if data is synthetic · guardrails from 10-seed.md §5 respected · nothing from 20-plan.md §7 (out of scope) accidentally half-built.
     Confidence: high = reproduced; medium = observed, cause presumed. Low-confidence findings do NOT go here but into §5. -->

| No. | Slice | Finding | Severity | Confidence | Decision |
| --- | --- | --- | --- | --- | --- |
| F1 | S1 | <…> | <high | medium | low> | <high | medium> | <fix | leave: <reason>> |

## 3. Fixes

<!-- One entry per fix, in order. With git: commit per fix, revert on regression, budget 10, STOP at the first revert and at any fix touching > 3 files. Without git: one fix → check → next, no revert, budget 5. -->

| Fix | Finding | Files | Result | Commit / check note |
| --- | --- | --- | --- | --- |
| X1 | F1 | <n> | <fixed | regression → reverted | aborted> | <hash | "checked hh:mm"> |

**Budget used:** <used / budget> · **Stop reason:** <none | budget | revert | > 3 files | user>

## 4. Verdict

- **Demo-ready:** <yes | with limitations | no>
- **Limitations:** <what the presenter must know and avoid>
- **Start vs. end state:** <better | same | worse — if "worse", highlight it clearly>

## 5. Appendix: uncertain, not fixed

<!-- Low-confidence findings or those outside the budget. Nothing is lost; brief takes them into the cannot-list or the open questions. -->

- <…>

## Open questions

- **Q<n>** — <…>

## Notes (human)

<!-- Off limits for all skills. Copied verbatim on every rewrite. -->
