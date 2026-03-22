---
description: Scaffold or audit Docker configuration for the current project.
argument-hint: "service name (e.g. api, worker)"
---

## Usage
`/docker [service name]`

## Context
- Optional service name or target: $ARGUMENTS (e.g. `api`, `worker`).
- `Dockerfile` and `.dockerignore` will be checked for existence to determine scaffold vs audit path.
- Runtime and framework will be detected from `package.json`, `Gemfile`, `pyproject.toml`, or equivalent.

Load the `docker` skill and follow it. Use $ARGUMENTS as the service name if provided.

## Output Format
1. **Runtime summary** — detected language, version, and framework.
2. **Dockerfile** — generated or audited configuration with inline comments explaining key decisions.
3. **.dockerignore** — generated or audited exclusion list.
4. **Audit findings** (audit path only) — issues found grouped by severity with recommended fixes.
5. **Next actions** — build and test commands to validate the Docker setup locally.
