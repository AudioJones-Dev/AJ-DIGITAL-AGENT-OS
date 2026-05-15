# Hermes Orchestration

## Purpose

Hermes is planned as the control-plane layer for AJ Digital agents. It should coordinate routing, memory, policy checks, audit trails, and agent task handoffs.

## Planned Responsibilities

- Resolve which agent or tool should handle a request.
- Check task scope against permission policies.
- Require human approval for gated actions.
- Track agent actions and results.
- Connect memory retrieval to agent context.
- Surface agent ecosystem status through `hermes.ajdigital.app`.

## Constraints

Hermes must not bypass human approval gates. It should record and enforce boundaries rather than silently taking privileged actions.

