# Destructive Action Policy

## Purpose

This policy defines actions that require explicit human approval before an agent may proceed.

## Explicit Approval Required

- Delete.
- Rename.
- Move.
- Overwrite.
- Install dependencies.
- Run migrations.
- Push to remote.
- Change env variables.
- Modify secrets.
- Modify active app code.
- Change deployment settings.

## Operating Rule

If the agent is unsure whether an action is destructive or production-affecting, it must stop and ask for approval before proceeding.

## Reporting Rule

When approval is granted, the agent must report what was changed, what validation ran, and what rollback path remains available.

