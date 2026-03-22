---
description: Run multi-layer pre-flight checks and produce an explicit Go / No-Go deployment verdict.
argument-hint: "deployment target or environment (e.g. production, staging)"
---

## Usage
`/deploy-check [deployment target or environment]`

## Context
- Deployment target or environment: $ARGUMENTS (e.g. `production`, `staging`, `hotfix/auth-fix`).
- Application code, configuration files, Dockerfiles, and infrastructure definitions will be read directly.
- Pending migrations, environment variables, and CI/CD pipeline state will be examined.

## Process

1. **Determine scope**: Use $ARGUMENTS as the deployment target. If omitted, default to the current branch against `origin/main`.

2. **Quality Assurance**: Load the `tdd` skill to confirm the full test suite passes with no skipped or pending tests that cover changed paths. Launch the `e2e-runner` agent to validate critical user journeys end-to-end. Flag any coverage gaps in code touched by this deployment.

3. **Security audit**: Launch the `security-reviewer` agent to scan changed files for OWASP Top 10 vulnerabilities, hardcoded secrets, and auth/authz issues. Validate dependency versions for known CVEs. Check environment variable handling and secrets management.

4. **Operations check**: Load the `docker` skill to verify Dockerfile correctness, image build hygiene, and health check definitions. If database migrations are present, launch the `database-reviewer` agent to assess migration safety, reversibility, and lock risk. Confirm environment variables, feature flags, and external service configuration are deployment-ready.

5. **Risk assessment**: Synthesise all findings. Classify each issue as a **blocker** (must fix before deploy), **warning** (acceptable with mitigation), or **note** (non-blocking observation). Produce the Go/No-Go verdict.

6. **Deployment plan**: If Go, provide the ordered deployment steps with verification checkpoints and rollback trigger conditions.

## Output Format

1. **Readiness Report** — pass/fail matrix across QA, Security, Operations dimensions. One-line status per check.
2. **Blockers** — issues that must be resolved before this deployment proceeds. Zero tolerance.
3. **Warnings** — risks acceptable with documented mitigation or monitoring.
4. **Deployment Plan** — ordered execution steps with rollback procedure at each stage.
5. **Monitoring Checklist** — post-deployment health signals to watch in the first 30 minutes.
6. **Go / No-Go** — explicit verdict with the conditions that determined it.

**This command validates deployment readiness. To fix identified issues use `/debug`, `/review`, or `/refactor`.**
