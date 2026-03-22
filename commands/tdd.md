---
description: Drive Test-Driven Development (Red-Green-Refactor) for a feature or behavior.
argument-hint: "feature description (e.g. user password reset)"
---

## Usage
`/tdd [feature description]`

## Context
- Feature or behavior to implement: $ARGUMENTS (e.g. `user password reset`).
- Existing test files and source code will be referenced as the cycle progresses.
- Test runner output will be checked after every Red and Green step.

Load the `tdd` skill and follow it.

Launch the `tdd-guide` agent at the start of the session. It will enforce test-first order and flag any deviation throughout.

## Output Format
1. **Behavior breakdown** — ordered list of discrete units to implement.
2. **Red step** — the failing test with clear intent documented.
3. **Green step** — the minimal implementation with passing test output.
4. **Refactor notes** — structural improvements made and their rationale.
5. **Coverage summary** — test coverage delta after the session completes.
