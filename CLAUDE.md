# CLAUDE.md

Operating contract for Claude (Claude Code, Claude CoWork, and any Claude-powered runner) working in this repository.

Read this file before doing any work. If anything here conflicts with a user instruction, ask before acting.

## Repo Identity

AJ Digital Agent OS is a documentation, governance, and registry repository. It contains no product code. Product code for each agent (e.g. Podcast OS) lives in its own workspace.

Source-of-truth files:

- `AGENT_OS_MASTER_SPEC.md` - architecture and layer model.
- `AGENT_REGISTRY.md` - human-readable agent index.
- `DOMAIN_TOPOLOGY.md` - domain and tenant routing.
- `ROADMAP.md` - phased plan (root, canonical).
- `CHANGELOG.md` - dated change log (root, canonical).
- `registry/*.yaml` - machine-readable registry.
- `permissions/*.md` - canonical security and approval policy.
- `docs/SECURITY.md`, `docs/DEPLOYMENT.md` - indexes that point into canonical files.

## Default Permission Level

Read-only. Claude does not gain write, operational, or destructive permission unless the human task explicitly grants a narrower scope. See `permissions/permission-model.md`.

## Branch Convention

Work on a branch named `claude/<topic>-<date-or-suffix>`. Never push to `main` directly. Never push to a branch other than the one named in the task.

## Approval Gates

Explicit human approval is required before:

- deleting, renaming, moving, or overwriting files
- installing dependencies
- running migrations
- pushing to a remote
- changing environment variables or secrets
- modifying active product code in any sibling workspace
- changing deployment, DNS, or domain settings

See `permissions/human-approval-gates.md` and `permissions/destructive-action-policy.md`.

## Secrets

Do not read `.env` files unless the task explicitly authorizes it for that file. Do not print secret values. Do not paste credentials into documentation or commits. Document only variable names. See `permissions/secrets-policy.md`.

## Validation

There is no automated test suite, linter, or CI. Validation today is human review. When making documentation changes:

- Check that all internal Markdown links resolve to existing files.
- Run `git status` before reporting completion.
- Summarize the diff and list any files that were moved or archived.

## What to Read First

1. This file.
2. `AGENTS.md` (the runner-agnostic version).
3. `AGENT_OS_MASTER_SPEC.md`.
4. `permissions/permission-model.md`.
5. `shared-sops/repo-safety-sop.md`.
6. The task description.

## What Not to Do

- Do not introduce product code or build tooling without an approved task.
- Do not refresh archived docs in `docs/archive/` - they are historical.
- Do not duplicate `ROADMAP.md` or `CHANGELOG.md` under `docs/`. Root files are canonical.
- Do not absorb `permissions/*.md` content into `docs/SECURITY.md`. The index summarizes; the canonical files own the policy.
