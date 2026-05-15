# Retrieval Policy

## Purpose

The retrieval policy defines how agents should use prior context while avoiding stale or unsafe assumptions.

## Rules

- Search current source files first when implementation details may have changed.
- Use memory for durable preferences, decisions, and historical context.
- Mark older facts as memory-derived when not verified in the current workspace.
- Do not retrieve or expose secrets.
- Keep retrieval scoped to the active task.
- Prefer direct evidence over broad summaries for production-impacting decisions.

## Validation

If a memory-derived fact affects code, deployment, domains, secrets, or production readiness, verify it against the live workspace before acting.

