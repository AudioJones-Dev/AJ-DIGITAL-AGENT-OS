# Incident Response SOP

## Purpose

This SOP defines the first response pattern for agent, deployment, data, or domain incidents.

## Initial Response

1. Stop automated changes if the incident may be caused by an agent or deployment.
2. Preserve evidence: timestamps, URLs, logs, screenshots, command output, and recent changes.
3. Identify affected product, tenant, domain, and data class.
4. Escalate to the human operator before destructive remediation.
5. Apply the smallest safe fix.
6. Validate the affected route or workflow.
7. Record what happened and what changed.

## Approval Required

Approval is required before rollback, DNS changes, secret rotation, data repair, production redeploy, or destructive cleanup.

