---
name: client
description: Manage client relationships, follow-ups, and emails. Use when user asks about clients, "who needs follow-up", or wants to add/email a client.
---

# Client Skill

Manage clients using `Clients/` folder.

## Workflows

### Check Follow-ups
Triggers: "Who needs follow-up?", "Check clients", "Who do I need to contact?"
See [references/check-followups.md](references/check-followups.md) for steps to identify clients needing attention based on `next_action` date.

### Draft Email
Triggers: "Draft email to [name]", "Email [name]"
See [references/draft-email.md](references/draft-email.md) for steps to draft a personalized email based on client context.

### Add Client
Triggers: "Add client [name]", "New lead [name]"
See [references/add-client.md](references/add-client.md) for steps to create a new client file with standard frontmatter.

## Data Structure

Client files live in `Clients/*.md` with frontmatter:

```yaml
---
type: client
name: Sarah Chen
email: sarah@example.com
company: TechStartup Inc
stage: active       # lead, active, customer
next_action: 2026-01-10
next_action_note: Follow up on proposal
last_contact: 2026-01-05
---
```

## Quick Queries

**List all clients:**
```bash
ls Clients/*.md
```

**Find who needs follow-up:**
```bash
grep -l "next_action:" Clients/*.md | while read f; do
  echo "=== $(basename "$f" .md) ==="
  grep -E "^(next_action|next_action_note):" "$f"
done
```

**Find by stage:**
```bash
grep -l "stage: lead" Clients/*.md
```
