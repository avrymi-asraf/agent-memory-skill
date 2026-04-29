# Project-Level Agents, Skills, Memory, and MCP Template

This repository contains a starter template for adding a local agent system to a project. The template is designed for OpenCode and GitHub Copilot, with every agent, skill, memory file, and MCP server stored at the project level.

Do not put this system in user-level configuration. Do not rely on dotfiles symlinks. A project that uses the template should be self-contained.

## What This Template Provides

The template creates a small local agent system:

- **Agents** define role, behavior, tool boundaries, and collaboration style.
- **Skills** hold durable domain knowledge and reusable workflows.
- **Memory files** keep active plans, decisions, and long-term project facts.
- **MCP config** exposes project-local tools with small call surfaces.
- **Copilot files** mirror the same roles and instructions for GitHub Copilot.

The goal is not to create a huge framework. The goal is to give a new project enough structure for agents to reason, delegate, remember, and improve their local instructions over time.

## Basic Agents

- **Manager**: plans large tasks, delegates one step at a time, reviews outputs, and updates memory.
- **Planner**: designs implementation plans, test plans, and deployment-aware code flow.
- **Builder**: implements small, focused changes from a plan.
- **Operator**: runs commands, manages local execution, verifies outcomes, and handles tools.
- **Reviewer**: reviews code and plans for bugs, regressions, missing tests, and risk.
- **Researcher**: searches current information, uses research MCPs, and updates knowledge artifacts.

## Basic Skills

- `agent-system`: explains the local agent system and file responsibilities.
- `manage-skill`: guides creating and updating project skills.
- `manage-mcp`: guides MCP design and project-local MCP configuration.
- `scripts`: guides clear, operational scripts.
- `code-principles`: captures implementation quality standards.
- `internet-search`: guides current web research and citation behavior.
- `wiki-llm`: explains the compounding wiki / knowledge-base pattern.
- `project-skills`: explains how to capture project-specific knowledge.

## Project-Level Rule

All agent settings, skills, memory, and MCP servers live inside the project:

```text
project-root/
  AGENTS.md
  opencode.json
  .opencode/
    agents/
    skills/
    mcp/
    tools/
  .github/
    copilot-instructions.md
    agents/
```

Agents should read and update only the local project files unless the user explicitly asks for global configuration work.

## MCP Rule

MCP tools should expose only the essential task inputs. Most tools should have no more than 3-4 call arguments. Provider, model, rendering, timeout, and preset settings belong in `opencode.json`, environment variables, or server-side defaults.

Example:

```text
Bad:  convert_pdf(pdf_path, provider, model, pages, render_dpi, timeout_seconds, completeness_check)
Good: convert_pdf_to_markdown(pdf_path, extra_instructions)
```

The template includes project-local MCP servers copied from the existing project:

- `project-template/.opencode/mcp/gemini-deep-research/`
- `project-template/.opencode/mcp/pdf-to-markdown/`

## OpenCode Template

OpenCode uses:

- `opencode.json` for project-local config, plugins, and MCP servers.
- `.opencode/agents/*.md` for project agents.
- `.opencode/agents/*.memory` for local agent memory.
- `.opencode/skills/*/SKILL.md` for local skills.
- `.opencode/mcp/*` for local MCP servers.

## GitHub Copilot Template

GitHub Copilot uses:

- `.github/copilot-instructions.md` for repository-wide agent instructions.
- `.github/agents/*.agent.md` for role-specific custom agents.

The Copilot files mirror the same role model as OpenCode, but they avoid OpenCode-specific syntax.

## Using the Template

1. Copy everything inside `project-template/` into a project root.
2. Fill `AGENTS.md` with the project overview, status, and active todo list.
3. Replace placeholder secrets in environment variables, not committed files.
4. Keep project skills and memory concise, integrated, and current.
5. When agents learn durable project facts, update local skills or memory instead of relying on chat history.
