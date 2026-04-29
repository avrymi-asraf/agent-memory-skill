---
name: gemini-deep-research
description: Project-local MCP server for starting and polling Google Gemini Deep Research jobs. Use when a project agent needs long-running sourced research.
---

# Gemini Deep Research MCP

This server starts and polls Gemini Deep Research interactions. It is intended for long-running research jobs where the agent should start work, poll later, and extract the final text output.

## Files

- `.opencode/mcp/gemini-deep-research/mcp-server.py`

## Requirements

- `GOOGLE_API_KEY` in the MCP environment.
- Optional `GEMINI_API_BASE_URL`.

## Run Manually

```bash
uv run .opencode/mcp/gemini-deep-research/mcp-server.py
```

## Tools

- `deep_research_start_regular(prompt, additional_instructions=None)`
- `deep_research_start_max(prompt, additional_instructions=None)`
- `deep_research_start_regular_with_files(prompt, file_uris, additional_instructions=None)`
- `deep_research_start_max_with_files(prompt, file_uris, additional_instructions=None)`
- `deep_research_poll(interaction_id)`

File-search store names are configured with `GEMINI_DEEP_RESEARCH_FILE_SEARCH_STORES` as a comma-separated environment variable, not passed at call time.

## Usage

1. Call one start tool and keep the returned `interaction_id`.
2. Poll with `deep_research_poll(interaction_id)` every 30-60 seconds.
3. When `done` is true, extract final report text from `raw.outputs` items where `type == "text"`.

Deep Research can take around 10 minutes. The agent can do unrelated work while polling.

## Result Handling

Ignore `thought` outputs in final user-facing answers. Present `text` outputs and preserve useful source URLs from annotations when available.
