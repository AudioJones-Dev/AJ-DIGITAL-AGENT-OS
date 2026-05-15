# Registry Schemas

JSON Schema (Draft 2020-12) definitions used to validate the YAML files in `registry/`.

These schemas are the first deliverable of Phase 1 work package **W1 - Registry Validation** from [PHASE_1_IMPLEMENTATION_PLAN.md](../../PHASE_1_IMPLEMENTATION_PLAN.md).

## Files

| Schema | Validates |
| --- | --- |
| `agent.schema.json` | Every file under `registry/agents/*.yaml`. |
| `domains.schema.json` | `registry/domains.yaml`. |
| `integrations.schema.json` | `registry/integrations.yaml`. |

## How validation runs

The `.github/workflows/validate.yml` workflow runs [`check-jsonschema`](https://github.com/python-jsonschema/check-jsonschema) against each YAML file on every pull request that touches `registry/**` or `**.md`.

To run the same checks locally:

```bash
pipx install check-jsonschema

check-jsonschema --schemafile registry/schemas/agent.schema.json registry/agents/*.yaml
check-jsonschema --schemafile registry/schemas/domains.schema.json registry/domains.yaml
check-jsonschema --schemafile registry/schemas/integrations.schema.json registry/integrations.yaml
```

## Status vocabulary

Agent and subdomain `status` values are constrained to:

- `planned`
- `active_in_development`
- `active`
- `paused`
- `deprecated`

This mirrors the vocabulary in [shared-schemas/agent-manifest-schema.md](../../shared-schemas/agent-manifest-schema.md).

Integration `status` values are constrained to:

- `planned`
- `planned_optional`
- `planned_active`
- `active_planned`
- `active`

Top-level domain `status` (the `domains.brand.status` and `domains.app.status` entries) is intentionally left as a free-form string. These describe a surface's role rather than an agent lifecycle stage and use bespoke values like `existing_brand_surface` and `agent_application_surface`.

## Approval-gate vocabulary

Agent `approval_gates` entries are constrained to the canonical list in [AGENT_OS_MASTER_SPEC.md](../../AGENT_OS_MASTER_SPEC.md) plus the additional operational gates currently used by `registry/agents/podcast-os.yaml`:

- `delete`
- `rename`
- `move`
- `overwrite`
- `install_dependencies`
- `run_migrations`
- `push_to_remote`
- `change_env_variables`
- `modify_secrets`
- `modify_active_app_code`
- `change_deployment_settings`

## Known drift not enforced by these schemas

The schemas validate the current YAML as written. They do **not** yet enforce:

1. **Agent-manifest field naming.** `shared-schemas/agent-manifest-schema.md` calls for `owner`, `code_boundary`, and `approval_policy` fields. The YAML uses `ownership`, `boundaries`, and `approval_gates`. The schema follows the YAML for now; reconciling the doc and the registry is tracked under Phase 1 W2.
2. **Status-value duplication.** `integrations.yaml` uses both `active_planned` and `planned_active`. Both are accepted by the schema until the canonical value is chosen.
3. **Cross-file referential integrity.** `domains.yaml` may reference an `agent_id` (e.g. `diagnostics-agent`, `hermes-control-plane`) that has no corresponding file in `registry/agents/`. JSON Schema cannot express this constraint across files; it is a candidate for a follow-up custom check.
4. **Registry-to-Markdown sync.** Drift between registry YAML and the narrative Markdown docs (e.g. `DOMAIN_TOPOLOGY.md`, `integrations/tool-stack.md`) is W2 territory and is not enforced here.
