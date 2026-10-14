# Changelog — maquette

## 0.7.0 — 2026-10-14
**Reads contract `register/1`** (idea ≥ 0.3.0, focus track). The Director finds `10-register.md` (project layout: the highest `.vN`; standalone: named or pasted) — one project, no pick; a `register/2` or later is named and the Director stops instead of guessing. Outcome `stop`, `next: build` and a partial committee are said once. Sparring prefills from frame, project check, register and handover: demo focus → Q4, "what would tip it" → premise, V7 → guardrail candidate, dissent → hints, open questions → `OQ-n` (never re-asked), K.o. conditions (origin `review`) → guardrails; candidates carry their R-ID. **Coverage table** (new section *Register coverage* in `20-plan.md`, final in `60-brief.md`): every R-ID is `shown` · `faked` · `not shown (later)` · `out`, with a reason where needed; every MUST explicit; a count line proves nothing dropped; new requirements get their own namespace `R-M<n>` (origin `maquette`, priority proposed) so a later register round can never collide; register priorities are never changed. **Newer register** (`10-register.vN.md`) is detected on every opening, shown as a delta and taken over by a coverage redo of the plan (design/build/harden stale only if an item newly becomes shown or faked). **Contract out H2/3:** brief Part 3 gains *Register and coverage* (the full register with final coverage, K.o. decisions, Users and scale, V6 note) and a *Register* column in the candidate table — read by build ≥ 0.2.0. H1/2 and H1/1 unchanged. Also: Director and bootstrap files read `profile/profile.md` (not `profile/README.md`); code 2–5 letters. RULES v3, QUESTIONS v3 (D1R, D6, P9; S0 extended). After test run-04: the delta covers lights and K.o. decisions, open questions and the *Complete* line; a coverage redo replaces the general redo rule (only plan and brief stale; unstarted stages stay open); after the brief is done a newer register is left to build; delta lines sit under the coverage table; out-of-scope R-IDs carry "—" where the register has no value; harden skipped → the brief takes Known gaps; `register:` path relative to the maquette folder; brief carries the V5 and V6 notes and the register versions. Examples: `60-brief.md` as H2/3 without register, new `60-brief-register.md`. **START.md** opens with *For AI agents* (start → read `AGENTS.md` and the files it names; a question about the file → answer, no workflow; local folder vs. GitHub link of the same release; say which step is missing); fallback sentence now "Read AGENTS.md in the folder that contains START.md and begin." (works in a renamed folder and when a parent folder is open); a hint tells people to skip the agent section; README § For agents: the copy goes into a project folder on the user's computer that the user can see, never only into the agent's sandbox. `AGENTS.md`/`CLAUDE.md` carry the same question-only exception.

## 0.6.3 — 2026-10-05
`ATTRIBUTION.md` names the AI tools used in development (Claude Opus, GPT-6 Astra). No contract change.

## 0.6.2 — 2026-09-17
README: own **Contracts** section (H1 in, H2 out, both optional) instead of a paragraph inside *How it works*; new **Language** and **Git** sections, the two duplicate git paragraphs folded into the latter; section order aligned with idea and build. No contract change. The company abbreviation DMBG is gone from the public texts: the product is simply the skill suite (idea → maquette → build); source credits in `ATTRIBUTION.md` name Dietmar Millinger.

## 0.6.1 — 2026-09-17
Discoverability: README gains § The suite (links to idea, maquette, build and skill-suite-setup, one line each, pointer to the `planning/` form for multi-skillset or customer use); § For agents no longer tells agents to ignore skill-suite-setup — point 3 names it as the producer of the `planning/` form, point 4 keeps only `hooks/` and `guard.py` as developer-only. START calls skill-suite-setup "the suite's setup tool" instead of "the maintainers' tool". No contract change.

## 0.6.0 — 2026-09-17
**Reads contract H1/2** (idea ≥ 0.2.0), H1/1 still accepted. Director proposes the entry the committee named under the shortlist's Maquette order (`next_maquette`) and, for an umbrella entry, its demo variants; the user confirms or picks another with a recorded one-sentence reason — always exactly one. Consumed cards are never offered. `00-maquette.md` gains `demo_variants`. Sparring: the demo variant(s) seed Q4, variant-only needs become Q1/Q3 hints, other variants become "later scope" lines in §8; the Relation line gives one sentence in §6. D1 wording updated (ID unchanged).

## 0.5.4 — 2026-09-16
Consistency fix: README's "chat tools without folder access" paragraph was a copy-paste of idea's collect-stage text; corrected to state maquette has no chat-only stage — every stage (sparring through build) needs folder access. German-only language aside removed, its content folded into the English text (a customer-variant concern, not the base README's). No contract change.

## 0.5.3 — 2026-09-16
Onboarding: README § For agents, AGENTS.md guard, START fallback names the folder. Director: cold-start question offers the shortlist path; a first message mentioning idea/shortlist/committee asks for the path first (D1' wording, ID unchanged); git `yes` only if the work folder is tracked (a clone counts as no); `examples/` with fictitious finished results (Example GmbH). Brief template: `30-design.md` in the input line, candidates numbered per prefix, resolved questions as a table that keeps OQ numbers (H2/2 note, no contract bump); brief skill wording updated from "retrofit seed / discovery sprint" to "handover to build / build intake". Director: `status: done` bumps revision (§4.4). No contract change.

## 0.5.2 — 2026-09-16
Documentation: prerequisites (browser), chaining from idea and to build by naming the file, profile pointer to skill-suite-setup/PROFILE.md with a minimal example, compatibility line, QUESTIONS.md in the structure, Director description names build and idea, update and uninstall notes. No contract change.

## 0.5.1 — 2026-09-16
RULES §8 profile reading incl. `profile/questions.md`; Director reads it. QUESTIONS.md IDs declared stable.

## 0.5.0 — 2026-09-15
**Contract H2/2:** brief Part 3 gains Guardrails, slices with acceptance criteria and the design choice under Prototype facts. Open questions are `OQ-n` (Q1–Q6 stay the forcing questions). Seed input knows "shortlist entry". Sparring prefills field of application from V4, guardrail candidate from V7, premise from "what would tip it", hints from Views/Dissent. QUESTIONS.md added.

## 0.4.0 — 2026-09-14
Contract H1 intake with idea pick, H2/1 handover, git policy, `planning/` project layout.

## 0.3.0 — 2026-09-12
Screen-by-screen demo walk-through in sparring and plan-board.

## 0.2.0 — 2026-09-09
English source of truth throughout; profile layer reserved.

## 0.1.0 — 2026-09-08
First version: workspace, six stage skills, templates, gstack attribution.
