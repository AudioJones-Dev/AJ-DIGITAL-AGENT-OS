# Product Requirements - AJ Digital Agent OS

## What Is This Product

AJ Digital Agent OS is the coordination layer for the AJ Digital agent ecosystem. It is a shared operating system for documentation, registry, permissions, orchestration policy, and deployment topology across multiple product agents.

It is not an end-user product. Its users are operators, agent runners (Codex, Claude, Hermes, OpenClaw), and the product agents themselves (Podcast OS, SEO/AEO Agent, Diagnostics Agent, Signal OS, Hermes Control Plane).

## Why It Exists

Product agents are built and deployed independently, but they share:

- domain and tenant routing
- security and approval policy
- integration surface (Cloudflare, Vercel, GitHub, Neon, R2, Upstash, PostHog)
- agent-runner conventions (branch names, permission gates, validation)
- a registry that tells dashboards, APIs, and orchestrators what exists

Without a shared layer, every agent re-derives these answers and they drift. Agent OS is the single source of truth.

## Goals

1. **Discoverability.** Any new agent runner or human can read 3-5 files and know how to operate safely in this ecosystem.
2. **Registry-backed truth.** A machine-readable registry (`registry/*.yaml`) describes every agent, domain, and integration.
3. **Approval gates by default.** Destructive, operational, deployment, and secret actions require explicit human approval.
4. **Documentation-first.** Policy is written before code; code follows policy, not the other way around.
5. **No accidental coupling.** Product code stays in its product workspace. Agent OS records contracts only.

## Non-Goals

- Hosting product code for individual agents.
- Storing client data or production credentials.
- Replacing per-product PRDs, design docs, or roadmaps.
- Providing automated runtime enforcement (today). Enforcement is human-review based.

## Users and Their Jobs-To-Be-Done

| User | Job |
| --- | --- |
| Operator (human) | Set policy, approve actions, review agent work, decide architecture. |
| Agent runner (Codex, Claude Code) | Read the contract, work on a scoped task, request approval before risky actions. |
| Orchestrator (Hermes, future) | Look up agents and integrations from the registry; route tasks; enforce approval gates. |
| Product agent (Podcast OS, etc.) | Reference shared schemas, SOPs, and integration assumptions; stay consistent with the ecosystem. |

## Success Criteria for v1

v1 of Agent OS is "ready" when all of these are true:

- A new agent runner can land in the repo, read `AGENTS.md` or `CLAUDE.md`, and know how to operate without further onboarding.
- Every active or planned agent appears in `registry/agents/` with status, owner, product URL, and approval requirements.
- Every active integration appears in `registry/integrations.yaml` with status and approval gates.
- Domain and tenant routing for all live products is documented and matches `registry/domains.yaml`.
- Security policy is consolidated under `permissions/` with a clear `docs/SECURITY.md` index.
- A decision log (`docs/DECISIONS.md`) captures every settled architectural choice.
- No secrets, no client data, and no product code have been committed.

## Out of Scope for v1

- Automated YAML schema validation (planned, future work package W1).
- The `agents.ajdigital.app` dashboard (planned, future work package W3 / Phase 3).
- The `api.ajdigital.app` registry API (planned, future work package W4 / Phase 3).
- Hermes Control Plane runtime (Phase 2).

## Constraints

- No product code in this repo.
- No installed dependencies, no build tooling, no CI in v1.
- No secret values in any committed file.
- All destructive, operational, and deployment changes require human approval.
- Operator workflow is multi-platform; line endings normalized via `.gitattributes`.

## Related Documents

- `AGENT_OS_MASTER_SPEC.md` - architecture
- `ROADMAP.md` - phased plan
- `docs/DESIGN.md` - system design
- `docs/DECISIONS.md` - architectural decisions
- `docs/SECURITY.md` - security index
