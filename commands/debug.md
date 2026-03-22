---
description: Investigate a bug using root-cause-first methodology.
argument-hint: "error message, failing test, or symptom"
---

## Usage
`/debug [error or symptom description]`

## Context
- Error message, failing test, or symptom: $ARGUMENTS (e.g. `TypeError: Cannot read properties of undefined at login`).
- Relevant source files and test files will be read as the investigation progresses.
- Logs, stack traces, and environment configuration will be examined during the Locate phase.

Load the `debug` skill and follow it.

After the fix is confirmed, load the `refactor` skill for cleanup if needed, and load the `tdd` skill to add regression tests if coverage was missing.

## Output Format
1. **Reproduction case** — minimal reproducible example or failing test with confirmed deterministic output.
2. **Root cause analysis** — clear explanation of what went wrong and where in the execution path.
3. **Fix applied** — the change made (file, line, before/after) with rationale.
4. **Verification result** — test suite output confirming the fix and no regressions.
5. **Follow-up actions** — any refactoring or regression tests recommended post-fix.
