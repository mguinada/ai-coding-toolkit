---
description: Push the current branch and open a GitHub pull request.
argument-hint: "title hint or description (optional)"
---

## Usage
`/pr [title hint or description]`

## Context
- Optional PR title hint or description context: $ARGUMENTS
- Current branch commits and diff will be inspected.
- GitHub repository conventions and label taxonomy will be applied.

Load the `create-pr` skill and follow it. Use $ARGUMENTS as a title hint or description context if provided.

## Output Format
1. **Branch summary** — commit count and scope of changes going into the PR.
2. **PR title** — conventional commit format title.
3. **PR body** — summary, motivation, and testing notes.
4. **Labels applied** — list of labels attached to the PR.
5. **PR URL** — link to the created pull request.

**Iron rule: never merge. Create the PR for human review only.**
