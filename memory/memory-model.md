# Memory Model

## Purpose

The memory model defines how agent context should be captured, retrieved, and bounded.

## Memory Types

- Operator preferences.
- Workspace decisions.
- Agent registry facts.
- Tenant context.
- Product architecture notes.
- Incident and deployment history.
- Validation evidence.

## Rules

- Do not store secrets in memory.
- Separate tenant-specific context from global context.
- Mark unverified memory as possibly stale.
- Prefer current repo inspection over old memory when the fact may have changed.
- Record decisions with dates and source context.

