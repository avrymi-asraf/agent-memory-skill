---
name: manage-mcp
description: Guides project-local MCP server design and configuration. Use when adding, changing, or reviewing MCP tools, server config, or tool signatures.
---

# Manage MCP

MCP servers in this template are project-local and configured through `opencode.json`. Tool calls should expose the smallest useful task surface.

## Call Surface

Most MCP tools should have no more than 3-4 arguments. Prefer one essential task input plus optional freeform guidance.

Bad:

```text
convert_pdf(pdf_path, provider, model, pages, render_dpi, timeout_seconds, completeness_check)
```

Good:

```text
convert_pdf_to_markdown(pdf_path, extra_instructions)
```

## Config Boundary

Move provider, model, rendering, timeout, and preset choices into one of:

- `opencode.json` MCP environment.
- MCP server defaults.
- Environment variables.
- A named preset inside the server.

Only expose an argument when the user naturally needs to choose it at task time.

## Project Layout

Local servers live in `.opencode/mcp/<server-name>/`. Prefer single-file `uv` Python MCP servers when possible, with dependencies declared inline.

## Verification

After changing an MCP server:

- Check the tool signature is small.
- Check config paths in `opencode.json`.
- Run unit tests if present.
- Start the server manually only when needed for integration verification.
