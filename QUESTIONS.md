# maquette — Every question the skillset asks a human

**Version 2 (maquette 0.6.0).** One row per question, in the order it is asked. **The IDs are stable identifiers** — `profile/questions.md` (setup skill) refers to them; renumbering is a breaking change. "Prefilled from" names the earlier file that already answers it; with a shortlist entry (contract H1) those rows are read back and confirmed in one block, never re-asked. "—" means the question is this stage's own. Mode column: W = workshop, D = discovery, both if empty.

## Director (`maquette`) — first call only

| # | Question | Prefilled from | Note |
| --- | --- | --- | --- |
| D1 | (with shortlist) H1/2: The committee chose <ID — title> (demo: <variants>) — do we build that one? · H1/1 or no choice: Which one do we build? — entries listed as rank · ID · title · recommendation | `10-shortlist.md` Maquette order | exactly one; a deviation from the committee's choice gets a one-sentence reason |
| D1' | (cold start) What do we start from — an idea in two sentences, an idea card, a concept sketch — or, if you come from idea, the path to your shortlist file? | — | if the first message mentions idea / shortlist / committee, the path is asked first |
| D2 | Code (2–4 letters) and working title — proposed, user corrects | shortlist entry ID / title | |
| D3 | Mode: the committee suggested <mode> — fine? / Workshop or discovery? | shortlist "Recommended mode" | default workshop |
| D4 | Git: is the folder a repository? | checked silently, result told | never `git init`; a clone of the public repo counts as no |
| D5 | Language of the result files? | profile → chat language → explicit statement | |

Every later call: one question at most — "Good as it is — next, or redo?" after a stage; the gate and conflict questions listed under the stages.

## Stage 1 — sparring

| # | Question | Mode | Prefilled from (H1 entry / card) | Seed section |
| --- | --- | --- | --- | --- |
| S0 | From the shortlist I take the following — tell me where it no longer holds. (one block) | | Opportunity, Min. success criterion → §1 · Stakeholders, Cost → Q1 · Process, Cost → Q2 · Stakeholders first line → Q3 · Min. success criterion → Q4 start · Data situation, Earlier attempts → §3 · Personal data, Legal, waivers → §5 · Riskiest assumption, V10 → §9 · unknowns, waivers → §8 · Committee rationale → §6 | all |
| S1 | Is this the problem in one sentence: …? | | Opportunity | §1 |
| S2 | Why does this matter right now? (ladder up once) | | — | §1 |
| S3 | Field of application — is it <proposal>? | | V4, Process & systems (confirmed, not guessed) | Field |
| Q1 | Who would be noticeably affected if this did not exist tomorrow — and how can you tell? | | who: prefilled; **how can you tell: own** | §2 Q1 |
| Q2 | What do they do today instead, and what does it cost (frequency × effort)? | | prefilled; confirmed | §2 Q2 |
| Q3 | Who exactly needs this most — role, situation, consequence if unsolved? | | role: prefilled; **situation, consequence: own** | §2 Q3 |
| Q4 | What is the smallest demo that makes your sponsor say yes? → scope sentence | | starting point only; **the decision is own** | §2 Q4 |
| Q5 | Have you watched someone do today's workaround — what surprised you? | D | — | §2 |
| Q6 | In three years, does this get more important or less? | D | — | §2 |
| S4 | What would have to be true for this problem to exist at all — and for this direction to hold? (2–4 premises, rated) | | Data situation, Earlier attempts | §3 |
| S5 | Three directions — which one do we take, and why? (hard stop) | | — | §6 |
| W1 | The sponsor sits in front of the maquette — what is the first thing on the screen? (objects and data by name) | | — | §7 walk-through |
| W2 | What does the sponsor do next — click, type, choose — and what appears then? (2–4 steps) | | — | §7 |
| W3 | Which step is the one that convinces — what must be visible there, exactly? | | — | §7 |
| W4 | What happens when there is nothing yet / far too much / something goes wrong — shown or left out? | | — | §7 non-cases → 20-plan §7 |
| W5 | What must the maquette deliberately not show? | | — | §7, §5 |
| S6 | Here are the candidates — anything missing the sponsor would look for, or anything you would not build? | | — | §7 table |
| S7 | The maquette has been shown and did not convince — why? → riskiest assumption; and the cheapest test? | | Riskiest assumption, V10 (confirmed) | §9 |
| S8 | Read-back in six lines — approved? | | — | write |

With a complete H1 entry sparring asks **3 own questions of substance** (Q1 evidence, Q3 situation, Q4 demo) plus the walk-through W1–W5 and the direction S5, which are decisions about the maquette, not facts about the idea (WP0 finding).

## Stage 2 — plan-board

| # | Question | Mode | Source | Plan section |
| --- | --- | --- | --- | --- |
| P1 | Per walk-through step: is this still the flow — what is missing between here and the next step? | W 10 min / D 30 min | 10-seed §7 | §3–§5 |
| P2 | Per candidate: testable? does the maquette need it? | | 10-seed §7 | §3–§5 |
| P3 | Job to be done — the one sentence why someone opens this page? | | — | §1, cU rows |
| P4 | Per slice: empty · many · error · slow — shown, or out of scope? | | 10-seed §7 non-cases | §7 |
| P5 | Open questions from the seed — one-liners where you can? | | 10-seed §8 | §8 / §11 |
| P6 | Field standard concerns: data source and licence, where it runs, any real personal data? | | 10-seed field, §5 | guardrails |
| F1 | Product fork (at most one), e.g. live data with loading time, or a frozen dataset with a date? | | — | §9 |
| F2 | Design fork (at most one), e.g. projector or own laptop? | | profile design rules decided here | §9 |
| F3 | Engineering fork (at most one), e.g. live fetch or a file in the folder? | | profile IT constraints are hard limits | §9 |
| P7 | Acceptance criteria per slice — read back one by one: right? | | — | §10 |
| P8 | Do you approve the plan — yes, with changes, or redo? (gate) | W 1 round / D 2 | — | §12 |

## Stage 3 — design-3 (skippable)

| # | Question | Source | Section |
| --- | --- | --- | --- |
| G1 | Existing constraints — corporate design, prohibitions, reference tools? | profile design.md if present | §1 |
| G2 | What must the viewer see in the first three seconds? (only if the flow line leaves it open) | 20-plan §10 | §1 |
| G3 | Which one do we take — A, B, C, or a mix — and why? (one extra round allowed) | — | §3 |

## Stage 4 — build

| # | Question | When |
| --- | --- | --- |
| B1 | Something must be installed: here is the exact command — go ahead? | only if the plan names an install |
| B2 | Slice S<n> is clickable here — next, or a correction? | after every slice |
| B3 | This slice cannot be built as planned — smallest cut is …, agreed? | on deviation |
| B4 | Budget reached after S3 — continue with S4, or close? | W after S3 |

## Stage 5 — harden (skippable)

| # | Question | When |
| --- | --- | --- |
| H1 | I would fix these findings (table shown, by severity) — agreed, or strike something? | once, before fixing |
| H2 | This fix touches more than three files — continue? | on that fix |

## Stage 6 — brief

| # | Question | Source | Brief part |
| --- | --- | --- | --- |
| R1 | Who presents, and to whom? | — | Part 1 tone |
| R2 | Q5 — Has anyone used the maquette without your help yet — what surprised you? | — | Part 3 observation |
| R3 | Who decides, and by when? | sponsor from 00-maquette.md (confirmed) | Part 4 |

Everything else in the brief is drafted from the six files and read back once — no interview.

## What maquette hands over and never asks again

`60-brief.md` (contract H2/2) carries the field of application, the guardrails, the candidate requirements with their maquette status, the shared vocabulary, decided and open questions, the riskiest assumption with what the maquette showed, and the prototype facts for reading `vcode/`. build's intake extracts these (Path B) and asks only for what the maquette did not show — see `build/QUESTIONS.md`.
