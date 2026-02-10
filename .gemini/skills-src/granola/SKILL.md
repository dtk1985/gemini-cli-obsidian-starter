---
name: granola
description: Query and sync Granola meetings to Obsidian vault. Use when user mentions Granola, meeting transcripts, or wants to sync meeting notes.
---

# Granola Skill

Query and sync Granola AI meeting notes to Obsidian vault.

## How It Works

Granola stores everything locally at `~/Library/Application Support/Granola/cache-v3.json`:
- Documents (meetings with title, notes, people)
- Transcripts (real-time, with timestamps and source)
- Updates in real-time as you record

No API calls needed - reads directly from local cache.

## Quick Start

```bash
# List all meetings
python3 .gemini/skills-src/granola/scripts/granola.py list

# Get specific meeting with transcript
python3 .gemini/skills-src/granola/scripts/granola.py get <id>

# Sync new meetings to vault
python3 .gemini/skills-src/granola/scripts/granola.py sync

# Sync specific meeting
python3 .gemini/skills-src/granola/scripts/granola.py sync --id <id>
```

## Commands

### list

List all Granola meetings with sync status.

```bash
python3 .gemini/skills-src/granola/scripts/granola.py list
python3 .gemini/skills-src/granola/scripts/granola.py list --limit 5
```

### get

View full meeting details and transcript.

```bash
python3 .gemini/skills-src/granola/scripts/granola.py get <id>
python3 .gemini/skills-src/granola/scripts/granola.py get <id> --no-transcript
```

### sync

Sync meetings to `Meetings/` as structured Markdown.

```bash
# Sync new meetings only
python3 .gemini/skills-src/granola/scripts/granola.py sync

# Sync specific meeting
python3 .gemini/skills-src/granola/scripts/granola.py sync --id <id>

# Re-sync all (overwrites existing)
python3 .gemini/skills-src/granola/scripts/granola.py sync --all
```
