# Domain Topology

## Primary Domains

```txt
audiojones.com = public brand, authority, content, lead generation
ajdigital.app = apps, agents, dashboards, APIs, internal tools, client portals
```

## Application Subdomains

```txt
podcastos.ajdigital.app = Podcast OS product
agents.ajdigital.app = agent ecosystem dashboard
api.ajdigital.app = API layer
admin.ajdigital.app = internal admin
diagnostics.ajdigital.app = diagnostic tooling
hermes.ajdigital.app = orchestration/control layer
```

## Tenant Model

```txt
clientname.podcastos.ajdigital.app
clientname.agents.ajdigital.app
```

## Routing Principles

- Brand and content live under `audiojones.com`.
- Agent applications and operational tools live under `ajdigital.app`.
- Public product marketing may link from `audiojones.com` into product surfaces under `ajdigital.app`.
- Tenant subdomains must resolve to product-specific tenant context and must not expose another client's data.

