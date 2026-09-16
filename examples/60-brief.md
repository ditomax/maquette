---
stage: brief
owner: brief
status: done
revision: 2
created: 2026-09-10T14:05
updated: 2026-09-10T14:24
input: 10-seed.md@2, 20-plan.md@2, 30-design.md@2, 40-build.md@3, 50-harden.md@2
contract: H2/2
---
<!-- Example — fictitious Example GmbH. Shows what a finished file looks like; not a template. -->

# Brief OFA: Offer draft assistant

_Result of the brief stage and exit point of the maquette. Part 1 is for the presentation, Part 2 for the decision afterwards, Part 3 is **contract H2** — the handover to build. Build intake reads Part 3 and `vcode/` (read-only) and runs Path B (extract what the prototype already answers) before Path A (grill what it does not)._

## Part 1 — Demo script (3 minutes)

- **The problem in one sentence:** "Our engineers spend two hours per offer copying data and hunting for old offers, so customers wait three days for a quote."
- **For whom:** a sales engineer with three requests in the inbox on a Monday morning.
- **Click path:**
  1. Open `vcode/index.html` in Chrome or Edge, window at least 1024 px wide.
  2. "Open opportunities" — six requests. Say: "This is Monday morning." Click "Create offer draft" on OPP-104.
  3. Workbench — left, 16 values already filled, each tagged CRM; three amber fields. Say: "These three are not in the CRM today — the tool says so instead of guessing." Type any lead time, curve reference and warranty variant.
  4. Right, three paragraphs from earlier P-80 offers with offer number and date. Accept two, reject one. Say: "No more searching the shared drive."
  5. Click "Preview draft" — the whole offer, every value tagged, "16 from CRM · 3 typed · 2 blocks reused".
  6. Optional: back to the list, open OPP-109 — "no earlier offers for this series" shows the honest empty case.
- **The moment that matters:** step 5 — a complete draft in a few minutes, and you can see where every value came from.
- **What not to click:** "Export to Word" (disabled on purpose); browser reload (everything typed is lost); the browser's print dialog (page breaks are not handled).

## Part 2 — Can / deliberately cannot

| Can | Deliberately cannot | Why not |
| --- | --- | --- |
| List open opportunities and open a draft in one click | Connect to the real CRM or read real records | data |
| Prefill 16 of 19 offer fields with origin tags | Show or calculate prices, discounts, margins | scope |
| Flag missing fields and accept typed values | Save a draft — everything is gone on reload | time |
| Suggest text blocks from earlier offers of the same series | Find blocks by similarity; the lookup is a fixed list per series | decision pending |
| Preview the assembled draft with an origin count | Export to Word or send the offer | decision pending |
| Show the "no earlier offers" case | Handle hundreds of opportunities, search or filter | scope |

**What this maquette proves:** a draft assembled from CRM values and reused text blocks, with visible origins, is understandable to a sales engineer without explanation.
**What it does not prove:** that the real CRM export and the shared-drive offers deliver this data — all records are invented, and three of 19 fields already have no CRM column.

## Part 3 — Handover to build

### Field of application

Internal web app (document assistant) for sales engineers: CRM opportunity in, offer draft out.

### Updated candidate requirements

| ID | Requirement | Origin | Status in maquette |
| --- | --- | --- | --- |
| cF-1 | A list of open opportunities with customer, pump series, quantity and stage | seed | shown |
| cF-2 | Offer fields are prefilled from the selected CRM record, each with an origin tag | seed | shown |
| cF-3 | Offer fields the record does not provide, or provides empty, are flagged as missing | seed | shown |
| cF-4 | Text blocks from earlier offers of the same pump series are suggested | seed | partial |
| cF-5 | A draft preview shows all sections and a count of values by origin | seed | shown |
| cF-6 | Each suggested block shows the earlier offer's number and date | plan | shown |
| cF-7 | The draft can be exported as a Word document based on the binding offer layout | plan | not shown |
| cF-8 | Flow rates from earlier offers in l/s are converted to m³/h before reuse | build | partial |
| cU-1 | One click from an opportunity to its draft workbench | seed | shown |
| cU-2 | Each suggested text block can be accepted or rejected | seed | shown |
| cU-3 | Preview is enabled only when no missing field is left empty | plan | shown |
| cNF-1 | A draft is assembled in under 10 minutes (today ~2 h) | seed | partial |
| cNF-2 | The preview prints on A4 without cut-off sections | build | partial |
| cNF-3 | Missing-field markers are readable without colour (icon and text) | harden | shown |

### Guardrails

- **GR-1** — No real customer or contact data in the maquette; mock records only (shortlist waiver W-1). — seed
- **GR-2** — No prices, discounts or margins — pricing stays in the ERP quotation. — seed
- **GR-3** — Every value shows its origin tag; a wrong value must be recognisable as such. — seed
- **GR-4** — The draft is never sent and nothing is written back to the CRM; the engineer stays the author. — seed
- **GR-5** — No CRM connection; the maquette only mirrors the shape of a CRM export. — seed
- **GR-6** — Runs from files in the folder: no server, no install, no external network calls. — plan
- **GR-7** — Text blocks are suggested only from offers of the same pump series, never across series. — build

### Shared vocabulary

| Term | Meaning |
| --- | --- |
| Opportunity | A CRM record for a customer request: customer, contact, pump series, quantity, stage |
| Offer draft | The offer before the engineer signs it off; never sent by the tool |
| Offer field | One value the offer needs; 19 in the standard offer, listed in `vcode/data/data.js` |
| Origin tag | The label next to a value: CRM · earlier offer · typed |
| Missing field | An offer field the CRM record does not provide, or provides empty; must be typed |
| Text block | A reusable paragraph from an earlier offer (scope of supply, technical notes, terms) |
| Pump series | The product family, e.g. P-80; the key for finding earlier offers |
| Workbench | The two-column screen: offer fields left, text blocks right |
| Origin count | The line "n from CRM · n typed · n blocks reused" in the preview |

### Resolved questions

| OQ | Question | Decision | Decided where |
| --- | --- | --- | --- |
| OQ-2 | Where do earlier offers live, and can they be found by pump series? | For the maquette: nine mock earlier offers, three per series; real search out of scope — the drive structure is unknown, the demo only needs the pattern | plan-board |
| OQ-7 | Which offer layout is binding — the current Word template or a new one? | For the maquette: a neutral layout; the binding template is decided with the export (cF-7) — layout is not the benefit being shown | plan-board |
| — (plan fork F1) | Live data or frozen mock data? | Frozen mock data dated 2026-09-01 (GR-1, GR-5) | plan-board |
| — (plan fork F3) | Data source of the prototype? | One file `vcode/data/data.js`, no fetch (GR-6; opens from disk without a server) | plan-board |

### Open questions

- **OQ-1** — Does the CRM export contain every field an offer needs? Partly answered: see riskiest assumption; five-record test still to run.
- **OQ-3** — Which text blocks are approved for reuse, and who owns the standard terms?
- **OQ-4** — Data protection for contact names and e-mails taken from the CRM — data protection officer not yet consulted (shortlist waiver W-1).
- **OQ-5** — Access: sales engineers only, or inside sales as well?
- **OQ-6** — Deployment: where would the tool run later?
- **OQ-8** — Should the draft contain a price section filled from the ERP, or a placeholder the engineer fills?
- **OQ-9** — Is a Word document required for the customer, or is PDF enough? (decides cF-7)
- **OQ-10** — Delivery lead time, pump curve reference and warranty variant have no CRM column: maintained elsewhere, or typed every time? (duplicate of part of OQ-1, kept for traceability)
- **OQ-11** — Earlier offers mix m³/h and l/s; which unit is the standard, and are other units (head in m vs. bar) also mixed?

### Riskiest assumption — state after the maquette

- **Assumption (from 10-seed.md §9):** The CRM export contains every field an offer needs.
- **What the maquette showed:** weakened — building the field list against the CRM export's header row (column names only, no records) left 3 of 19 offer fields without a CRM column [evidenced]; whether the other 16 are actually filled in real records is untested.
- **Q5 Observation:** A second sales engineer used the maquette on 2026-09-09 without help and reached the preview in 7 minutes [evidenced]. Surprise: she ignored the origin tags at first and asked "which of these did I type?" only in the preview — the origin count was what she read.

### Prototype facts (for Path B)

- **Stack and entry point:** plain HTML + JavaScript, no framework, no build step, no install; open `vcode/index.html` in a current browser. Files: `index.html`, `app.js`, `styles.css`, `data/data.js`.
- **Real vs. faked:**
  - Navigation and draft state: real, in memory only; lost on reload.
  - Prefill: real mapping logic from mock record columns to the 19 offer fields.
  - Missing-field detection: real, compares each record against the field list.
  - Block suggestion: scripted, a fixed list of blocks per pump series; no ranking or search.
  - Unit conversion: real for l/s → m³/h only.
  - Preview: real HTML render of the draft; origin count computed.
  - Export to Word: faked, disabled button with a note.
- **Data:** all mock, frozen 2026-09-01, in `vcode/data/data.js`: 6 opportunities, 4 invented customers, 9 earlier offers (3 series × 3), 12 text blocks, the 19-field offer list with its source mapping. Column names follow the real CRM export header row provided by the sponsor [evidenced]; no real values.
- **Slices built and acceptance criteria:**
  - S1 opportunity → prefilled workbench: "Create offer draft on OPP-104 shows 16 fields tagged CRM and 3 flagged as missing" — passed.
  - S2 text-block suggestions: "OPP-104 shows three P-80 blocks with offer number and date; accepting two marks exactly those two for the draft" — passed.
  - S3 preview: "With the three missing fields filled, Preview shows all sections and '16 from CRM · 3 typed · 2 blocks reused'; Export stays disabled" — passed.
- **Design:** variant B "two-column workbench" (over A wizard and C single long form) — the sponsor wanted CRM values and reused blocks visible side by side; tokens in `30-design.md` §4.
- **Shortcuts taken:** no persistence; minimum width 1024 px, no mobile layout; print page breaks not handled (cNF-2); validation only "not empty"; keyboard focus order not checked; the harden fix budget (5, no git) was used for colour-independent markers, two layout overlaps and one wrong origin tag.
- **Worth keeping:** the 19-field list and its source mapping in `data/data.js` as the starting point for the data model; the origin-tag and origin-count pattern.
- **Not worth keeping:** `app.js` state handling, the scripted block lookup, the mock records themselves.

## Part 4 — Next step

- **Recommendation:** test the riskiest assumption first — export five real opportunity records and map them against the 19 offer fields (about one day with sales ops), then start build intake with this brief. The maquette convinced a first user, but its biggest promise rests on data nobody has looked at yet.
- **Who decides:** Head of Sales
- **When:** sales leadership meeting on 2026-09-17

## Notes (human)
