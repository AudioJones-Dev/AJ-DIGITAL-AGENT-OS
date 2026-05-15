# Agent Onboarding SOP

## Purpose

This SOP defines the minimum steps for adding a new agent to AJ Digital Agent OS.

## Steps

1. Confirm the agent purpose, owner, and product boundary.
2. Add the agent to `AGENT_REGISTRY.md`.
3. Create an agent profile in `agents/`.
4. Document product URL, local path, status, and approval gates.
5. Identify required integrations without recording secret values.
6. Add or update shared schemas only when the agent introduces a reusable contract.
7. Review destructive action, deployment, and secrets policies before any implementation work.

## Done Criteria

- Agent has a registry row.
- Agent has an owner and status.
- Product code boundary is documented.
- Required approval gates are clear.

