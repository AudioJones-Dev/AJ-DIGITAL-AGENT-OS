# Domain Architecture

## Control Plane

Cloudflare is the DNS and domain control plane for AJ Digital agent domains.

## Wildcard Subdomain

```txt
*.ajdigital.app
```

The wildcard subdomain supports product, tenant, API, dashboard, and admin routing patterns.

## Product Pattern

```txt
podcastos.ajdigital.app
```

Product subdomains identify individual agent products.

## Tenant Pattern

```txt
clientname.podcastos.ajdigital.app
```

Tenant subdomains identify a client context inside a product-specific domain.

## Brand and App Separation

```txt
audiojones.com = public brand, media, content, lead generation
ajdigital.app = apps, agents, dashboards, APIs, internal tools, client portals
```

## Approval Rule

DNS, certificate, wildcard, product-domain, and tenant-routing changes require explicit human approval before execution.

