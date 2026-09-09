# maquette — Start in three steps

maquette turns an idea into a clickable model: something you can hold in your hands before you decide whether to really build it. You need no technical knowledge — you answer questions, the AI does the rest and stores everything as readable text files in this folder.

**This folder contains only text files. No programs, no installation, no internet access.**

## 1. Put the folder somewhere

Unzip the file and place the `maquette` folder where you will find it again — your Documents, for example. Do not rename it, do not delete anything inside.

## 2. Open the folder in your AI app

- **ChatGPT app (Codex):** choose Codex mode → "Open project" → select this folder.
- **Claude (Cowork):** new task → connect folder → select this folder.
- **Claude Code / Codex in a terminal:** change into the folder and start the program.

The app reads the rules from this folder automatically when it opens it.

## 3. Type "start"

Type **start** — or simply your idea in two sentences. From then on the AI guides you through six stations and asks after each one: **next**, **redo** or **stop**. There are no other commands.

| Station | Who | What you get | approx. |
| --- | --- | --- | --- |
| 1 | Sparring partner | Your idea sharpened, with a clear goal for the model | 15 min |
| 2 | Review board | A plan in three to five slices | 20 min |
| 3 | Designer | Three drafts side by side in the browser, you choose | 15 min |
| 4 | Build team | The clickable model, slice by slice | 60 min |
| 5 | Quality checker | Tested and repaired, with an honest verdict | 20 min |
| 6 | Demo brief | A three-minute script for the presentation and the next step | 10 min |

You can stop at any time. Whatever exists by then stays in the `maquettes/` folder and continues next time with **next**.

## Where is what?

Every model gets its own subfolder in `maquettes/`, for example `maquettes/WST-world-steel-dashboard/`. Inside are numbered text files — `10-seed.md`, `20-plan.md` … `60-brief.md` — and the model itself in the subfolder `vcode/`. Everything opens in any text editor. At the end of every file there is a section **Notes (human)**: leave your own remarks there, the AI never touches it.

## If something does not work

- The AI does not react to "start"? Type: "Read AGENTS.md and begin."
- You want a second model? Type: "New maquette." The first one is kept.
- New version of maquette? Download the latest ZIP from https://github.com/ditomax/maquette/releases, copy your `maquettes/` subfolder across, done.

Version: see file `VERSION`. Questions and feedback: dietmar@millinger.at
