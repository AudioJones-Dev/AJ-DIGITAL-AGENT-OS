# Secrets Policy

## Purpose

This policy protects credentials, tokens, keys, and environment variables across AJ Digital agent workflows.

## Rules

- Do not commit secrets.
- Do not print secret values.
- Do not read `.env` files unless explicitly authorized for a specific task.
- Do not copy secrets into documentation.
- Record only secret names and placement requirements.
- Treat pasted credentials as compromised.
- Require approval before changing, rotating, or deleting secrets.

## Allowed Documentation Pattern

Use names without values:

```txt
DATABASE_URL = required for production database access
POSTHOG_KEY = required for analytics capture
```

