# Integration Schema

## Purpose

The integration schema records external tools, APIs, storage systems, and platforms connected to an AJ Digital agent.

## Required Fields

| Field | Description |
| --- | --- |
| `integration_id` | Stable integration identifier. |
| `name` | Human-readable integration name. |
| `provider` | Vendor or platform. |
| `status` | Planned, optional, active, paused, deprecated. |
| `used_by` | Agents or workflows that depend on the integration. |
| `data_access` | Data classes the integration can read or write. |
| `secret_requirements` | Environment variables or credentials required, without values. |
| `approval_required` | Actions that require human approval. |
| `runbook` | Link to setup or operational docs. |

## Secret Rule

Integration docs may name required secret keys but must never contain secret values.

