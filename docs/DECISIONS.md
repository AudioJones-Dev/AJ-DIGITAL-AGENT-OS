# Architectural Decisions

A lightweight decision log so future agents and operators do not re-litigate settled choices. Each entry should capture: date, decision, context, and consequences. Newest at the top.

Entries are append-only. If a decision is reversed, add a new entry that supersedes the old one rather than editing history.

---

## ADR-0006 - 2026-05-15 - Bootstrap readiness docs (`CLAUDE.md`, `AGENTS.md`, `docs/`)

**Decision.** Add a project-level Claude operating contract (`CLAUDE.md`), a runner-agnostic agent contract (`AGENTS.md`), and a `docs/` folder containing index-style readiness docs (`SECURITY.md`, `DEPLOYMENT.md`, `DESIGN.md`, `PRD.md`, `DECISIONS.md`).

**Context.** A repo readiness audit on 2026-05-15 found that operating rules were spread across many small files, with no concise contract any agent runner could read first. Stale planning docs (`WORKSPACE_AUDIT.md`, `PHASE_1_IMPLEMENTATION_PLAN.md`) were also present at the root.

**Consequences.** Agents now have a single entry point. The four `permissions/*.md` files remain canonical for security policy; `docs/SECURITY.md` is an index, not a replacement. `WORKSPACE_AUDIT.md` and `PHASE_1_IMPLEMENTATION_PLAN.md` archived under `docs/archive/`.

---

## ADR-0005 - 2026-05-15 - `ROADMAP.md` and `CHANGELOG.md` stay at the repo root

**Decision.** Keep `ROADMAP.md` and `CHANGELOG.md` at the repository root. Do not duplicate them under `docs/`. If `docs/ROADMAP.md` or `docs/CHANGELOG.md` are ever needed, they must be one-line pointers back to the root files.

**Context.** Convention conflict: some readiness templates expect `docs/ROADMAP.md` and `docs/CHANGELOG.md`. Operator preference is root-only to avoid drift between two copies.

**Consequences.** Tooling and templates that expect `docs/ROADMAP.md` will need to be adapted, not the repo.

---

## ADR-0004 - 2026-05-14 - Documentation-first registry (Markdown + YAML)

**Decision.** Maintain a Markdown layer for human-readable policy and a parallel YAML layer in `registry/` for machine-readable source of truth.

**Context.** Phase 1 needed a path from prose-only documentation to validated structured data without committing to a build system or framework yet.

**Consequences.** Two artifacts must be kept in sync (`AGENT_REGISTRY.md` ↔ `registry/agents/*.yaml`, `DOMAIN_TOPOLOGY.md` ↔ `registry/domains.yaml`, `integrations/*.md` ↔ `registry/integrations.yaml`). Sync rules are owned by future work package W2.

---

## ADR-0003 - 2026-05-14 - No product code in Agent OS

**Decision.** This repository documents and coordinates agent products. It does not own product code for individual agents.

**Context.** Each agent (Podcast OS first) has its own workspace. Merging product code into Agent OS would couple lifecycles and inflate blast radius.

**Consequences.** Agent OS edits never modify sibling product workspaces unless a task explicitly permits it. Cross-cutting contracts (schemas, SOPs, prompts) live here; implementation does not.

---

## ADR-0002 - 2026-05-14 - Default hosting and DNS targets

**Decision.** Vercel is the default web hosting target unless a product spec chooses another. Cloudflare is the DNS and domain control plane.

**Context.** Need a consistent baseline so agent products do not each pick incompatible infrastructure.

**Consequences.** Deviations require a product-specific spec and approval. Documented in `deployment/vercel-deployment-model.md` and `deployment/cloudflare-dns-model.md`.

---

## ADR-0001 - 2026-05-14 - Domain split: `audiojones.com` vs `ajdigital.app`

**Decision.** `audiojones.com` is the public brand, content, and lead-generation surface. `ajdigital.app` is the application surface for agents, dashboards, APIs, internal tools, and client portals.

**Context.** Need a clear separation between marketing and application traffic, and a stable home for tenant subdomains.

**Consequences.** Tenant routing uses `clientname.<product>.ajdigital.app`. Documented in `DOMAIN_TOPOLOGY.md` and `registry/domains.yaml`.
