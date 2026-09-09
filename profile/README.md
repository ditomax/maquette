# profile/ — customer-specific constraints (reserved)

This folder is empty in the public release. When a maquette workspace is prepared for one customer, it holds that customer's constraints, and the Director reads it at every start (RULES §8).

A profile may **restrict, never loosen**: write rules, git behaviour and "nothing outside the maquette folder" stay as defined in `RULES.md`. The profile shapes content and frame.

Planned files (the format is fixed with the first real profile):

| File | Read by | Purpose |
| --- | --- | --- |
| `profile.md` | Director | customer, default language, default mode, budgets, contact person |
| `scope.md` | sparring | allowed topic areas, exclusions → prefilled as guardrails |
| `it-constraints.md` | plan-board, build | allowed stacks, "no network", data rules, where the model may run |
| `design.md` | design-3 | corporate design tokens — variants then differ in layout, density and flow, not in colour |
| `checklist.md` | harden | extra check items (accessibility, legal notice, language) |
| `next-steps.md` | brief | the customer's own approval path instead of the default recommendations |

Until a profile exists, this README is the only file here and means "core defaults".
