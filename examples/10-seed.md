---
stage: seed
owner: sparring
status: done
revision: 2
created: 2026-09-08T09:12
updated: 2026-09-08T09:31
input: 00-maquette.md@2
---
<!-- Example — fictitious Example GmbH. Shows what a finished file looks like; not a template. -->

# Seed OFA: Offer draft assistant

_Concept Seed light — result of the sparring stage. Candidate requirements (`cF-` / `cU-` / `cNF-`) are **unratified**: they serve the maquette as guardrails and the later retrofit (Manifest Phase 1) as raw material, not as a specification._

## Input

- **Source:** shortlist entry EXG-001 (planning/idea/10-shortlist.md@3, contract H1/1)
- **Prefilled from the source:** opportunity and minimum success criterion (§1), stakeholders and cost of the status quo (Q1 who, Q2), first stakeholder line (Q3 role), data situation and earlier attempts (§3), personal data and the waiver "maquette without real customer data" (§5), riskiest assumption and cheapest test (§9), the four "open before or during the maquette" lines (§8), committee rationale (§6). Read back in one block; the user confirmed all of it with one correction: "the ~2 h include looking up the right old offer, not only typing."

## Field of application

Internal web app (document assistant): pick a CRM opportunity, get an offer draft. Confirmed.

## 1. Purpose

Sales engineers build every offer by hand: they copy customer and pump data out of the CRM, search the shared drive for an earlier offer of the same pump series and paste its text blocks into Word. The real goal (laddered once): answer customer requests faster without adding people — the Head of Sales wants offer turnaround visibly down before the next budget round. Success: a sales engineer turns a CRM opportunity into a complete, checkable offer draft in minutes, with every value showing where it came from.

## 2. Forcing questions

- **Q1 Demand reality** — The sales engineers, and the customers waiting for quotes. How we can tell: the monthly sales report shows a median of 3 working days from request to sent offer [evidenced]; two key accounts complained about slow quotes in Q2, recorded as CRM notes [evidenced].
- **Q2 Status quo** — Copy data from the CRM, search the shared drive for a similar old offer, paste and adapt in Word: ~2 h per offer including the search, ~15 offers per week across a team of six, so ~30 h per week [estimated].
- **Q3 The specific person** — A sales engineer with three requests in the inbox on a Monday morning: offers go out in the order they arrive, so a large request can wait until Thursday. If it stays unsolved, the backlog grows before every trade fair and quotes go out with values copied from the wrong old offer (happened at least once this year) [estimated].
- **Q4 Smallest demo** — Open one real-looking opportunity and watch the draft assemble itself, with the few fields the CRM lacks clearly marked [estimated].
  → **Scope sentence:** From a list of open opportunities, one click creates an offer draft whose CRM fields are prefilled and tagged by origin, and whose missing fields are flagged for typing.

## 3. Premise check

| Premise | True if … | Rating |
| --- | --- | --- |
| The CRM holds most of the data an offer needs | the export of five real records covers the offer fields (shortlist test) | open |
| Earlier offers are reusable across the same pump series | sales engineers already copy from them today — they say they do | evidenced |
| Earlier offers can be found by pump series | the shared-drive naming allows it; the shortlist says naming is inconsistent | open |
| Engineers trust a prefilled draft if they see each value's origin | the first colleague who uses the maquette checks values instead of retyping them | plausible |

## 4. Shared vocabulary

| Term | Meaning |
| --- | --- |
| Opportunity | A CRM record for a customer request: customer, contact, pump series, quantity, stage |
| Offer draft | The offer before the engineer signs it off; never sent by the tool |
| Offer field | One value the offer needs (e.g. flow rate, head, delivery address); 19 in the standard offer |
| Origin tag | The label next to a value: CRM · earlier offer · typed |
| Missing field | An offer field the CRM record does not provide; must be typed |
| Text block | A reusable paragraph from an earlier offer (scope of supply, technical notes, terms) |
| Pump series | The product family, e.g. P-80; the key for finding earlier offers |

## 5. Guardrails

- **GR-1** — No real customer or contact data in the maquette; mock records only (shortlist waiver W-1).
- **GR-2** — No prices, discounts or margins — pricing stays in the ERP quotation.
- **GR-3** — Every value shows its origin tag; a wrong value must be recognisable as such.
- **GR-4** — The draft is never sent and nothing is written back to the CRM; the engineer stays the author.
- **GR-5** — No CRM connection; the maquette only mirrors the shape of a CRM export.

## 6. Chosen direction and alternatives

The committee picked this idea because the pain is frequent, measurable and the build is small enough to test the CRM assumption early.

- **Chosen:** Workbench — pick an opportunity, CRM fields fill the draft, text blocks from earlier offers of the same pump series are suggested for accept/reject, a preview shows the assembled draft with origin tags. — **because:** it attacks both halves of the 2 h (typing and searching) and keeps the engineer in control of every value.
- **Rejected A:** Free-text generator — the engineer describes the request, an AI writes the whole offer. — **because:** values would not be traceable to a source, and a wrong pump value in an offer is expensive.
- **Rejected B:** Word mail merge from a CRM export — no new tool at all. — **because:** it saves the typing but not the search for old offers, and gives no signal for missing fields; kept as the fallback if the workbench is not approved.

## 7. Candidate requirements (unratified)

### Demo walk-through

| Step | On the screen | The viewer does | Then |
| --- | --- | --- | --- |
| 1 | "Open opportunities": six rows with customer, pump series, quantity, stage | clicks "Create offer draft" on OPP-104 (P-80, 4 pumps) | the workbench opens for OPP-104 |
| 2 | Left column: the 19 offer fields, 16 filled and tagged CRM, 3 amber "not in CRM — please enter" (delivery lead time, pump curve reference, warranty variant) | types the three values | amber turns to "typed" |
| 3 | Right column: three text blocks from earlier P-80 offers, each with offer number and date | accepts two, rejects one | accepted blocks are marked for the draft |
| 4 | "Preview draft" button | clicks it | the full draft appears, every value with its origin tag, and a line "16 from CRM · 3 typed · 2 blocks reused" |

- **Convincing moment:** step 4 — the complete draft on one page, no field blank, origin visible for every value.
- **Non-cases:** empty (no earlier offer for the series): shown — "no earlier offers for this series" · many (hundreds of opportunities): left out · error (CRM field empty in the record): shown — treated like a missing field.
- **Deliberately not shown:** prices, sending the offer, CRM write-back, approval workflow, export to Word.

### Functional
| ID | Requirement |
| --- | --- |
| cF-1 | A list of open opportunities with customer, pump series, quantity and stage |
| cF-2 | Offer fields are prefilled from the selected CRM record, each with an origin tag |
| cF-3 | Offer fields the record does not provide are flagged as missing |
| cF-4 | Text blocks from earlier offers of the same pump series are suggested, with offer number and date |
| cF-5 | A draft preview shows all sections and a count of values by origin |

### User interaction
| ID | Requirement |
| --- | --- |
| cU-1 | One click from an opportunity to its draft workbench |
| cU-2 | Each suggested text block can be accepted or rejected |

### Non-functional
| ID | Requirement |
| --- | --- |
| cNF-1 | In the demo, a draft is assembled in under 10 minutes (today ~2 h) |

## 8. Open questions

- **OQ-1** — From the shortlist: does the CRM export contain every field an offer needs? Not checked with real records yet (see §9).
- **OQ-2** — From the shortlist: where do earlier offers live, and can they be found by pump series? Naming on the shared drive is inconsistent [unknown].
- **OQ-3** — Which text blocks are approved for reuse, and who owns the standard terms?
- **OQ-4** — From the shortlist: data protection for contact names and e-mails taken from the CRM — data protection officer not yet consulted.
- **OQ-5** — Access: sales engineers only, or inside sales as well? (standard concern, internal web app)
- **OQ-6** — Deployment: where would the tool run later? (standard concern)
- **OQ-7** — From the shortlist: which offer layout is binding — the current Word template or a new one?

## 9. Riskiest assumption

- **Assumption:** The CRM export contains every field an offer needs.
- **If wrong:** engineers keep typing half the offer; the saving shrinks from ~2 h to minutes, and the demo promises something the data cannot deliver.
- **Cheapest test:** Export five real opportunity records and map their columns against the 19 offer fields.

## Notes (human)
