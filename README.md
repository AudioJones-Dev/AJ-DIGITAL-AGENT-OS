# AJ Digital Agent OS

AJ Digital Agent OS is the master orchestration and documentation layer for the AJ Digital agent ecosystem. It defines shared operating rules, agent registry data, domain topology, deployment assumptions, safety policies, and handoff prompts across agent products.

This repository documents and coordinates agent systems. It does not own product code for individual agents.

## Where to Start

Read these in order. They are the entry points for any operator or agent runner working in this repo.

1. [`CLAUDE.md`](CLAUDE.md) - operating contract for Claude (Claude Code, Claude CoWork).
2. [`AGENTS.md`](AGENTS.md) - runner-agnostic operating contract for Codex, Hermes, OpenClaw, and humans.
3. [`AGENT_OS_MASTER_SPEC.md`](AGENT_OS_MASTER_SPEC.md) - architecture and layer model.
4. [`docs/PRD.md`](docs/PRD.md) - what this product is and what "done" looks like for v1.
5. [`docs/DESIGN.md`](docs/DESIGN.md) - system design, today and target.
6. [`docs/SECURITY.md`](docs/SECURITY.md) - security and approval policy index (canonical files live in [`permissions/`](permissions)).
7. [`docs/DEPLOYMENT.md`](docs/DEPLOYMENT.md) - deployment and DNS index (canonical files live in [`deployment/`](deployment)).
8. [`docs/DECISIONS.md`](docs/DECISIONS.md) - architectural decision log.
9. [`ROADMAP.md`](ROADMAP.md) and [`CHANGELOG.md`](CHANGELOG.md) - phased plan and dated change log (root, canonical).

The machine-readable source of truth lives in [`registry/`](registry).

## Local Workspace

The expected operator workspace layout (Windows path shown; adapt for macOS or Linux as needed):

```txt
<workspace-root>/AJ DIGITAL AGENTS
|-- AJ-DIGITAL-AGENT-OS
|-- PODCAST OS
```

`AJ-DIGITAL-AGENT-OS` is the source of truth for cross-agent documentation, schemas, policies, and orchestration prompts.

`PODCAST OS` is an active product workspace for the AI Podcast Producer Agent. Product code remains in that folder and is referenced here only for registry and orchestration purposes.

## GitHub

Repository:

[https://github.com/AudioJones-Dev/AJ-DIGITAL-AGENT-OS.git](https://github.com/AudioJones-Dev/AJ-DIGITAL-AGENT-OS.git)

## Domain Architecture

- `audiojones.com` is the public brand, media, authority, content, and lead generation surface.
- `ajdigital.app` is the application surface for agents, dashboards, APIs, internal tools, and client portals.

Product and tenant domains are documented in [DOMAIN_TOPOLOGY.md](DOMAIN_TOPOLOGY.md).

## Operating Rule

Each product agent keeps its implementation in its own product repository or workspace. AJ Digital Agent OS records shared contracts, approval gates, routing rules, deployment patterns, and integration assumptions so the ecosystem can operate consistently without merging product code into this repo.

