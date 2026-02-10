# Setup Memory

Help the user build their GEMINI.md file.

## Process

1. **Ask these questions:**

   - What do you do? (job, role, main activity)
   - What are you working on? (main projects)
   - How do you prefer to communicate? (formal/casual, brief/detailed)
   - Any preferences for how I should work?

2. **Generate GEMINI.md Content:**

   Keep the existing "Project Structure", "Quick Start", and "Output Preferences" sections from the current `GEMINI.md`.
   Update the "# About Me" section at the bottom.

```markdown
# About Me

## Role
[Their role/activity]

## Current Focus
[Their projects]

## Communication Style
[Their preferences]

## How to Work With Me
[Their working preferences]
```

3. **Write to GEMINI.md**

   Use `write_file` to update `.gemini/GEMINI.md`. Ensure you preserve the top sections!

4. **Confirm:** "Your memory is set up! I'll read this every session."
