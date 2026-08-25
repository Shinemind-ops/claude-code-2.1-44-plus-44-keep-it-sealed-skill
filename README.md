# Keep It Sealed — Archeology Skill

*For those who know, 44+44. For those who don't, this is an archeology project.*

## What is this?

A skill (SKILL.md) that turns any AI agent into an archeologist. Give it a task and it independently hunts down preserved copies of a particular software release, verifies them, downloads them, and writes up the findings — no human intervention needed.

## What it does

The agent will:

1. Explore public sources to locate preserved copies of the release
2. Verify each candidate (version number, file structure, hashes)
3. Download the artifacts into the working directory
4. Cross-validate against multiple independent sources
5. Write a structured archeology report

## How to use

1. Copy `SKILL.md` into your agent's skill directory (e.g. `~/.claude/skills/agent-archeology/`)
2. Dispatch a task with a minimal prompt: `Run the agent-archeology skill.`
3. The agent reads the skill and executes the full archeology workflow on its own

## Running Claude Code

The skill drives Claude Code under the hood. To run it from a downloaded archive — no installer needed, just three steps:

```
extract                       # 1. unpack the archive
cd ~/claude-code/package      # 2. enter the package directory
node ./cli.js                 # 3. launch the main program
```

- **Extract**: unpack the archive into `~/claude-code/`
- **Enter**: move into the `package/` directory
- **Launch**: run `cli.js` with Node.js (v18+) — the only runtime dependency

No installer, no login flow. Once it starts, dispatch the skill and it runs the full archeology workflow on its own.

## Why archeology?

The release in question is no longer served by the official registry. Archeology is how you recover history: find the preserved copies, verify they are genuine, and document what you found.

## Why download this?

The skill is the tool; the value analysis explains what it unlocks:

- [Value & Use Analysis (EN)](docs/VALUE-ANALYSIS.md)
- [價值與用途分析 (中文)](docs/VALUE-ANALYSIS.zh.md)

## Design highlights

- **Trust-based autonomy**: the skill tells the agent to solve problems with its own intelligence instead of stopping to ask
- **Guided method**: instead of spelling out every step, it poses guiding questions so the agent reasons out the approach
- **Anti-hallucination guard**: completion requires actual artifacts on disk, not just a written report

## License

MIT — see [LICENSE](LICENSE).
