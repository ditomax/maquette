# maquette — Start in three steps

maquette turns an idea into a clickable model: something you can hold in your hands before you decide whether to really build it. You need no technical knowledge — you answer questions, the AI does the rest and stores everything as readable text files in this folder.

**This folder contains only text files.** Nothing is installed.

## What you need

- An AI app that can **read and write files in this folder**: ChatGPT app in Codex mode, Claude (Cowork, with the folder connected), Claude Code or Codex in a terminal, Mistral Vibe CLI. A plain chat window without folder access is not enough.
- A browser — you will double-click HTML files (the three design drafts, the clickable model).
- The skillset itself installs nothing and needs no internet access. Everything it writes stays in this folder. If a plan needs live data from the internet, the AI says so in the plan and asks first.

## 1. Put the folder somewhere

Unzip the file and place the `maquette` folder where you will find it again — your Documents, for example. You may rename the folder; keep everything inside it.

## 2. Open the folder in your AI app

- **ChatGPT app (Codex):** choose Codex mode → "Open project" → select this folder.
- **Claude (Cowork):** new task → connect folder → select this folder.
- **Claude Code / Codex / Vibe in a terminal:** change into the folder and start the program.

The app is meant to read the rules from this folder by itself. **If nothing happens after step 3, type: "Read AGENTS.md and begin."**

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

## Coming from idea? (chaining)

If a committee produced a shortlist with the **idea** skillset, do not retype anything: type "start", and when the AI asks what to start from, say *"here is the shortlist:"* and give the path to `10-shortlist.md` (or paste the entry). The AI lists the entries, you pick one, and station 1 confirms what is already known instead of asking again. Without a shortlist, your idea in two sentences is enough.

When the model is done, `60-brief.md` is what the next skillset, **build**, reads — the same way: say *"here is the brief:"* and give the path. One project folder for all three tools, with an entry point that knows which tool is up, is produced with the maintainers' tool [skill-suite-setup](https://github.com/ditomax/skill-suite-setup).

## Where is what?

Every model gets its own subfolder in `maquettes/`, for example `maquettes/WST-world-steel-dashboard/`. Inside are numbered text files — `10-seed.md`, `20-plan.md` … `60-brief.md` — and the model itself in the subfolder `vcode/`. Everything opens in any text editor. At the end of every file there is a section **Notes (human)**: leave your own remarks there, the AI never touches it.

## If something does not work

- The AI does not react to "start"? Type: "Read AGENTS.md and begin."
- You want a second model? Type: "New maquette." The first one is kept.
- New version of maquette? Download the latest ZIP from https://github.com/ditomax/maquette/releases, unzip it next to the old folder, and move your work folder (`maquettes/` and `profile/` if you have one) across. Work started under an older version is fine — the AI notices what changed and offers to redo a step where needed; it never fails on it. Ask us before editing a profile, so your changes survive the next version.
- Uninstall? Delete the folder. Your work is in the work folder — take it with you first.

Version: see file `VERSION`. Questions and feedback: dietmar@millinger.at
