# Agent Manifest Schema

## Purpose

The agent manifest defines the minimum information required to register an AJ Digital agent in Agent OS.

## Required Fields

| Field | Description |
| --- | --- |
| `agent_id` | Stable lowercase identifier for the agent. |
| `name` | Human-readable agent name. |
| `status` | Planned, Active/In Development, Active, Paused, Deprecated. |
| `purpose` | One-sentence operating purpose. |
| `local_path` | Local workspace path, if applicable. |
| `product_url` | Primary product or dashboard URL. |
| `owner` | Human or team accountable for approval. |
| `code_boundary` | Where product code lives and what Agent OS may modify. |
| `approval_policy` | Link to required approval gates. |
| `integrations` | External tools or services used by the agent. |

## Notes

Agent manifests should be treated as registry inputs. Product code, secrets, and environment values do not belong in manifests.

