# Registry

This folder contains machine-readable source-of-truth files for the AJ Digital Agent OS ecosystem.

Markdown files in the repository remain the human-readable policy and operating documentation. YAML files in this folder are intended to become the structured registry for dashboards, validation scripts, APIs, and orchestration tools.

## Files

- `agents/podcast-os.yaml`: first active agent record.
- `domains.yaml`: brand, app, product, API, admin, and tenant domain map.
- `integrations.yaml`: tool and platform integration inventory.

## Rules

- Do not store secrets in registry files.
- Do not point to private client data unless the tenant boundary is approved.
- Keep status values conservative until setup is verified.
- Update the matching Markdown docs when registry facts change.

