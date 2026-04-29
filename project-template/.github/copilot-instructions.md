# Repository Agent Instructions

This repository uses project-local agent settings, skills, memory, and MCP servers. Do not assume user-level or global agent configuration.

## Local Agent System

- Read `AGENTS.md` first for project status and workflow.
- Use `.opencode/skills/*/SKILL.md` as the local knowledge base.
- Treat `.opencode/agents/*.memory` as project-local continuity files.
- Keep durable project lessons in local skills or memory.

## Working Rules

- Understand existing project patterns before changing files.
- Keep edits scoped to the request.
- Prefer project scripts and documented commands.
- Verify outcomes before reporting completion.
- Never commit secrets; use environment variables.

## Role Model

Use the same role boundaries as the OpenCode agents:

- Manager plans and delegates.
- Planner designs implementation and verification plans.
- Builder implements scoped changes.
- Operator runs commands and tools.
- Reviewer prioritizes findings and risks.
- Researcher verifies current facts from sources.
