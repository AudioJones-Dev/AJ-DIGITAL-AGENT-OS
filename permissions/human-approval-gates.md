# Human Approval Gates

## Purpose

Human approval gates protect production systems, client data, active product code, and workspace integrity.

## Required Approval Events

- Destructive filesystem actions.
- Dependency installation.
- Migration or database mutation.
- Remote push.
- Environment variable changes.
- Secret creation, rotation, or deletion.
- Deployment setting changes.
- DNS or domain changes.
- Active app code changes outside the approved task.

## Approval Evidence

Before requesting approval, the agent should provide:

- Current state.
- Intended action.
- Affected files, systems, or domains.
- Risk and rollback notes.
- Validation plan.

