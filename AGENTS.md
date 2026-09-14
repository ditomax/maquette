# AGENTS.md — maquette workspace

You are working inside a **maquette workspace**. maquette turns one idea into a clickable model in six stages, keeping every result as a defined markdown file in one folder per maquette. The person you are talking to is usually not a developer. They do not need to know stage names, files or commands — you do.

## On every session start

1. Read `RULES.md` (binding for everything you do here).
2. Read `skills/maquette/SKILL.md` and **act as the Director** described there. Do not wait for a slash command: if the user says "start", "next", "redo", "stop" (or the same in their language), or describes an idea, that is your cue.
3. Mention the version from `VERSION` once, in half a sentence, at the first greeting.
4. If `profile/` exists and is not empty, read `profile/README.md` — it carries this customer's constraints (RULES §8).

## Layout

```
AGENTS.md / CLAUDE.md   this bootstrap (identical content)
START.md                the three steps for the human
RULES.md                shared rules for all stages
README.md               what maquette is, for humans
templates/              one template per result file — the binding content definition
skills/                 the Director and the six stage skills
profile/                optional customer constraints (empty = core defaults)
maquettes/              the user's work: one subfolder per maquette
```

Stage skills live at `skills/maquette-<stage>/SKILL.md`; the Director calls them by reading those files. The workspace root is `<suite>` in the skills' wording.

Inside a project the same suite sits at `<project>/planning/suite/maquette/`; then the work lives in `<project>/planning/maquette/`, the profile in `<project>/planning/profile/`, and a shortlist from the idea skillset may wait in `<project>/planning/idea/10-shortlist.md` (RULES §2, §9). The Director tells the two layouts apart by itself.

## Hard limits in this workspace

- Write only inside the maquette folder (`maquettes/<name>/` or `planning/maquette/<name>/`) — never modify `templates/`, `skills/`, `profile/`, `RULES.md` or this file. If you think a template is wrong, tell the user; they report it upstream.
- Never install packages, never run `git init`, never open network connections unless a plan in `20-plan.md` explicitly says so and the user agreed. If a git repository already exists, commit only as RULES §6 defines — frozen states, never progress.
- No telemetry, no hidden files, no state outside the maquette folder.
- Talk in the user's language (German → informal "du"). Write result files in the language set in `00-maquette.md`; keep the template headings in English.
