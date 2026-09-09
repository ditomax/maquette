---
stage: design
owner: design-3
status: in_progress          # open | in_progress | done | skipped
revision: 1
created: <YYYY-MM-DDThh:mm>
updated: <YYYY-MM-DDThh:mm>
input: 20-plan.md@<rev>
---

# Design <code>: <title>

_Result of the design-3 stage. Three deliberately different variants as standalone HTML files (`30-design-a.html`, `-b.html`, `-c.html`), compared in `30-compare.html`. Idea from gstack design-shotgun (© 2026 Garry Tan, MIT License, see `LICENSES/gstack-MIT.txt`), without server, screenshots and taste profile._

## 1. Context

<!-- Five questions, one at a time. Answers in the user's words. Prefill from 20-plan.md where possible and have it confirmed. -->

- **Who uses it:** <role, situation, device>
- **Job to be done:** <the one sentence why someone opens the page>
- **Existing constraints:** <corporate design, reference tools, prohibitions — or "free">
- **User flow of S1:** <step → step → result>
- **Edge cases:** <empty, many, error, slow>

## 2. Variants

<!-- Anti-convergence rule: the three variants MUST differ in typeface, colour world and layout. One line of reasoning why each variant fits §1. -->

| Variant | Character | Typeface | Colour world | Layout | Fits because |
| --- | --- | --- | --- | --- | --- |
| A | <e.g. "sober, table first"> | <…> | <…> | <…> | <…> |
| B | <e.g. "visual, card first"> | <…> | <…> | <…> | <…> |
| C | <e.g. "guided, one step per screen"> | <…> | <…> | <…> | <…> |

**All three show the same content:** slice S1 with realistic sample data, no lorem ipsum.

## 3. Decision

- **Chosen:** <A | B | C | mix: <…>> — **because:** <the user's reasoning, in their words>
- **Taken from the others:** <concrete elements, or "nothing">
- **Rejected:** <the other two, one sentence each>

## 4. Design tokens for the build

<!-- What build takes over from the chosen HTML file. Short, machine-readable. -->

```yaml
typeface: <family, fallback>
colours: {background: "#…", text: "#…", accent: "#…", warning: "#…"}
layout: <grid/columns in one sentence>
spacing: <base unit>
start_file: 30-design-<x>.html
```

## Notes (human)

<!-- Off limits for all skills. Copied verbatim on every rewrite. -->
