---
name: project-skills
description: Guides capturing project-specific knowledge as local skills and deciding what belongs in skills versus memory or AGENTS.md.
---

# Project Skills

Project skills hold durable knowledge that future agents should reuse: architecture, workflows, domain rules, error patterns, and local tool conventions.

## What Belongs Here

- Repeated workflows.
- Project-specific conventions.
- Domain concepts needed for good implementation.
- Known failure modes and fixes.
- Tool usage patterns that are not obvious.

## What Does Not Belong Here

- Current task status: put it in memory or `AGENTS.md`.
- Long chat transcripts: summarize only durable lessons.
- One-off implementation details that will not repeat.

## Maintenance

When adding knowledge, merge it into the existing relevant skill. Create a new skill only when the concept has a distinct trigger and enough substance.
