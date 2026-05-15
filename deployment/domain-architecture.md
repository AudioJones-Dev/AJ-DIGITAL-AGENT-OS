# Domain Architecture

This is the canonical domain topology document for the AJ Digital agent ecosystem.

## Control Plane

Cloudflare is the DNS and domain control plane for AJ Digital agent domains.

## Brand and App Separation

```txt
audiojones.com = public brand, media, authority, content, lead generation
ajdigital.app  = apps, agents, dashboards, APIs, internal tools, client portals
```

## Wildcard Subdomain

```txt
*.ajdigital.app
```

The wildcard subdomain supports product, tenant, API, dashboard, and admin routing patterns.

## Application Subdomains

```txt
podcastos.ajdigital.app    = Podcast OS product
agents.ajdigital.app       = agent ecosystem dashboard
api.ajdigital.app          = API layer
admin.ajdigital.app        = internal admin
diagnostics.ajdigital.app  = diagnostic tooling
hermes.ajdigital.app       = orchestration / control layer
```

Product subdomains identify individual agent products.

## Tenant Pattern

```txt
clientname.podcastos.ajdigital.app
clientname.agents.ajdigital.app
```

Tenant subdomains identify a client context inside a product-specific domain.

## Routing Principles

- Brand and content live under `audiojones.com`.
- Agent applications and operational tools live under `ajdigital.app`.
- Public product marketing may link from `audiojones.com` into product surfaces under `ajdigital.app`.
- Tenant subdomains must resolve to product-specific tenant context and must not expose another client's data.

## Approval Rule

DNS, certificate, wildcard, product-domain, and tenant-routing changes require explicit human approval before execution.

