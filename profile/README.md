# profile/ — customer-specific constraints

Empty in the public release. A customer version carries this customer's constraints here; the Director reads `profile.md` at every start (RULES §8). The format is owned by the setup skill — see https://github.com/ditomax/skill-suite-setup/blob/main/PROFILE.md. This skillset reads: `profile.md`, `questions.md`, `scope.md` (topic limits → sparring guardrails), `it-constraints.md` (stacks, network, data rules → plan-board, build), `design.md` (corporate design tokens → design-3), `review.md` (who decides after the maquette, next-step options → brief Part 4).

A profile may **restrict, never loosen**. `questions.md` may skip (with a value) or add questions by the IDs in `QUESTIONS.md`.

## Minimal example

Put this into `profile/profile.md` and the Director will use it at the next start:

```markdown
# Profile — Example GmbH

- **Customer:** Example GmbH
- **Org code:** EXG
- **Document language:** de
- **Contact for questions:** Jane Doe, jane@example.com
- **Profile files present:** none
```

Every further file (`questions.md`, `scope.md`, …) is optional; the field spec is in PROFILE.md linked above.
