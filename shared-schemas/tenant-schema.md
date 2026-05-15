# Tenant Schema

## Purpose

The tenant schema defines how client-specific contexts are represented across AJ Digital agent products.

## Required Fields

| Field | Description |
| --- | --- |
| `tenant_id` | Stable tenant identifier. |
| `display_name` | Human-readable client or workspace name. |
| `primary_domain` | Tenant product domain, if assigned. |
| `product_contexts` | Product agents enabled for the tenant. |
| `data_boundaries` | Storage, privacy, and access boundaries. |
| `owner` | Accountable human owner. |
| `status` | Planned, onboarding, active, paused, archived. |
| `approval_policy` | Tenant-specific approval requirements. |

## Domain Pattern

```txt
clientname.podcastos.ajdigital.app
clientname.agents.ajdigital.app
```

Tenant routing must prevent cross-tenant data exposure.

