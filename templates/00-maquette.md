---
stage: control
owner: maquette
status: in_progress          # open | in_progress | done | skipped
revision: 1
created: <YYYY-MM-DDThh:mm>
updated: <YYYY-MM-DDThh:mm>
input: —
# --- only in 00-maquette.md ---
title: <working title of the maquette>
code: <2–4 letters, e.g. WST>
mode: workshop               # workshop | discovery
git: no                      # yes | no — checked by the Director at start
language: en                 # language of the result files' content
budget_min: {sparring: 15, plan: 20, design: 15, build: 60, harden: 20, brief: 10}
profile: none                # none | profile/ (if a profile folder exists)
contract_in: none            # none | H1/1 | H1/2 (started from a shortlist entry)
demo_variants: —             # umbrella entry only: variant IDs the demo shows (from the shortlist's Maquette order)
---

# Maquette <code>: <title>

<!-- This file belongs to the Director. No other skill writes here. -->

## Starting point

- **Input:** <shortlist entry <ID> (<path>@<rev>) | idea in two sentences | idea card <ID> | concept sketch <ID>-K>
- **Sponsor:** <role, if known>
- **Purpose of this maquette:** <one sentence: what should be decidable after the demo?>

## Stages

| Stage | Skill | File | Status | Current revision | Started | Finished | Minutes |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | sparring | 10-seed.md | open | — | | | |
| 2 | plan-board | 20-plan.md | open | — | | | |
| 3 | design-3 | 30-design.md | open | — | | | |
| 4 | build | 40-build.md | open | — | | | |
| 5 | harden | 50-harden.md | open | — | | | |
| 6 | brief | 60-brief.md | open | — | | | |

<!-- Status values: open | in_progress | done | skipped | stale (input changed, see write rule 6).
     "Current revision" names the file the next stage must read, e.g. 20-plan.v2.md. -->

## Decision log

| Time | Stage | Decision | Note |
| --- | --- | --- | --- |
| <hh:mm> | — | start | mode <workshop>, git <no> |

<!-- Allowed decisions: start · next · redo · stop · skip · budget_exceeded (with the user's answer) -->

## Open items for the Director

<!-- Things the Director must raise at the next call: exceeded budget, conflict files, stale downstream files, pending user decisions. Empty = nothing open. -->

- —

## Notes (human)

<!-- Off limits for all skills. The human corrects, adds and comments here. Copied verbatim on every rewrite. -->
