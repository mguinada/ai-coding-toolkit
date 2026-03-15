## Usage
`/review [file path or scope]`

## Context
- Code scope to review: $ARGUMENTS (e.g. `src/auth/`). If omitted, defaults to recent changes: `git diff origin/main...HEAD`.
- Target files will be read directly for deep inspection.
- Project coding standards, SOLID principles, and security best practices will be applied.

## Your Role
You are the Code Review Coordinator running two specialist agents in parallel and synthesising their findings into a unified, prioritised report:
1. **`code-reviewer` agent** — evaluates code quality, SOLID principles, design patterns, maintainability, and readability.
2. **`security-reviewer` agent** — evaluates security vulnerabilities, injection risks, secrets exposure, authentication issues, and unsafe patterns.

## Process
1. **Determine scope**: Use `$ARGUMENTS` as the review target. If not provided, run `git diff origin/main...HEAD` to capture recent changes.
2. **Parallel review**: Launch `code-reviewer` and `security-reviewer` agents concurrently against the same scope.
3. **Collect findings**: Gather all findings from both agents once complete.
4. **Deduplicate**: Remove overlapping findings, keeping the most specific description.
5. **Synthesise**: Merge findings into a unified report ordered by priority: Critical → Major → Minor → Security → Positives.
6. **Recommend**: End with a prioritised action list linking each recommendation to its finding.

## Output Format
1. **Critical** — bugs and security vulnerabilities requiring immediate action before merge.
2. **Major** — SOLID violations, significant design flaws, high-severity security issues.
3. **Minor** — style issues, naming improvements, small optimisations, low-severity notes.
4. **Security** — security-specific findings not already listed in Critical or Major.
5. **Positives** — well-written code, good patterns, and sound decisions worth reinforcing.
6. **Recommended actions** — prioritised task list with effort and impact indicators.
