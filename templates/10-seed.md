---
stage: seed
owner: sparring
status: in_progress          # open | in_progress | done | skipped
revision: 1
created: <YYYY-MM-DDThh:mm>
updated: <YYYY-MM-DDThh:mm>
input: 00-maquette.md@1      # starting point; with an idea card / concept sketch also its ID under "Input"
---

# Seed <code>: <title>

_Concept Seed light — result of the sparring stage. Candidate requirements (`cF-` / `cU-` / `cNF-`) are **unratified**: they serve the maquette as guardrails and the later retrofit (Manifest Phase 1) as raw material, not as a specification._

## Input

- **Source:** <idea in two sentences | idea card <ID> | concept sketch <ID>-K>
- **Prefilled from the source:** <which fields were taken over and confirmed by the user, or "none — cold start">

## Field of application

<one line, e.g. "internal web app" / "dashboard on public data" / "document assistant">
<!-- Confirmed by the user. Determines the standard concerns that must appear as open questions (web → data protection, access, deployment). -->

## 1. Purpose

<the framed problem and the real goal behind it (laddering: "why does this matter?"). What success looks like.>

## 2. Forcing questions

<!-- From gstack office-hours (© 2026 Garry Tan, MIT License, see `LICENSES/gstack-MIT.txt`), placed per concept §5. Every answer carries an evidence mark [evidenced|estimated|unknown].
     Q2 and Q3 are prefilled from an idea card if one exists and only confirmed. Q5 and Q6 are deliberately NOT here (Q5 → 60-brief, Q6 → discovery mode only). -->

- **Q1 Demand reality** — Who would be noticeably affected if this solution did not exist tomorrow, and how can you tell? <…> [evidenced|estimated|unknown]
- **Q2 Status quo** — What do the affected people do today instead, and what does that workaround cost (frequency × effort)? <…> [evidenced|estimated|unknown]
- **Q3 The specific person** — Who exactly needs this most: role, situation, consequence if it stays unsolved? <…> [evidenced|estimated|unknown]
- **Q4 Smallest demo** — What is the smallest version that makes the sponsor say yes? <…> [evidenced|estimated|unknown]
  → **Scope sentence:** <one sentence; becomes slice S1 in 20-plan.md>

## 3. Premise check

<!-- Premise challenge: what would have to be true for this problem to exist at all and for this solution direction to hold? One line per premise, with a rating. -->

| Premise | True if … | Rating |
| --- | --- | --- |
| <…> | <…> | <evidenced | plausible | open> |

## 4. Shared vocabulary

<!-- Terms that emerged in the conversation, in the user's own words. Becomes CONTEXT.md in the retrofit. -->

| Term | Meaning |
| --- | --- |
| <…> | <…> |

## 5. Guardrails

<!-- Non-negotiable limits for the maquette: must-nots, data-protection / security flags from the field of application, things the prototype must deliberately not show. -->

- **GR-1** — <…>

## 6. Chosen direction and alternatives

<!-- Hard stop in sparring: the user has seen three directions before choosing one. Rejected alternatives stay, with reasons (ADR seeds). -->

- **Chosen:** <direction in two sentences> — **because:** <…>
- **Rejected A:** <…> — **because:** <…>
- **Rejected B:** <…> — **because:** <…>

## 7. Candidate requirements (unratified)

<!-- 5–8 in total. Only what the maquette must show. Testable where possible. -->

### Functional
| ID | Requirement |
| --- | --- |
| cF-1 | <…> |

### User interaction
| ID | Requirement |
| --- | --- |
| cU-1 | <…> |

### Non-functional
| ID | Requirement |
| --- | --- |
| cNF-1 | <…> |

## 8. Open questions

<!-- Everything unresolved, incl. the standard concerns of the field of application. Numbering Q1… continues in 40/50/60 and never restarts. -->

- **Q1** — <…>

## 9. Riskiest assumption

- **Assumption:** <one sentence — from the mini pre-mortem: "the maquette was shown and did not convince — why?">
- **If wrong:** <consequence>
- **Cheapest test:** <the smallest experiment that confirms or kills it; picked up again in 60-brief.md>

## Notes (human)

<!-- Off limits for all skills. Copied verbatim on every rewrite. -->
