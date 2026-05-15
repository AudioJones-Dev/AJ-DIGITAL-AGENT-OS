# System Design - AJ Digital Agent OS

This document describes how Agent OS is structured today and how it is intended to evolve. For the high-level spec, see [`../AGENT_OS_MASTER_SPEC.md`](../AGENT_OS_MASTER_SPEC.md). For the phased plan, see [`../ROADMAP.md`](../ROADMAP.md). For settled architectural choices, see [`./DECISIONS.md`](./DECISIONS.md).

## Layers

Agent OS is organized into five layers, all expressed today as documentation plus a YAML registry:

1. **Registry** - canonical index of agents, domains, and integrations. (`registry/*.yaml`, `AGENT_REGISTRY.md`, `DOMAIN_TOPOLOGY.md`)
2. **Shared schemas** - Markdown contracts for agent manifests, workflows, tasks, tenants, approval gates, and integrations. (`shared-schemas/*.md`)
3. **Orchestration** - routing rules for Codex, Claude, Hermes, OpenClaw, and human operators. (`orchestration/*.md`, `prompts/*.md`)
4. **Permissions** - permission levels, approval gates, destructive-action policy, secrets policy. (`permissions/*.md`)
5. **Deployment topology** - domain ownership, tenant routing, DNS, hosting targets, env management. (`deployment/*.md`)

Each layer has Markdown for humans and (where it exists) YAML for machines. Markdown is the policy; YAML is the source of truth for tooling.

## Today's Architecture

```txt
Operator (human)
     |
     | reads / approves
     v
+---------------------------+        +-----------------------------+
|   Markdown policy docs    |  <-->  |   registry/*.yaml           |
|   (root + topic folders)  |        |   (machine-readable truth)  |
+---------------------------+        +-----------------------------+
     ^
     | reads (entry points)
     |
+---------------------------+
| Agent runners             |
|   - Codex (AGENTS.md)     |
|   - Claude (CLAUDE.md)    |
|   - Hermes  (planned)     |
|   - OpenClaw (planned)    |
+---------------------------+
```

There is no runtime today. Enforcement is human review. Validation is human review.

## Target Architecture (Phase 2 / Phase 3)

```txt
Operator (human)
     |
     v
+---------------------------+
|  agents.ajdigital.app     |   <-- read-only dashboard
+---------------------------+
            |
            v
+---------------------------+        +-----------------------------+
|  api.ajdigital.app        | -----> |  registry/*.yaml (or DB)    |
|  (registry API)           |        |  + audit log + memory       |
+---------------------------+        +-----------------------------+
            ^
            |
+---------------------------+
| Hermes Control Plane      |   <-- routing, approval enforcement
+---------------------------+
            ^
            |
+---------------------------+
| Agent runners             |
+---------------------------+
```

Phase 2 introduces the Hermes contract and storage requirements. Phase 3 introduces the dashboard and the registry API. Neither is built yet.

## Key Design Choices

See `docs/DECISIONS.md` for the full decision log. Highlights:

- **No product code in this repo** (ADR-0003). Agent OS records contracts; product workspaces own implementation.
- **Documentation-first registry** (ADR-0004). Markdown and YAML coexist; YAML is the structured truth.
- **Vercel + Cloudflare as defaults** (ADR-0002). Per-product overrides require an approved spec.
- **Domain split** (ADR-0001). `audiojones.com` for brand, `ajdigital.app` for apps and tenants.
- **Root-canonical roadmap and changelog** (ADR-0005). Not duplicated under `docs/`.

## Data Model

The registry today consists of three YAML files:

- `registry/agents/<agent>.yaml` - one file per agent product.
- `registry/domains.yaml` - brand, app, product, API, admin, and tenant domain map.
- `registry/integrations.yaml` - tool and platform inventory with status and approval gates.

Schema is informal. Required fields are enumerated in `shared-schemas/agent-manifest-schema.md`, `shared-schemas/integration-schema.md`, and `shared-schemas/tenant-schema.md`. Validation is a future work package; today it is human review against a checklist.

## Boundaries and Invariants

- The registry must never contain secret values - only variable names. Enforced by review (`permissions/secrets-policy.md`).
- Markdown policy and YAML registry must agree. Drift is a defect.
- Tenant subdomains must isolate tenant context; one client must never see another's data. Enforced at product-runtime, declared in `deployment/tenant-routing-model.md`.
- Active product code is never modified by Agent OS tasks unless explicitly authorized.

## Open Design Questions

- How will the future registry API authenticate orchestrators vs. operators vs. read-only dashboards?
- Where does audit log storage live - inside the registry repo, in a database, or in an event stream?
- How are schema migrations versioned once YAML moves from Markdown-defined to formally-validated?
- Does Hermes own approval-gate enforcement, or does it call into a separate policy service?

These are tracked at the level of "to be decided" until Phase 2 planning.
