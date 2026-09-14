# maquette

**From idea to clickable model — seven markdown skills, one command.**

Version 0.3 · September 2026 · DMBG · https://github.com/ditomax/maquette

_Deutsch: Für Anwender genügt `START.md` — drei Schritte, keine Installation. Eine deutsche Sprachfassung der Vorlagen folgt bei Bedarf; die Skills antworten ohnehin in der Sprache, in der man sie anspricht._

## What is a maquette?

A maquette (French, "ma-KET") is the model architects build before they build: small, tangible, made of cardboard — not the building, but exact enough to walk around it, check proportions and decide with the client whether and how to proceed. Here the maquette is the clickable prototype of a software idea: not a product, but a model on which you grasp the idea and decide about the real build. It is valuable precisely because it is cheap and provisional.

## How it works

The user types **start** and afterwards only **next**, **redo** or **stop**. A Director skill reads the maquette folder, says where things stand, and calls the next of six stages:

| Stage | "Team member" | Result | Minutes (workshop) |
| --- | --- | --- | --- |
| 1 sparring | sparring partner | `10-seed.md` — idea sharpened, scope, three directions, one chosen, demo walked through screen by screen | 15 |
| 2 plan-board | review board | `20-plan.md` — requirements grilled along the walk-through, edge cases decided, slices, approval | 20 |
| 3 design-3 | designer | `30-design.md` + three HTML variants + comparison page | 15 |
| 4 build | build team | `40-build.md` + `vcode/` — slice by slice | 60 |
| 5 harden | quality checker | `50-harden.md` — findings, fixes within budget, demo-readiness | 20 |
| 6 brief | chronicler | `60-brief.md` — demo script, can/cannot, retrofit seed | 10 |

Every stage reads exactly one input file and writes exactly one result file. All results live in **one folder per maquette**, carry frontmatter and follow write rules that stop agents from overwriting each other (see `RULES.md`). The folder is the state — there is nothing outside it.

Upstream, our SME chain can feed it (ki-ideenfindung → idea card, konzeptskizze → concept sketch; both are prefilled in stage 1). Downstream comes the Concept Authoring Manifest: `60-brief.md` contains the retrofit seed for Phase 1 (Path B).

## Structure

```
maquette/
  START.md             three steps for the human
  AGENTS.md            entry point for Codex — turns the agent into the Director
  CLAUDE.md            the same for Claude
  VERSION
  README.md            this file
  RULES.md             shared rules for all stages — frontmatter, write rules, conversation rules
  ATTRIBUTION.md       adopted ideas and their origin
  LICENSES/            third-party license texts
  profile/             optional customer-specific constraints (empty = core defaults)
  maquettes/           the users' work, one subfolder per maquette (not in the repo)
  templates/           one template per result file (binding content definition)
  skills/
    maquette/          Director
    maquette-sparring/
    maquette-plan-board/
    maquette-design-3/
    maquette-build/
    maquette-harden/
    maquette-brief/
```

## Distribution and installation

This folder is the **workspace** — repo and ZIP share the same structure. Users download the ZIP of a release, unzip it, open the folder in their AI app and type "start" (instructions in `START.md`). `AGENTS.md` (Codex) and `CLAUDE.md` (Claude) are read automatically when the folder opens and turn the agent into the Director — nothing to install, no symlinks, no global skill folders.

Developers who want the skills globally can additionally:

```
ln -s "$PWD/skills/"maquette* ~/.codex/skills/      # or ~/.claude/skills/
```

**ChatGPT / Mistral** (no folder access): no Director. Use the body of a stage skill (without frontmatter) as system prompt, attach `RULES.md` and the matching template; the human maintains `00-maquette.md` by hand.

No dependencies, no setup script, no network access, no telemetry. `maquettes/` is excluded from the repo via `.gitignore` — users' work never lands in the public repository.

## Profiles

Customer-specific variants (restricted topics, IT constraints, corporate design, extra checklist items, the customer's own approval process) do not fork this repo. They live in a `profile/` folder inside the workspace that the Director reads at start and passes to each stage. A profile may restrict, never loosen the core rules. The profile format is documented in `profile/README.md`; an empty `profile/` means core defaults. Customer ZIP = core release + `profile/` + empty `maquettes/`.

## Modes

- **workshop** (default): half a day, goal is a demo. Forcing questions Q1–Q4, grilling 10 minutes, slices S1–S3, fix budget 10 (with git) / 5 (without).
- **discovery**: two to three days, goal is a robust prototype plus a complete retrofit seed. Q1–Q6, grilling 30 minutes, all slices, double fix budget.

Git is optional: if a repository exists, every slice and every fix is committed; otherwise not. The skills never create a repository themselves.

## Release

Repository: https://github.com/ditomax/maquette — releases at https://github.com/ditomax/maquette/releases.

New version: bump `VERSION`, tag `vX.Y.Z`, GitHub release with the folder attached as `maquette-vX.Y.Z.zip`. Users update by downloading the new folder and copying their `maquettes/` (and `profile/`) across.

## Origin

The stages combine our own skills (idea-work, ki-ideenfindung, konzeptskizze, Concept Authoring Manifest, CLAUDE.local.md) with ideas from gstack (Garry Tan, MIT): forcing questions and premise challenge, review board with roles, three divergent design variants, confidence-calibrated review, one commit per fix with revert on regression. Method was adopted, not code.

## License

gstack is © 2026 Garry Tan under the MIT License; the full text is in `LICENSES/gstack-MIT.txt` and in `ATTRIBUTION.md`, which also lists exactly which method went into which stage. maquette itself is © 2026 Dietmar Millinger and also released under the MIT License (`LICENSE`).
