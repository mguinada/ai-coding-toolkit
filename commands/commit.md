---
description: Inspect staged changes and create a conventional git commit.
argument-hint: "context or hint (optional)"
---

## Usage
`/commit [context or hint]`

## Context
- Optional commit context or hint: $ARGUMENTS
- Staged changes will be inspected with `git diff --staged`.
- Recent commit history will be referenced for style consistency.

Load the `git-commit` skill and follow it. Use $ARGUMENTS as context or a hint for the commit message if provided.

After committing, offer to open a pull request with `/pr`.

## Output Format
1. **Staged changes summary** — brief description of what is staged.
2. **Commit message** — final conventional commit with type, scope (if applicable), and subject.
3. **Commit confirmation** — confirmation that the commit was executed successfully.
4. **Next action prompt** — offer to run `/pr` if the branch is ready for review.
