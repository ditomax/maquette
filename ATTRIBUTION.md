# Attribution

maquette is an original skill suite by DMBG (Dietmar Millinger). It contains no code and no text copied from third-party projects, but several of its methods are adapted from open-source work. This file names them.

## gstack — Garry Tan, MIT License

Repository: https://github.com/garrytan/gstack · Version consulted: 1.79.0 (September 2026)

The full license text is in `LICENSES/gstack-MIT.txt` and reproduced here verbatim, as the license requires:

```
MIT License

Copyright (c) 2026 Garry Tan

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

Files in this suite that carry adapted gstack methods reference this file in their "Lineage" line: `skills/maquette-sparring`, `skills/maquette-plan-board`, `skills/maquette-design-3`, `skills/maquette-harden`, and the templates `10-seed.md`, `20-plan.md`, `30-design.md`, `50-harden.md`. The suite itself is © 2026 Dietmar Millinger, MIT License (`LICENSE`).

Methods adapted (paraphrased, restructured, and reduced to prompt-only form):

| gstack skill | Adapted into | What was taken |
| --- | --- | --- |
| office-hours | maquette-sparring | the six forcing questions (demand reality, status quo, desperate specificity, narrowest wedge, observation & surprise, future-fit), the framing check after Q1, the premise challenge, the mandatory alternatives stop before choosing a direction |
| autoplan | maquette-plan-board | sequential role reviews (product, design, engineering) that take small decisions autonomously and surface only real forks, ending in a single approval gate |
| design-shotgun | maquette-design-3 | five context dimensions, three variants under an anti-convergence rule (must differ in type, colour and layout), side-by-side comparison, choice with recorded reasoning |
| review | maquette-harden | checklist-driven review, confidence calibration (low-confidence findings go to an appendix, not the fix list) |
| qa | maquette-harden | one commit per fix, revert on regression, a hard stop budget instead of open-ended fixing |

Not adopted: gstack's runtime (TypeScript, bun), browser binaries, telemetry, Supabase backend, egress ledger, taste profiles, slug-bound shared state, YC framing, and all preamble/setup sections.

## Our own sources

- **idea-work** (DMBG) — six ideation modes, Concept Seed format, candidate requirement IDs `cF-/cU-/cNF-`, pre-mortem, open-question numbering.
- **ki-ideenfindung v0.8** and **konzeptskizze v0.1** (DMBG) — one question at a time, opening statement, stop-anytime rule, evidence marks `[belegt|geschätzt|unbekannt]`, opportunity language, prefill-and-read-back, no confidentiality promises.
- **Concept Document Authoring Manifest v8** and **CLAUDE.local.md v2** (DMBG) — Path B (retrofit), document template §0–8, vertical slices, grilling, PM gate, simplicity-first and surgical-change principles.
- The "virtual team" narrative (CEO / Design Manager / Engineering / QA agents) originates in the enliteAI workshop deck for RHI Magnesita (September 2026) and is used here only as plain-language role names.
