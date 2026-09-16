# maquette

**From idea to clickable model — seven markdown skills, one command.**

Version: see `VERSION` · September 2026 · DMBG · https://github.com/ditomax/maquette

_Deutsch: Für Anwender genügt `START.md` — drei Schritte, keine Installation. Gespräch und Ergebnisdateien folgen Ihrer Sprache; die Überschriften in den Vorlagen bleiben englisch._

## For agents

If you are reading this from a link and have no local copy yet:

1. Get one — `git clone https://github.com/ditomax/maquette` or unzip the latest release from https://github.com/ditomax/maquette/releases — into a folder the user chooses (default: `./maquette` next to their other work). That download is the only network access; the "no network" rule in `AGENTS.md` applies from then on.
2. Work from inside that folder and read its `AGENTS.md`. Do not act as the Director from this README — the rules live in `RULES.md` and `skills/`.
3. Layout: standalone (this folder as is) unless the user has a project with a `planning/` folder — then the suite belongs at `planning/suite/maquette/` and `planning/AGENTS.md` is the entry point, not this file.
4. A clone gives updates via `git pull`; the user's work in `maquettes/` is ignored by git, so nothing of it is ever committed to a clone. `hooks/`, `guard.py` and `skill-suite-setup` are for skillset developers — ignore them.

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

Finished results look like `examples/10-seed.md` and `examples/60-brief.md` (fictitious company). Every stage reads exactly one input file and writes exactly one result file. All results live in **one folder per maquette**, carry frontmatter and follow write rules that stop agents from overwriting each other (see `RULES.md`). The folder is the state — there is nothing outside it.

maquette is the middle of a three-part suite — **idea → maquette → build** — and talks to its neighbours through two files. Upstream, the idea skillset (idea-collect, idea-evaluate) hands over `10-shortlist.md` (contract H1): the Director lists the entries, the user picks exactly one, and stage 1 prefills from it. Downstream, `60-brief.md` (contract H2) is the handover to the build skillset, which turns the clickable model into a product. Both seams are optional: without a shortlist, stage 1 starts from an idea in prose, an idea card or a concept sketch; without build, the brief is still the honest record of what the maquette proved.

**Compatibility.** In: `10-shortlist.md` contract `H1/1` from idea ≥ 0.1.0. Out: `60-brief.md` contract `H2/2`, read by build ≥ 0.1.1 (`H2/1` briefs are still accepted by build with a note). Version triples tested together: [skill-suite-setup/compat.md](https://github.com/ditomax/skill-suite-setup/blob/main/compat.md). Changes: `CHANGELOG.md`.

## Structure

```
maquette/
  START.md             three steps for the human
  AGENTS.md            entry point for Codex — turns the agent into the Director
  CLAUDE.md            the same for Claude
  VERSION
  README.md            this file
  RULES.md             shared rules for all stages — frontmatter, write rules, conversation rules
  QUESTIONS.md         every question the skillset asks, with stable IDs — the tailoring surface for profiles
  CHANGELOG.md         what changed per version
  hooks/               pre-commit guard for development clones (see Release)
  ATTRIBUTION.md       adopted ideas and their origin
  LICENSES/            third-party license texts
  profile/             optional customer-specific constraints (empty = core defaults)
  examples/            fictitious finished results — a seed and a brief (Example GmbH)
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

**Chat tools without folder access** (plain ChatGPT, Le Chat, Perplexity): not supported here — unlike idea's collect stage, every maquette stage (sparring through build) needs folder access.

No dependencies, no setup script, no network access, no telemetry. `maquettes/` is excluded from the repo via `.gitignore` — users' work never lands in the public repository.

## Inside a project

The workspace above is the standalone form. Inside a project folder the same suite is copied to `planning/suite/maquette/` (read-only), the maquettes live in `planning/maquette/`, the profile in `planning/profile/`, and the shortlist in `planning/idea/10-shortlist.md`. Product code lives outside `planning/`; the prototype code stays in each maquette's `vcode/`, frozen after the brief. The Director recognises the layout by the `planning/` folder — nothing to configure.

Git is optional in both forms. Skills never create a repository; if one exists, a commit marks a frozen state (a stage `done`, a slice, a fix) and nothing else — the policy is in `RULES.md` §6.

## Profiles

Customer-specific variants (restricted topics, IT constraints, standards, corporate design, the customer's own review process, questions skipped or added) do not fork this repo. They live in a `profile/` folder the Director reads at start; a profile may restrict, never loosen. The format is specified in [skill-suite-setup/PROFILE.md](https://github.com/ditomax/skill-suite-setup/blob/main/PROFILE.md); a minimal example is in `profile/README.md`. `QUESTIONS.md` lists every question the skillset asks, with stable IDs — read it before a session, and use the IDs in a profile to skip or add questions.

## Modes

- **workshop** (default): half a day, goal is a demo. Forcing questions Q1–Q4, grilling 10 minutes, slices S1–S3, fix budget 10 (with git) / 5 (without).
- **discovery**: two to three days, goal is a robust prototype plus a complete retrofit seed. Q1–Q6, grilling 30 minutes, all slices, double fix budget.

Git is optional: if a repository exists, every slice and every fix is committed; otherwise not. The skills never create a repository themselves.

## Release

Development clones activate the customer-data guard once: `git config core.hooksPath hooks` (the hook calls `guard.py` from the sibling `skill-suite-setup` repo and blocks commits that carry customer markers). Release ZIPs are built with `skill-suite-setup/release.py`, which ships only git-tracked, allowlisted, guard-clean files.

Repository: https://github.com/ditomax/maquette — releases at https://github.com/ditomax/maquette/releases.

New version: bump `VERSION`, tag `vX.Y.Z`, GitHub release with the folder attached as `maquette-vX.Y.Z.zip`. Users update by downloading the new folder and copying their `maquettes/` (and `profile/`) across.

## Origin

The stages combine our own skills (idea-work, ki-ideenfindung, konzeptskizze, Concept Authoring Manifest, CLAUDE.local.md) with ideas from gstack (Garry Tan, MIT): forcing questions and premise challenge, review board with roles, three divergent design variants, confidence-calibrated review, one commit per fix with revert on regression. Method was adopted, not code.

## License

gstack is © 2026 Garry Tan under the MIT License; the full text is in `LICENSES/gstack-MIT.txt` and in `ATTRIBUTION.md`, which also lists exactly which method went into which stage. maquette itself is © 2026 Dietmar Millinger and also released under the MIT License (`LICENSE`).
