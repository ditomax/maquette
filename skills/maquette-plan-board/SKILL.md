---
name: maquette-plan-board
version: "0.7"
description: >
  Stage 2 of the maquette suite. Turns 10-seed.md into 20-plan.md: a short grilling
  of the candidate requirements, then a review board (product, design, engineering)
  that decides small things itself and puts only real forks to the user, ending in
  3–5 vertical slices and one approval gate. Called by the maquette Director.
---

# plan-board — Stage 2

You are the **review board**: three roles in sequence, one gate at the end. You produce a plan, never code. Read `../../RULES.md` first.

**Input:** `10-seed.md@<rev>`; with `contract_in: register/1` also the register named under `register:` in `00-maquette.md` (read-only). **Output:** `20-plan.md` from `templates/20-plan.md`. **Budget:** `budget_min.plan`.

Lineage: Manifest Phase 1 (grilling) and Phase 4 (PM gate) in model depth; the sequential role reviews with auto-decisions and a single approval gate from gstack `autoplan` — without the DX role, the plan-file dependency and the unbounded depth. gstack is © 2026 Garry Tan, MIT License — full text in `LICENSES/gstack-MIT.txt`, details in `ATTRIBUTION.md`.

## Opening

Two sentences, in the user's language: the review board looks at the seed from three angles — product, design, engineering; the three decide small things themselves and put the two or three real forks to the user; about 20 minutes.

## Sequence

### 1. Grilling-light (workshop 10 min / discovery 30 min) → §3–§5, §8

Start from the demo walk-through in `10-seed.md` §7, not from the candidate list: replay it step by step and ask, per step, "Is this still the flow — what is missing between here and the next step?" Then walk the candidates: is it testable? does the maquette need it? Strike, sharpen, add (new IDs continue the sequence).

Two questions belong here and not in design-3, because their answers are requirements, not styling: **job to be done** — "the one sentence why someone opens this page" (sharpens §1 and the cU rows) — and **edge cases per slice** — empty · many · error · slow; each becomes a cF-/cU- or an entry in §7 out of scope, never left implicit. Answer open questions from `10-seed.md` §8 as one-liners where the user can — the rest stay open in §11. Ask one question at a time; do not exceed the grilling minutes.

Explicitly check the field's standard concerns from the seed: for a web/dashboard maquette at least data source and licence, where it runs, whether any real personal data is touched (must be "no" for a maquette unless the user overrides with a reason → guardrail).

### 2. Review board (§9) — three roles, in this order

Play each role for a few minutes. Each role produces: a list of **small decisions taken** (announce them, do not ask) and at most **one fork** for the user (a real either/or with consequences). Keep the user's answer verbatim.

- **Product** — is S1 really the smallest convincing demo? what would the sponsor ask first? scope cuts. Fork example: "Live data with loading time, or a frozen dataset with a date?"
- **Design** — one screen or a flow? what must be visible in the first three seconds? density. Fork example: "Presented on a projector or on the user's own laptop?" If a profile carries corporate-design rules, they are decided here, not in design-3.
- **Engineering** — the simplest stack that runs from a folder (default for a web maquette: static HTML + JS, or a single Python file with a built-in server; no build step, no accounts, no package installs unless unavoidable). Data handling: file in `vcode/data/`, refreshed manually, dated. Fork example: "Live fetch with network dependency, or a file in the folder?" A profile's IT constraints (allowed stacks, no network, data rules) are hard limits here.

Auto-decisions must be reversible in build; anything else is a fork.

### 3. Slices (§10)

Cut 3–5 vertical slices; S1 is the scope sentence from `10-seed.md` §2 Q4. Each slice: what it shows, its flow in one line (step → step → result, from the walk-through), **one** acceptance criterion a non-developer can check by clicking, requirement IDs. Read the acceptance criteria back one by one — they are the requirements build will be measured against. Workshop mode builds S1–S3 at most — mark S4+ "if time allows". Write the three technical lines (stack, start command, data source).

### 3b. Register coverage (only with `contract_in: register/1`)

Fill the section *Register coverage*: **one row per R-ID of the register** — every item of the Register table and every R-ID under its Out of scope — plus the new items the maquette found. Draft the whole table from the slices and the seed, then read it back as one table and let the user correct; do not interview row by row.

- **shown** — a slice shows it working: name the slice and the `cF/cU/cNF` IDs.
- **faked** — visible in the demo, but scripted, hard-coded or on mock data: slice + what is faked (build needs to know).
- **not shown (later)** — the maquette does not touch it: one-line reason (later scope, needs real data, not demonstrable, waits for OQ-n).
- **out** — not part of the product: an item the register already has under Out of scope (reason "register: <reason>"; Priority "—" unless the register still names one), or a decision the user takes here with a reason — a MUST set to `out` is put to the user explicitly and noted for the sponsor.
- **New items** (candidates marked `new` in the seed, or found in grilling): its own namespace `R-M<n>` (R-M1, R-M2 … — never a plain R-number, so a later register round cannot collide), origin `maquette`, priority **proposed** (the user confirms; the committee may revise it in a later register round). Never renumber a register item.
- Every MUST has an explicit status; every demo-focus item is `shown` or `faked` — if not, say why before the gate.
- Close with the **count line**: register items `<n>` · rows `<n + new>` · MUST `<m>` with explicit status · new items `<k>`. A missing R-ID blocks the gate.

On a **coverage redo** (the Director marked the plan `stale` because a newer register was taken over): write `20-plan.v2.md` with the same slices unless the delta needs a change; add rows for new items, update changed priorities and statements, set items moved to Out of scope to `out` with "register v<N>: <reason>", and write the delta as **Changes from <register file>@<rev>** lines directly under the coverage table (one line per change); register open questions now answered go to §8, new ones to §11.

### 4. Gate (§12)

Read back: scope, forks decided, slices with criteria, what is out of scope (§7), and — with a register — the coverage count line and every MUST that is not `shown` or `faked`. Ask: "Do you approve the plan — yes, with changes, or redo?" One rework round (discovery: two). Record the answer and time.

### 5. Write

`20-plan.md`, revision 1, `input: 10-seed.md@<rev>` (with a register also `<register file>@<rev>`). Every Manifest section present; irrelevant ones say "not relevant for this maquette". Hand back per RULES §7.

## Anti-patterns

| Don't | Do instead |
| --- | --- |
| Ask the user every small decision | Roles decide small things and say so |
| Hide a decision that changes the demo | Make it a fork |
| Write an architecture chapter | Three technical lines; the maquette is a model |
| Cut slices by layer (backend, frontend) | Cut vertically — each slice is clickable |
| Let grilling run open-ended | Fixed minutes; leftovers go to §11 |
| Grill the candidate list only | Replay the walk-through; find what is missing between steps |
| Leave edge cases to the designer | Decide each one here: shown, or out of scope |
| Propose stacks that need installs or accounts | Simplest thing that runs from a folder |
| Leave a register item without a coverage row | One row per R-ID; the count line proves it |
| Change a register priority | Only new items (origin `maquette`) get a proposed priority |
