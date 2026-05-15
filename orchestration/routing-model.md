# Routing Model

## Purpose

The routing model defines how work should be assigned across humans, Codex, Claude, Hermes, OpenClaw, and product agents.

## Default Lanes

| Lane | Primary Use |
| --- | --- |
| Human operator | Final approval, production decisions, destructive actions, account access. |
| Codex Desktop | Local repo inspection, documentation edits, code changes, validation, Git-aware execution. |
| Claude CoWork | Planning, synthesis, documentation drafting, strategy, long-form reasoning. |
| Claude Code | Repo-aware code assistance when explicitly assigned. |
| Hermes Agent | Future orchestration, policy enforcement, memory, and routing layer. |
| OpenClaw | Future execution or routing component once implementation details are confirmed. |

## Routing Rule

Route each task to the least risky lane that can complete it. Any action that changes product code, secrets, deployments, data, or remotes must pass through the relevant approval gate.

