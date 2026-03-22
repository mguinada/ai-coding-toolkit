---
description: Orchestrate a full release: pre-flight checks, changelog, version bump, tag, and GitHub release.
argument-hint: "version (e.g. 1.2.0)"
---

## Usage
`/release [version]`

## Context
- Target release version: $ARGUMENTS (e.g. `1.2.0`). Required for a clean release; will prompt if omitted.
- Working tree, test suite, and branch state will be validated before any changes are made.
- `CHANGELOG.md`, `package.json` (or equivalent manifest), and git tags will all be updated.

Load the `release` skill and follow it. Use $ARGUMENTS as the target version.

## Output Format
1. **Pre-flight report** — pass/fail status for each readiness check.
2. **Changelog entry** — the new section added to `CHANGELOG.md`.
3. **Version change** — before and after version in the manifest.
4. **Tag created** — annotated tag name and SHA.
5. **Release URL** — link to the created GitHub release.

**Do not merge branches. Do not skip pre-flight checks.**
