# Agent OS Master Spec

## Purpose

AJ Digital Agent OS is the overarching coordination layer for AJ Digital agent products. It defines the common language, registry, safety model, domain map, memory rules, and operational policies that let individual agents work as part of one governed ecosystem.

## Architecture

The system is organized into five layers:

1. Agent registry: canonical list of agent products, local paths, public URLs, statuses, and responsibilities.
2. Shared schemas: common definitions for agent manifests, workflows, tasks, tenants, approval gates, and integrations.
3. Orchestration: routing rules for Codex, Claude, Hermes, OpenClaw, and future coordination services.
4. Permissions: human approval gates, destructive action limits, secrets handling, and environment-change policies.
5. Deployment topology: domain ownership, tenant routing, DNS assumptions, hosting targets, and environment management.

## Agent Ecosystem Model

Each agent can have a product surface, a code workspace, an operations profile, and a deployment destination. Agent OS does not absorb that implementation. It records how the agent is registered, routed, governed, and connected.

Initial agents:

- Podcast OS
- SEO/AEO Agent
- Diagnostics Agent
- Signal OS
- Hermes Control Plane

## Shared Schemas

Shared schemas live in `shared-schemas/` and define common Markdown contracts before code-level schemas are introduced. These schemas should be treated as policy-facing source documents for future JSON, TypeScript, database, or API implementations.

## Permissions

Permissions are documented in `permissions/`. Destructive actions, deployment changes, secret handling, dependency installation, and remote pushes require explicit human approval unless a later approved policy narrows the scope.

## Human Approval Gates

Human approval is required before:

- Deleting, renaming, moving, or overwriting files.
- Installing dependencies.
- Running migrations.
- Pushing to a remote.
- Changing environment variables or secrets.
- Modifying active app code.
- Changing deployment settings.

## Domain Topology

`audiojones.com` is the public brand and media surface.

`ajdigital.app` is the application and agent surface.

Detailed product, API, admin, and tenant routing rules are documented in [deployment/domain-architecture.md](deployment/domain-architecture.md).

## Tool Stack

The expected ecosystem includes Codex Desktop, Claude CoWork, Claude Code, Hermes Agent, OpenClaw, Obsidian, GitHub, Cloudflare, Vercel, Neon, Cloudflare R2, Upstash, and PostHog. Production status is tracked in [integrations/tool-stack.md](integrations/tool-stack.md).

## Deployment Assumptions

- Cloudflare is the DNS and domain control plane.
- Vercel is the default web app hosting target unless a product spec says otherwise.
- `*.ajdigital.app` supports product and tenant subdomains.
- Environment variables are managed outside this repo and are never committed.

## Productization Direction

Agent OS should mature from documentation into an operational control layer with registry-backed routing, approval gates, tenant-aware deployment maps, shared memory retrieval, and dashboard surfaces for monitoring agent products.

