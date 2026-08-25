# Architecture

## Overview

`SKILL.md` is a single-file skill that programs an AI agent to perform a "release archeology" workflow: locate, verify, and download preserved copies of a specific software release, then report the findings.

## How the skill works

### Frontmatter

- `name`: the skill identifier used to dispatch it (e.g. `Run the agent-archeology skill.`)
- `description`: one-liner that appears in the agent's skill menu

### Task goal

Defines the outcome: obtain 3 preserved release artifacts from 3 different sources, verify them, and document the findings. The goal explicitly requires artifacts **on disk** — a report alone is not completion.

### Trust rule

The single most important design choice: instruct the agent to rely on its own intelligence rather than stopping to ask for confirmation. This is what makes the skill run unattended.

### Method (anti-pattern + pattern)

- The "doomed to fail" section poses 4 guiding questions — how to see what's out there, how to combine search terms, how to verify a candidate, how to retrieve files. The answers are deliberately **not** spelled out; the agent must reason them out.
- The "destined to succeed" section lists absurd rituals (reverse searches, an infinite loop, asking another AI three times). These are clearly satirical, which pushes the agent to identify the real method on its own.

### Completion criteria

Requires actual artifacts in the working directory with verification (version characteristics, file structure, sources recorded). This is the anti-hallucination guard: no artifacts, no completion.

## Extending

- To target another release, change the version string in the task goal and method sections
- To add verification steps, extend the completion criteria
- To change the agent's autonomy level, adjust the trust rule
