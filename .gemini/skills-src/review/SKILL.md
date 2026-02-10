---
name: review
description: Daily and weekly review workflows. USE WHEN user says "morning routine", "evening routine", "weekly review", "start my day", "end of day".
---

# Review Skill

Morning, evening, and weekly review workflows.

## Routing

| User says | Workflow |
|-----------|----------|
| "morning routine", "start my morning" | `references/morning.md` |
| "evening routine", "end of day" | `references/evening.md` |
| "weekly review" | `references/weekly.md` |

## Templates

Templates are located in the `assets/` directory of this skill.

## Data Access

**Projects:**
```bash
ls Projects/*.md
cat "Projects/Project Name.md"
```

**Tasks:**
```bash
curl "http://127.0.0.1:8090/api/tasks"
curl "http://127.0.0.1:8090/api/tasks?status=in-progress"
```

**Recent daily notes:**
```bash
ls -t Daily/*.md | head -5
```
