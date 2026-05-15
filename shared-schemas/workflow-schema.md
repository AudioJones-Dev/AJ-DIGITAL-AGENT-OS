# Workflow Schema

## Purpose

The workflow schema defines how an agent task moves from request to validated outcome.

## Required Fields

| Field | Description |
| --- | --- |
| `workflow_id` | Stable identifier for the workflow. |
| `name` | Human-readable workflow name. |
| `agent_id` | Agent responsible for the workflow. |
| `trigger` | Human request, schedule, webhook, event, or manual run. |
| `inputs` | Required input data and allowed sources. |
| `steps` | Ordered actions with tool and approval requirements. |
| `outputs` | Expected artifacts, reports, commits, or dashboard changes. |
| `validation` | Checks required before the workflow is considered complete. |
| `approval_gates` | Human approval gates that block execution. |
| `rollback_plan` | Recovery plan for production-facing changes. |

## Operating Rule

Workflows must separate read-only inspection from write actions. Any workflow that can modify code, data, deployments, remotes, or secrets must declare its approval gate.

