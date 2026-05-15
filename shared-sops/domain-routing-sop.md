# Domain Routing SOP

## Purpose

This SOP defines how domains and subdomains should be planned for AJ Digital agent products.

## Routing Model

- `audiojones.com` is public brand, authority, content, and lead generation.
- `ajdigital.app` is apps, agents, dashboards, APIs, internal tools, and client portals.
- Product subdomains should use direct product names, such as `podcastos.ajdigital.app`.
- Tenant subdomains should follow `clientname.product.ajdigital.app`.

## Change Process

1. Confirm the domain purpose.
2. Confirm Cloudflare DNS ownership.
3. Confirm the hosting target.
4. Record the routing decision in [`deployment/domain-architecture.md`](../deployment/domain-architecture.md).
5. Get approval before DNS, hosting, or certificate changes.

