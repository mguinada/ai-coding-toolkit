---
description: Generate a CHANGELOG.md entry from git history since the last tag.
argument-hint: "version (e.g. 1.2.0)"
---

## Usage
`/changelog [version]`

## Context
- Target release version: $ARGUMENTS (e.g. `1.2.0`). If omitted, inferred from the latest git tag or `package.json`.
- `CHANGELOG.md` will be read before writing to preserve existing entries.

Load the `changelog` skill and follow it. Use $ARGUMENTS as the target version if provided.

After writing the changelog entry, load the `git-commit` skill to commit the update with message `docs: update changelog for vX.Y.Z`.

## Output Format
1. **Version determined** — confirmed target version with source (argument, tag inference, or package.json).
2. **Commit summary** — count of commits collected and their type distribution.
3. **Changelog entry** — the new `CHANGELOG.md` section, formatted and ready to review.
4. **File updated** — confirmation that `CHANGELOG.md` was written.
5. **Commit executed** — confirmation of the changelog commit.
