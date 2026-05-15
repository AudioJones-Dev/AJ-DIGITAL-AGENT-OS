# Environment Variable Model

## Purpose

The environment variable model defines how configuration should be described without exposing values.

## Rules

- Do not commit `.env` files.
- Do not print secret values.
- Document variable names, purpose, and required environment only.
- Keep local, preview, and production values separate.
- Require approval before changing environment values.
- Prefer platform-managed secret storage for production.

## Documentation Pattern

| Variable | Purpose | Environment | Status |
| --- | --- | --- | --- |
| `DATABASE_URL` | Database connection string | Preview/Production | Planned |
| `POSTHOG_KEY` | Product analytics key | Preview/Production | Optional |
| `UPSTASH_REDIS_REST_URL` | Redis or queue endpoint | Preview/Production | Optional |

Values must be stored outside this repo.

