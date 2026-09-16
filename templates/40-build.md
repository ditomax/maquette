---
stage: build
owner: build
status: in_progress          # open | in_progress | done | skipped
revision: 1
created: <YYYY-MM-DDThh:mm>
updated: <YYYY-MM-DDThh:mm>
input: 20-plan.md@<rev>, 30-design.md@<rev>
git: <yes | no>              # copied from 00-maquette.md
---

# Build <code>: <title>

_Result of the build stage. The code lives in `vcode/`. This file is the build log: one entry per slice, in order, never changed retroactively._

## How to start

<!-- Three lines a non-developer can execute. Used by harden and brief. -->

```
<command 1, e.g. cd vcode>
<command 2, e.g. python -m http.server 8000>
<address, e.g. http://localhost:8000>
```

## Slices

<!-- One block per slice. Status: done | partial | dropped. Smoke check = the acceptance criterion from 20-plan.md §10, actually tried, not assumed. Commit only with git. -->

### S1 — <title from 20-plan.md>
- **Status:** <done | partial | dropped>
- **Smoke check:** <acceptance criterion> → <passed | failed: <…>>
- **Commit:** <hash | — (no git)>
- **Deviation from plan:** <none | <what and why>>
- **Duration:** <minutes>

### S2 — <…>
- …

## Requirements discovered while building

<!-- Everything the plan lacked and the code needed. IDs continue from 20-plan.md (cF-new-1 … until brief sorts them in). Never written back into 10 or 20 (write rule 3). -->

| ID | Requirement | Discovered in slice | Implemented? |
| --- | --- | --- | --- |
| cF-new-1 | <…> | S<n> | <yes | no> |

## Known gaps

<!-- What was deliberately left out or stubbed. Honestly — harden checks exactly here, brief turns it into the cannot-list. -->

- <…>

## Open questions

- **OQ-<n>** — <…>

## Notes (human)

<!-- Off limits for all skills. Copied verbatim on every rewrite. -->
