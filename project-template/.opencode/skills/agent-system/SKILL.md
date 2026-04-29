---
name: agent-system
description: Explains the project-local agent system: agents, skills, memory, MCP servers, AGENTS.md, and OpenCode/GitHub Copilot file responsibilities. Use when setting up, reviewing, or changing the local agent system.
---

# Agent System

This project uses a local agent system. All agent instructions, skills, memory, and MCP servers belong in the repository, not in user-level config.

## Files

- `AGENTS.md`: project overview, status, todo list, and coordination notes.
- `.opencode/agents/*.md`: OpenCode agent definitions.
- `.opencode/agents/*.memory`: short-term and long-term agent memory.
- `.opencode/skills/*/SKILL.md`: durable knowledge and workflows.
- `.opencode/mcp/*`: local MCP servers.
- `opencode.json`: project-local MCP and OpenCode config.
- `.github/copilot-instructions.md`: GitHub Copilot repository instructions.
- `.github/agents/*.agent.md`: Copilot role definitions.

## Memory

Use memory for current plans, decisions, durable project facts, and recurring pitfalls. Integrate new notes into existing sections. Do not append long chat summaries.

## Skills

Skills teach reusable project or domain knowledge. Update a skill when a lesson should help future agents beyond the current task.

## Continuous Improvement

After meaningful work, update one of these:

- `AGENTS.md` for status and project map changes.
- An agent memory file for active context or role-specific lessons.
- A skill for durable workflow or domain knowledge.
