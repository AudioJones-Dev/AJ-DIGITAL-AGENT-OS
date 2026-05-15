# Security

This document is an **index** into the canonical security, permission, and approval policy that lives in `permissions/`. It does not replace those documents.

If the index and a `permissions/*.md` file ever disagree, the file in `permissions/` wins.

## Canonical Policy Files

| Topic | Canonical File |
| --- | --- |
| Permission levels and defaults | [`permissions/permission-model.md`](../permissions/permission-model.md) |
| Destructive action approval | [`permissions/destructive-action-policy.md`](../permissions/destructive-action-policy.md) |
| Human approval gates | [`permissions/human-approval-gates.md`](../permissions/human-approval-gates.md) |
| Secrets handling | [`permissions/secrets-policy.md`](../permissions/secrets-policy.md) |
| Repo safety SOP | [`shared-sops/repo-safety-sop.md`](../shared-sops/repo-safety-sop.md) |
| Incident response SOP | [`shared-sops/incident-response-sop.md`](../shared-sops/incident-response-sop.md) |

## Summary

### Default Permission

Agents start at **read-only**. Write, operational, and destructive permission must be explicitly granted by a human task.

### Approval Required Before

- delete, rename, move, or overwrite files
- install dependencies
- run migrations
- push to a remote
- change environment variables or secrets
- modify active product code outside the approved task scope
- change deployment, DNS, or domain settings

### Secrets Rules

- Do not commit secrets.
- Do not print or paste secret values.
- Do not read `.env*` files unless the task explicitly authorizes that file.
- Document only variable names, never values.
- Treat any leaked credential as compromised; request rotation.

### Repo Safeguards Already in Place

- `.gitignore` excludes `.env`, `.env.*` (allowing only `.env.example` / `.env.template`).
- `.gitattributes` normalizes line endings and marks common binaries.
- No product code or executable build tooling lives in this repo, limiting blast radius.

## Reporting a Security Concern

This is a private governance repo. Security concerns should be raised directly to the repo owner via the channel agreed in the operator workspace. There is no public disclosure surface.

## What This Document Is Not

- Not a replacement for `permissions/*.md`.
- Not a runtime enforcement mechanism. Enforcement is human-review based today; automation is on the roadmap.
- Not a vulnerability disclosure policy.
