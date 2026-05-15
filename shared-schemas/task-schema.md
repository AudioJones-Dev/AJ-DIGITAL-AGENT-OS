# Task Schema

## Purpose

The task schema defines the smallest unit of work that can be assigned to an agent or operator.

## Required Fields

| Field | Description |
| --- | --- |
| `task_id` | Stable identifier or generated request ID. |
| `title` | Short task label. |
| `requester` | Human, system, or workflow that requested the task. |
| `scope` | Allowed folders, repos, systems, and data sources. |
| `out_of_scope` | Explicitly prohibited areas. |
| `risk_level` | Low, medium, high, or production-critical. |
| `allowed_actions` | Inspection, file creation, edits, tests, deploys, or reporting. |
| `blocked_actions` | Actions requiring explicit approval or not allowed. |
| `expected_output` | Final report, artifact, patch, PR, or other outcome. |
| `validation` | Commands, checks, screenshots, reviews, or manual gates. |

## Notes

Tasks should be narrow enough that the agent can state what changed, what was skipped, what was verified, and what still needs human approval.

