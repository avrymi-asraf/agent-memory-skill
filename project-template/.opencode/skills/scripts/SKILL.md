---
name: scripts
description: Guides writing clear project scripts with simple dependencies, explicit usage, safe shell behavior, and verifiable output. Use when creating or reviewing scripts.
---

# Scripts

Scripts should be small, readable operational tools with one purpose.

## Principles

- Use the simplest tool that works.
- Put configuration in args or environment variables, not constants.
- Print status to stderr and machine-readable data to stdout when relevant.
- Make the run command obvious from the file header or docs.
- Verify scripts by running the smallest safe command.

## Python

Prefer `uv run` with PEP 723 inline dependencies for standalone scripts.

## Shell

Use `set -euo pipefail`, validate arguments before use, and send errors to stderr.

## Security

Never commit secrets, tokens, account IDs, or project-specific private endpoints as script constants.
