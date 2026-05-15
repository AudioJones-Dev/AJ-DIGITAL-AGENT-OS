# Tenant Routing Model

## Purpose

The tenant routing model defines how client-specific routes should map into agent products.

## Patterns

```txt
clientname.podcastos.ajdigital.app
clientname.agents.ajdigital.app
```

## Requirements

- Resolve tenant from a verified subdomain.
- Load only that tenant's configuration and data.
- Prevent cross-tenant data access.
- Record tenant ownership and status.
- Require approval before creating production tenant routes.

## Initial Products

Podcast OS is the first active product expected to use tenant-aware routing.

