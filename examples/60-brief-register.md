---
stage: brief
owner: brief
status: done
revision: 2
created: 2026-10-14T19:08
updated: 2026-10-14T19:10
input: 10-seed.md@2, 20-plan.v2.md@2, 40-build.md@2
contract: H2/3
---
<!-- Example — fictitious Example GmbH (test run-04, focus track). A brief started from a register (contract_in: register/1), written as H2/3. Not a template. -->

# Brief EXF: Service report assistant

_Result of the brief stage and exit point of the maquette. Part 1 is for the presentation, Part 2 for the decision afterwards, Part 3 is **contract H2** — the handover to build. Build intake reads Part 3 and `vcode/` (read-only) and runs Path B (extract what the prototype already answers) before Path A (grill what it does not); with a register it also traces every R-ID (Path R)._

## Part 1 — Demo script (3 minutes)

Presented by the Head of Service to the managing director (answer to "who presents, and to whom?").

- **The problem in one sentence:** Our technicians type every service report at night — 25 minutes each, 40 a day — and customers still get them days late and in different shapes.
- **For whom:** the field service technician with five to six visits a day who types reports at the kitchen table at 9 pm.
- **Click path:**
  1. Open the folder `vcode` and double-click `index.html` — a phone screen appears: "My visits today", three sample visits.
  2. Tap "Lindenstraße 12 — WP-12" — the draft on form QM-F-12: findings, parts used, measurements, next maintenance; each value with the line from the voice note it came from. Say: "Nobody typed this."
  3. Point at the red outlet temperature "55 °C — not in voice note". Say: "The AI made this up — and the technician sees it at once." "Approve and send" is grey.
  4. Type "48 °C", tap "Correct" — the flag turns green, "Approve and send" becomes active; the timer shows well under five minutes.
  5. Tap "Approve and send" — "sent", with the log line "approved by J. Huber, time, version 1". Say: "Nothing leaves without the technician."
  6. Back to the list: "Am Hang 3 — recorded offline". Tap "Simulate connection" — the draft is ready; nothing was lost in the basement.
- **The moment that matters:** step 3 — the invented value stands out in red and blocks sending until the technician corrects it.
- **What not to click:** there is no dispatch view; parts have no correction field; reloading the page resets the demo (quality check skipped — taken from the build log's known gaps).

## Part 2 — Can / deliberately cannot

| Can | Deliberately cannot | Why not |
| --- | --- | --- |
| Show a scripted draft on QM-F-12 with all four parts | Generate a draft from a real voice note (no AI, no speech-to-text) | scope |
| Flag every measurement that is not in the voice note and block approval until corrected | Measure real checking time of real technicians | data |
| Approve and send only by the named technician, with a log line | Actually send an e-mail or write to the ERP | scope |
| Show an offline voice note becoming a draft | Show upload failures or many visits | scope |
| Label the voice note "deleted after transcription" | Prove EU hosting, deletion, cost cap or SSO (R-14, R-15, R-16, R-17, R-18) | decision pending |
| — | Show the dispatch 24-hour list (R-9) | time |

**What this maquette proves:** the check-and-approve flow on the phone can make an invented value impossible to overlook and keeps the technician's final word.
**What it does not prove:** that real speech-to-text and AI drafts are good enough, that technicians actually catch misheard values within five minutes, or that the EU and deletion condition can be met — all of that is still open.

## Part 3 — Handover to build

### Field of application

Mobile web app for field service technicians (draft generation from voice notes, approval on the phone), plus a small dispatch view in the browser.

### Register and coverage

- **Register:** ../../idea/10-register.v2.md@2 · contract register/1 · **outcome:** go-with-conditions · **complete:** yes — round 2: the IT lead's answers to the partial register `10-register.md@2`; changes by decision only, every R-number kept. Changes: R-16 SHOULD → MUST (IT lead: no app on company devices without single sign-on); R-19 new (MUST, origin review); R-6 COULD → out of scope (won't); V6 yellow → green
- **K.o. decisions:**
  - **V8 · R-14, R-15:** pass with condition: voice notes are processed only by EU-hosted services under a data processing agreement and deleted right after transcription; customer data is kept only in the ERP → R-18 (MUST, origin review) — confirmed by the IT lead in round 2
  - **V8 · R-13:** unknown — estimated [estimated, Head of Service]: resolvable by a change of the documentation procedure; QM lead to confirm → open question 1 (unchanged)
  - **V3:** pass — round 2: IT lead confirms ERP read access to parts and stock bookings via the existing ERP interface
  - **V6:** pass — round 2: operating model settled (IT operates integration and SSO, EU provider runs speech-to-text / LLM); running cost capped (R-17)
  - **V8 · round 2 (IT lead):** pass with condition: every sent service report is traceable — who approved it, when, which version → R-19 (MUST, origin review)
- **Users and scale (frame):** Internal team: 18 field service technicians and 4 dispatch / back-office staff. About 40 reports per day; peaks in the heating season October–February. Used during office hours plus evenings; an outage of a few hours is tolerable as long as voice notes are not lost. Depends on the ERP (report data, parts and stock bookings) and an external speech-to-text / LLM provider. [estimated]
- **V5 and V6 notes (upkeep, operation, running cost):** green — corrected in round 2 (yellow → green): IT lead — IT operates the ERP integration and SSO, the provider runs speech-to-text / LLM in the EU under a contract; effort class 10–50k; running cost per report far below value per report, capped by R-17.
- **Register versions:** started on 10-register.md@2; taken over 10-register.v2.md@2 (coverage redo, 20-plan.v2.md)
- **Newer register not taken over:** —

| Item | Priority | Type | Statement | Perspectives | Sources | Measure | Touchpoint | Origin | Coverage | Slice · requirements | Reason |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| R-2 | MUST | goal | Checking a drafted service report takes the technician no more than 5 minutes. | SRV | EXF-C002 | ≤ 5 min from opening the draft to approval | — | contribution | faked | S1 · cU-1, cNF-2 | timer runs on a scripted draft; real checking time only in the cheapest test |
| R-3 | MUST | constraint | Works offline in basements and plant rooms; the voice note is uploaded later. | SRV | EXF-C003 | No voice note lost when recorded without connection | — | contribution | faked | S2 · cF-4, cF-9 | reconnection is scripted |
| R-4 | MUST | constraint | A service report is sent only after the approval of the named technician (conflict decided: view A). | SRV, QM, DSP | EXF-C004, EXF-C016, EXF-C011 | — | — | contribution | shown | S1 · cU-2 | — |
| R-5 | MUST | requirement | The draft contains the findings, the parts used, the measurements and the next maintenance date. | SRV | EXF-C005 | All four parts filled in every draft | — | contribution | faked | S1 · cF-1 | draft content scripted, no AI |
| R-7 | MUST | concern | The AI invents a measurement that was never dictated, and the technician misses it when checking. | SRV | EXF-C007 | No value in the report that is not in the voice note | — | contribution | shown | S1 · cF-2, cF-8 | flag computed in the page against the transcript |
| R-12 | MUST | constraint | Every service report uses the standard QM report template and the fault code list, so every customer gets the same layout regardless of the technician. | DSP, QM | EXF-C014, EXF-C015 | Every report on template QM-F-12 with valid fault codes | — | contribution | faked | S1 · cF-1 | layout imitated, sample fault codes |
| R-14 | MUST | constraint | Voice notes contain customer names and addresses (personal data) and must not leave the EU. | IT | EXF-C019 | — | — | contribution | not shown (later) | — | not demonstrable in a model; no real data (GR-2); waits for OQ-4 |
| R-15 | MUST | constraint | Voice notes are deleted right after transcription. | IT | EXF-C020 | No recording older than the transcription job | — | contribution | faked | S1 · cF-5 | label only; nothing is recorded |
| R-16 | MUST | constraint | Access only via single sign-on with the company accounts. | IT | EXF-C021 | — | — | contribution | not shown (later) | — | no accounts in a maquette; OQ-7 |
| R-17 | MUST | constraint | A monthly cap on AI cost, with an alert before the cap is reached. | IT | EXF-C022 | Monthly AI cost ≤ agreed cap; alert at 80 % | — | contribution | not shown (later) | — | operation topic; no AI calls in the model |
| R-18 | MUST | constraint | Voice notes are processed only by EU-hosted services under a data processing agreement and deleted right after transcription; customer data is kept only in the ERP. | IT, QM | — (K.o. decision V8 on R-14, R-15) | Provider contract names EU hosting and deletion on completion | — | review | not shown (later) | — | contract condition, not demonstrable; GR-1; waits for OQ-4 |
| R-19 | MUST | requirement | Every sent service report is logged: who approved it, when, and which version was sent; the log is kept with the ERP record. | IT, QM | — (round 2, IT lead) | Every sent report has an audit log entry | — | review | faked | S1 · cF-7 | log line on the sent screen, nothing stored |
| R-9 | SHOULD | goal | The service report reaches the customer within 24 hours of the visit. | DSP | EXF-C010 | ≥ 90 % of reports sent within 24 h | — | contribution | not shown (later) | — | slice S3 not built (planned faked, cF-6) |
| R-10 | SHOULD | requirement | The parts used in the service report match the stock booking in the ERP. | DSP | EXF-C012 | 0 differences between report and ERP booking | — | contribution | not shown (later) | — | needs real ERP (access confirmed in register v2) |
| R-1 | COULD | concern | Service reports are typed after hours (~25 min each) and reach customers three to five days after the visit; dispatch spends about an hour a day on the resulting calls. | SRV, DSP | EXF-C001, EXF-C009 | ~25 min per report; 3–5 days delay; ~1 h/day dispatch time | — | contribution | not shown (later) | — | status-quo pain; told in the demo script, measured in the cheapest test |
| R-8 | COULD | question | Who is liable if a customer disputes what an AI-drafted service report says? | SRV | EXF-C008 | — | — | contribution | not shown (later) | — | waits for OQ-2 |
| R-13 | COULD | question | Is an AI-drafted service report acceptable under the ISO 9001 documentation procedure, and who signs off the procedure change? | QM | EXF-C017 | — | — | contribution | not shown (later) | — | waits for OQ-1 |
| R-6 | — | wish | Photos (type plate, damage) can be attached to the service report. | SRV | EXF-C006 | — | — | contribution | out | — | register v2 Out of scope: won't (round 2) — photos add personal data and storage questions beyond condition R-18; revisit after the first release |
| R-11 | — | wish | Customers can also see their service reports in a customer portal. | DSP | EXF-C013 | — | — | contribution | out | — | register Out of scope: won't — no customer portal today; e-mail delivery covers R-9 |
| R-M1 | SHOULD (proposed) | requirement | The technician sees today's visits with the report status of each. | SRV | maquette walk-through (cF-3) | — | — | maquette | shown | S1 · cF-3 | new from the walk-through |
| R-M2 | SHOULD (proposed) | requirement | Approval stays blocked while a value is flagged and uncorrected. | SRV, QM | build log cF-new-1 | No report sent with an uncorrected flagged value | — | maquette | shown | S1 · cF-8 | found while building; block vs. warn is OQ-9 |

**Count:** register items 19 · rows 21 · MUST 12, each with explicit status · new items 2 (R-M1, R-M2)

### Updated candidate requirements

| ID | Requirement | Origin | Status in maquette | Register |
| --- | --- | --- | --- | --- |
| cF-1 | The draft shows the four parts findings, parts used, measurements, next maintenance date on the QM-F-12 layout with valid fault codes. | seed | shown | R-5, R-12 |
| cF-2 | Every measurement and part shows the voice-note passage it came from; a value without a passage is flagged "not in voice note". | seed | shown | R-7 |
| cF-3 | "My visits today" lists the technician's visits with the report status of each. | seed | shown | R-M1 |
| cF-4 | A voice note recorded without connection shows "recorded offline — will upload" and becomes a draft once uploaded. | seed | shown | R-3 |
| cF-5 | Once the draft exists, the voice note shows "deleted after transcription"; only the transcript remains. | plan | partial | R-15 |
| cF-6 | Dispatch sees every draft not approved 24 h after the visit, with technician and visit, and can send a reminder. | plan | not shown | R-9 |
| cF-7 | After approval the sent report shows its log line: approved by the named technician, date and time, version sent. | plan | partial | R-19 |
| cF-8 | "Approve and send" stays disabled while a measurement is flagged and uncorrected. | build | shown | R-M2 |
| cF-9 | Tapping a visit recorded offline explains that the voice note is safe on the phone and uploads later. | build | shown | R-3 |
| cU-1 | The technician corrects a flagged value inline in the draft. | seed | partial | R-2 |
| cU-2 | "Approve and send" is the only way a report leaves; it records the named technician. | seed | shown | R-4 |
| cNF-1 | Only fictitious sample data, visibly labelled "sample data". | seed | shown | model only |
| cNF-2 | A timer shows the time from opening the draft to approval (target ≤ 5 min). | seed | shown | R-2 |

### Guardrails

- **GR-1** — Voice notes are processed only by EU-hosted services under a data processing agreement and deleted right after transcription; customer data is kept only in the ERP. (R-18) — origin: seed
- **GR-2** — No real personal data in the maquette: all customers, addresses and voice notes are fictitious and labelled "sample data" (R-14). — origin: seed
- **GR-3** — A wrong result must be visible as such: any value that is not in the voice note is flagged, never shown as plain fact (V7, R-7). — origin: seed
- **GR-4** — A service report is sent only after the approval of the named technician; no automatic sending, not even after 24 h (R-4). — origin: seed
- **GR-5** — Every draft uses the layout of template QM-F-12 and valid fault codes (R-12). — origin: seed
- **GR-6** — The voice note must not be lost when recorded without connection (R-3) — the maquette must not suggest otherwise. — origin: seed
- **GR-7** — Running AI cost is capped monthly with an alert (R-17) — product constraint; the maquette makes no AI calls. — origin: seed
- **GR-8** — Not shown: no real AI or speech-to-text call, no ERP connection, no e-mail actually sent — so nobody mistakes the model for the product. — origin: seed
- **GR-9** — Access only via single sign-on with the company accounts (R-16, MUST since register v2). — origin: plan
- **GR-10** — Every sent service report is logged: who approved it, when, which version (R-19, K.o. condition V8 round 2). — origin: plan

### Shared vocabulary

| Term | Meaning |
| --- | --- |
| service report | the report the customer receives after a heat-pump service visit (also: report, visit report, customer report) |
| voice note | the technician's short dictation after the visit (also: dictation, recording) |
| draft | the AI-written service report before approval |
| approval | the named technician's check and release; only after it is the report sent (also: check, release) |
| parts used | parts fitted during the visit (also: material, spare parts) |
| QM-F-12 | the standard QM report template |
| flagged value | a value in the draft that does not occur in the voice note |
| waiting > 24 h | a draft not approved 24 hours after the visit; dispatch reminds the technician |
| voice note deleted | the label shown once the transcript exists; only the transcript remains |
| log line | approved by, date and time, version sent — shown on every sent report |

### Resolved questions

| OQ | Question | Decision | Decided where |
| --- | --- | --- | --- |
| OQ-3 | Who operates the provider and ERP integration, and is ERP read access available? | IT operates integration and SSO; ERP read access via the existing interface (register v2) | plan-board |
| OQ-5 | How does dispatch learn about reports still waiting for approval after 24 h? | A "waiting > 24 h" list with a reminder button; never automatic sending (not built — S3 dropped) | plan-board |
| OQ-6 | Committee incomplete — IT lead's answers follow as 10-register.v2.md. | arrived and taken over (10-register.v2.md@2) | plan-board |
| OQ-7 | (maquette part) Where does the model run? | phone-sized page in the laptop browser; product part stays open | plan-board |

### Open questions

- **OQ-1** — Is an AI-drafted service report acceptable under the ISO 9001 documentation procedure, and who signs off the procedure change? (QM lead)
- **OQ-2** — Who is liable if a customer disputes an AI-drafted service report? (Head of Service with legal)
- **OQ-4** — Verify condition R-18 in the provider contract (EU hosting, data processing agreement, deletion on completion) before real customer voice notes are used. (IT lead, data protection officer)
- **OQ-7** — (product part) How do technicians reach the app on their phones (browser, MDM), and where does it run? SSO is MUST (R-16).
- **OQ-8** — Premise P1: does speech-to-text cope with dialect and technical terms recorded in plant rooms?
- **OQ-9** — Should approval be blocked while a value is flagged (R-M2), or only warned? The maquette blocks.

### Riskiest assumption — state after the maquette

- **Assumption (from 10-seed.md §9):** Technicians can reliably spot an invented or misheard value within 5 minutes of checking (R-2, R-7).
- **What the maquette showed:** weakened risk for *invented* values (a value absent from the voice note can be flagged mechanically); untouched for *misheard* values — a value that is in the transcript but wrong is not flagged.
- **Q5 Observation:** not yet observed: next test — 20 real voice notes from last week, drafted and checked by two technicians (checking time, invented and misheard values found vs. missed).

### Prototype facts (for Path B)

- **Stack and entry point:** one static `vcode/index.html`, inline CSS and JS, no build, no server, no network; start by double-click.
- **Real vs. faked:** real — flag logic (a value is flagged when its key does not occur in the transcript), approval block, timer, status changes in the session · faked — transcripts and drafts (scripted, no AI), reconnection (button), "voice note deleted" label, approval log line (not stored), sending (no e-mail).
- **Data:** synthetic sample data inline in `index.html` (three visits, two transcripts, two drafts), described in `vcode/data/SOURCE.md`, dated 2026-10-14; no real personal data.
- **Slices built and acceptance criteria:** S1 check and approve one draft — passed · S2 offline voice note — passed · S3 dispatch 24-hour list — dropped (not built).
- **Design:** skipped, plain style (design stage skipped: one phone screen, the plan's design decisions suffice).
- **Shortcuts taken:** quality check skipped — no harden pass; state is lost on reload; only measurements are correctable.
- **Worth keeping:** the flag rule "value not in transcript → flagged, approval blocked" as an acceptance test idea; the sample transcripts as test data.
- **Not worth keeping:** the page itself — rebuild from concept.

## Part 4 — Next step

- **Recommendation:** test the riskiest assumption first — 20 real voice notes drafted and checked by two technicians — because the maquette shows invented values can be caught, but not that misheard values are; build intake follows if the test holds.
- **Who decides:** Head of Service (sponsor)
- **When:** 2026-11-12 (register decision date, confirmed)

## Notes (human)

<!-- Off limits for all skills. Copied verbatim on every rewrite. -->
