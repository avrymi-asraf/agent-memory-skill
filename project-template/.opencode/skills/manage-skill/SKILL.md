---
name: manage-skill
description: Guides creation and maintenance of project-local SKILL.md files. Use when adding, editing, reviewing, or reorganizing agent skills.
---

# Manage Skill

Skills are concise markdown knowledge units. They should teach the agent enough context to reason, not only a rigid checklist.

## Structure

Each skill lives at `.opencode/skills/<skill-name>/SKILL.md` and starts with:

```markdown
---
name: skill-name
description: What the skill does and when to use it.
---
```

## Authoring Rules

- Keep `SKILL.md` focused and under 300 lines.
- Put essentials in the skill; put large references in nearby files only when needed.
- Write descriptions with both what the skill does and when to use it.
- Prefer concrete examples over generic warnings.
- Update existing skills in place instead of creating duplicates.

## Update Workflow

1. Read the full current skill.
2. Identify the durable idea that belongs there.
3. Integrate the change into the natural section.
4. Remove stale or duplicate wording.
5. Re-read the result and verify the workflow still makes sense.
