# AGENTS.md

Runner-agnostic operating contract for any agent runner working in this repository (Codex, Claude Code, Hermes, OpenClaw, or human operators using an agent-style workflow).

This file is the entry point for non-Claude agents. Claude-specific guidance lives in `CLAUDE.md`. The two files share the same rules; if they ever diverge, this file is canonical for non-Claude runners.

## Repo Identity

AJ Digital Agent OS is a documentation, governance, and registry repository. No product code lives here. Product agents (e.g. Podcast OS) keep code in their own workspaces and are referenced from this repo via the registry.

## Default Permission Level

Read-only. An agent does not gain write, operational, or destructive permission unless the human task explicitly grants a narrower scope.

See `permissions/permission-model.md` for the level definitions.

## Branch Convention

- `main` is protected. Never push directly.
- Work branches: `<runner>/<topic>-<date-or-suffix>` (e.g. `codex/registry-cleanup-2026-05-15`, `claude/docs-readiness-bootstrap-2026-05-15`).
- Never push to a branch other than the one named in the active task.

## Approval Gates

Explicit human approval required before:

- deleting, renaming, moving, or overwriting files
- installing dependencies
- running migrations
- pushing to a remote
- changing environment variables or secrets
- modifying active product code in any sibling workspace
- changing deployment, DNS, or domain settings

See `permissions/human-approval-gates.md` and `permissions/destructive-action-policy.md`.

## Secrets

- Do not read `.env*` files unless explicitly authorized for that file.
- Do not print, paste, or commit secret values.
- Document credentials by variable name only.
- Treat any pasted credential as compromised and request rotation.

See `permissions/secrets-policy.md`.

## Registry Discipline

- `registry/*.yaml` is the machine-readable source of truth.
- Markdown docs (`AGENT_REGISTRY.md`, `DOMAIN_TOPOLOGY.md`, `integrations/*.md`) must stay consistent with registry YAML.
- Do not introduce a new agent, integration, or domain without updating both the registry file and the matching Markdown doc.

## Validation

- No automated CI exists today. Human review is the validation loop.
- Before reporting a task complete: run `git status`, summarize the diff, and verify internal Markdown links resolve.

## What to Read First

1. This file.
2. `CLAUDE.md` (if running as Claude).
3. `AGENT_OS_MASTER_SPEC.md`.
4. `permissions/permission-model.md`.
5. `shared-sops/repo-safety-sop.md`.
6. The active task description.

## Runner-Specific Prompts

Detailed runner prompts live in `prompts/`:

- `prompts/codex-orchestration-prompt.md`
- `prompts/claude-cowork-prompt.md`
- `prompts/hermes-agent-prompt.md`
- `prompts/repo-audit-prompt.md`
