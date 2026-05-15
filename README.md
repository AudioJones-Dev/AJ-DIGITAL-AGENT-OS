# AJ Digital Agent OS

AJ Digital Agent OS is the master orchestration and documentation layer for the AJ Digital agent ecosystem. It defines shared operating rules, agent registry data, domain topology, deployment assumptions, safety policies, and handoff prompts across agent products.

This repository documents and coordinates agent systems. It does not own product code for individual agents.

## Local Workspace

```txt
C:\dev\AJ DIGITAL AGENTS
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

