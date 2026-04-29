# Project Agents

## Project

Describe what this project does, how it is built, and the main workflows agents need to understand.

## Agent System

This project uses local agents, local skills, local memory, and local MCP servers. Do not use global agent settings for project work unless the user explicitly asks.

Key paths:

- `.opencode/agents/` - OpenCode agents and memory files.
- `.opencode/skills/` - project skills.
- `.opencode/mcp/` - project MCP servers.
- `.github/copilot-instructions.md` - GitHub Copilot repository instructions.
- `.github/agents/` - Copilot custom agents.

## Status

- Current phase: initial template setup.
- Current blocker: replace this placeholder with real project status.
- Next step: document project structure and run/test commands.

## Todo

- [ ] Fill in project overview.
- [ ] Document run, test, lint, and deploy commands.
- [ ] Add project-specific skills as durable knowledge appears.
- [ ] Keep agent memory concise and current.

## Working Rules

- Read relevant skills before specialized work.
- Prefer existing project tools and patterns.
- Verify edits and command results before claiming completion.
- Update local memory or skills when a durable project fact is learned.
