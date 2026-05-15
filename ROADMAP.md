# Roadmap

## Phase 0 - Documentation Foundation

- Create the Agent OS documentation structure.
- Register Podcast OS as the first active product agent.
- Document domain topology, permission model, tool stack, and deployment assumptions.
- Keep all active product code outside this repo.

## Phase 1 - Registry and Policy Hardening

- Convert the Markdown registry into a validated structured manifest.
- Add explicit ownership and status fields for every agent.
- Define required approval gates for each agent lifecycle stage.
- Add operational review checklists for onboarding, deployment, and incident response.

## Phase 2 - Orchestration Runtime Planning

- Define the Hermes control-plane contract.
- Model Codex, Claude, OpenClaw, and human operator routing.
- Draft API boundaries for agent registry lookup and task dispatch.
- Identify storage requirements for memory, events, and audit logs.

## Phase 3 - Productization

- Build an agent ecosystem dashboard at `agents.ajdigital.app`.
- Add tenant-aware routing documentation and implementation specs.
- Connect observability, analytics, and incident workflows.
- Promote approved integrations from planned to active as they are verified.

