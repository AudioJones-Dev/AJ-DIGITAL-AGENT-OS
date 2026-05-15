# Phase 1 Implementation Plan (Archived)

> Archived 2026-05-15. Phase 1 work landed in commit `fe681f3`. Live status now lives in `ROADMAP.md` and `CHANGELOG.md`.

## Purpose

Phase 1 turns AJ Digital Agent OS from a Markdown baseline into a cleaner, machine-readable orchestration foundation while staying documentation-first.

## Scope

Phase 1 is limited to:

- Repo hygiene.
- Machine-readable registry files.
- Policy alignment between Markdown docs and YAML registry records.
- Validation planning.
- Dashboard/API requirements planning.

Phase 1 does not include:

- Modifying `PODCAST OS`.
- Installing dependencies.
- Building app code.
- Changing deployments.
- Changing DNS.
- Reading or changing secrets.

## Current Baseline

The repo already contains:

- Agent OS root documentation.
- Agent profiles.
- Shared schemas.
- Shared SOPs.
- Orchestration policies.
- Permission policies.
- Memory policies.
- Deployment docs.
- Integration docs.
- Prompt docs.

## Phase 1 Additions

The first hardening pass adds:

- `.gitattributes` for stable text normalization.
- `.gitignore` for local artifacts, dependency folders, env files, logs, and generated reports.
- `registry/` for machine-readable source-of-truth files.
- `registry/agents/podcast-os.yaml` for the first active product agent.
- `registry/domains.yaml` for domain and tenant routing records.
- `registry/integrations.yaml` for integration status and approval gates.

## Next Work Packages

### W1 - Registry Validation

Create a lightweight validation approach for registry YAML files.

Deliverables:

- YAML field requirements.
- Required status values.
- Required approval-gate values.
- Manual validation checklist.

No package installation is required for the planning version.

### W2 - Markdown and Registry Sync Rules

Define which Markdown files must be updated when registry values change.

Deliverables:

- Registry-to-doc mapping.
- Change checklist.
- Review requirements.

### W3 - Dashboard Requirements

Define the future `agents.ajdigital.app` dashboard without implementing it yet.

Deliverables:

- Page inventory.
- Registry fields required by the dashboard.
- Read-only status model.
- Approval-gated action model.

### W4 - API Requirements

Define the future `api.ajdigital.app` registry API without implementing it yet.

Deliverables:

- Read-only endpoint list.
- Authentication assumptions.
- Tenant-safety rules.
- Audit requirements.

## Manual Review Checklist

- Confirm `.gitattributes` and `.gitignore` fit the repo.
- Confirm YAML status values are acceptable.
- Confirm `Podcast OS` boundaries are accurate.
- Confirm domain and tenant patterns are still correct.
- Confirm integrations marked planned or optional are not overstated as production-ready.

## Recommended Commit

```powershell
git add .
git commit -m "Add Phase 1 registry and repo hygiene"
```

Push only after review.

