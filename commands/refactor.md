---
description: Apply safe, incremental structural refactoring without changing behavior.
argument-hint: "file path or function name (e.g. src/auth/session.ts)"
---

## Usage
`/refactor [file or function]`

## Context
- Refactoring target (file path or function name): $ARGUMENTS (e.g. `src/auth/session.ts`).
- The existing test suite must pass before any refactoring begins.
- Current code structure, coupling, and complexity will be assessed before planning changes.

Load the `refactor` skill and follow it. Use $ARGUMENTS as the refactoring target; if omitted, default to the most recently changed code.

When structural improvements map to a design pattern, load the `design-pattern-adopter` skill. If uncovered paths are discovered, load the `tdd` skill to add tests before refactoring those paths and launch the `tdd-guide` agent if new behavior is required.

## Output Format
1. **Pre-refactor test status** — confirmation all tests passed before changes began.
2. **Structure assessment** — identified issues: coupling, complexity, design smells.
3. **Transformation plan** — ordered list of steps with rationale for each.
4. **Changes applied** — summary of each transformation made.
5. **Post-refactor test status** — confirmation all tests still pass after changes.

**Do not change behavior. Refactoring is structural improvement only. Commit behavioral fixes separately.**
