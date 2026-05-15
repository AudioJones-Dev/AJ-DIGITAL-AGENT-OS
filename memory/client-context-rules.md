# Client Context Rules

## Purpose

Client context rules prevent cross-client leakage and keep tenant-specific work scoped.

## Rules

- Keep client data tied to the correct tenant.
- Do not reuse private client context in another tenant.
- Do not expose client details in public documentation.
- Confirm tenant before acting on client-specific tasks.
- Avoid storing sensitive client records in general memory.
- Require approval before connecting client data to external integrations.

## Tenant Reminder

Tenant domains must resolve to only the relevant client context:

```txt
clientname.podcastos.ajdigital.app
clientname.agents.ajdigital.app
```

