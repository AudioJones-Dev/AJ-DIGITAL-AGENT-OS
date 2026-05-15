# Cloudflare DNS Model

## Purpose

Cloudflare is the DNS and edge control plane for AJ Digital domains.

## Expected Records

- Apex and public routes for `audiojones.com`.
- Wildcard and product routes for `ajdigital.app`.
- Product subdomains such as `podcastos.ajdigital.app`.
- Tenant subdomains such as `clientname.podcastos.ajdigital.app`.

## Responsibilities

- Maintain DNS routing.
- Support wildcard routing where approved.
- Coordinate certificates and proxy settings.
- Protect production routes from unreviewed changes.

## Approval Rule

All DNS, proxy, certificate, redirect, firewall, and wildcard changes require explicit human approval.

