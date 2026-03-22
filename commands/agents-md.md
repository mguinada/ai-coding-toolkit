---
description: Generate or update AGENTS.md for the current project.
argument-hint: "project description or focus area (optional)"
---

## Usage
`/agents-md [project description or focus area]`

## Context
- Optional project description or focus hint: $ARGUMENTS
- `package.json`, lockfiles, config files, and directory structure will be inspected.
- Existing `AGENTS.md` will be read before writing to avoid overwriting current content.

Load the `agents-md-creator` skill and follow it. Use $ARGUMENTS as a project description hint if provided.

## Output Format
1. **Project summary** — detected type, stack, and key directories.
2. **`AGENTS.md` content** — complete generated or updated file content.
3. **Changes summary** — new sections added or existing sections updated.
4. **Verification prompt** — ask the user to confirm or refine agent-specific guidelines (e.g. tool restrictions, prohibited actions).
