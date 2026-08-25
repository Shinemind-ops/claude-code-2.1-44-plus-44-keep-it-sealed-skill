# Contributing

This is a small, focused project. Contributions that keep the skill sharp and reliable are welcome.

## Dev setup

- No build step required — `SKILL.md` is plain markdown consumed by AI agents
- Test by dispatching the skill to an agent in a sandbox directory (never your real working directory)

## Quality standards

- Keep the skill self-contained (a single `SKILL.md`)
- Keep language neutral and precise
- Do not add platform-specific assumptions
- Preserve the trust-based autonomy design (the agent should solve, not stop to ask)

## PR checklist

- [ ] `SKILL.md` still passes a fresh-agent test (agent completes the full workflow unattended)
- [ ] No new environment-specific paths
- [ ] `README.md` updated if behavior changes
