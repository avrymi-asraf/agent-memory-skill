---
name: code-principles
description: Captures project implementation standards: understand first, follow local patterns, keep changes scoped, verify behavior, and avoid unrelated refactors.
---

# Code Principles

Use the existing project shape before introducing a new one.

## Standards

- Read nearby code before editing.
- Prefer existing patterns, helpers, and conventions.
- Keep changes scoped to the user request.
- Add abstractions only when they remove real complexity.
- Verify the behavior touched by the change.
- Do not hide uncertainty; state remaining risk.

## Testing

Match test depth to risk. Small documentation changes may need file inspection only. Shared behavior, user-facing flows, and data changes need focused tests.
