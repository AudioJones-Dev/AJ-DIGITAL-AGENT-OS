# Approval Gate Schema

## Purpose

Approval gates define actions that require a human operator before an agent may proceed.

## Required Fields

| Field | Description |
| --- | --- |
| `gate_id` | Stable gate identifier. |
| `name` | Human-readable gate name. |
| `trigger_action` | Action that activates the gate. |
| `risk` | Why approval is required. |
| `approver` | Person or role that can approve. |
| `approval_format` | Written instruction, UI approval, PR review, or signed runbook step. |
| `evidence_required` | Context the agent must provide before approval. |
| `post_approval_validation` | Checks required after the approved action. |

## Default Gates

- Destructive filesystem action.
- Dependency installation.
- Migration or data mutation.
- Remote push.
- Deployment setting change.
- Secret or environment variable change.
- Active product code modification.

