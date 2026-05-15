# Deployment

This document is an **index** into the canonical deployment, DNS, domain, and environment-variable models that live in `deployment/`. It does not replace those documents.

If the index and a `deployment/*.md` file ever disagree, the file in `deployment/` wins.

## Canonical Deployment Files

| Topic | Canonical File |
| --- | --- |
| Web app hosting (default: Vercel) | [`deployment/vercel-deployment-model.md`](../deployment/vercel-deployment-model.md) |
| DNS and domain control (Cloudflare) | [`deployment/cloudflare-dns-model.md`](../deployment/cloudflare-dns-model.md) |
| Domain architecture | [`deployment/domain-architecture.md`](../deployment/domain-architecture.md) |
| Tenant routing | [`deployment/tenant-routing-model.md`](../deployment/tenant-routing-model.md) |
| Environment variables | [`deployment/environment-variable-model.md`](../deployment/environment-variable-model.md) |
| Domain topology overview | [`../DOMAIN_TOPOLOGY.md`](../DOMAIN_TOPOLOGY.md) |
| Deployment SOP | [`../shared-sops/deployment-sop.md`](../shared-sops/deployment-sop.md) |

## Summary

### Hosting Targets

- **Vercel** is the default for web apps, agent dashboards, API routes, and serverless functions, unless a product-specific spec chooses another target.
- **Cloudflare** is the DNS, wildcard routing, and edge-control plane.
- Optional / planned data services: **Neon** (Postgres), **Cloudflare R2** (object storage), **Upstash** (Redis/queues), **PostHog** (analytics).

### Domain Layout

- `audiojones.com` - public brand, authority, content, lead generation.
- `ajdigital.app` - apps, agents, dashboards, APIs, internal tools, client portals.
- Product subdomains: `<product>.ajdigital.app` (e.g. `podcastos.ajdigital.app`).
- Tenant subdomains: `<client>.<product>.ajdigital.app`.

### Approval Gates for Deployment

Explicit human approval is required before:

- deploying to production
- promoting a preview to production
- changing project settings
- changing environment variables
- changing DNS, wildcard, certificate, or firewall rules
- creating or destroying databases, buckets, or queues

See [`../permissions/destructive-action-policy.md`](../permissions/destructive-action-policy.md) and [`../permissions/human-approval-gates.md`](../permissions/human-approval-gates.md).

### Environment Variables

- Managed outside this repo.
- Never committed.
- Documented by name only, never by value.
- See [`deployment/environment-variable-model.md`](../deployment/environment-variable-model.md) and [`../permissions/secrets-policy.md`](../permissions/secrets-policy.md).

## What This Document Is Not

- Not a deployment runbook for any specific product.
- Not a replacement for the per-topic files in `deployment/`.
- Not a record of currently-deployed environments. Status is tracked in [`../registry/integrations.yaml`](../registry/integrations.yaml) and [`../integrations/tool-stack.md`](../integrations/tool-stack.md).
