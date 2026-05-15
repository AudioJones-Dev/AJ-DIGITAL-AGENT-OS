# Deployment SOP

## Purpose

This SOP defines the default deployment posture for AJ Digital agents.

## Default Flow

1. Confirm the product domain and target environment.
2. Verify Git state and review uncommitted changes.
3. Confirm required environment variables exist without printing values.
4. Run approved validation commands.
5. Require human approval before deployment or promotion.
6. Capture the deployment URL, status, and rollback plan.
7. Verify the live route after deployment.

## Hard Gates

- No production deployment without explicit approval.
- No deployment setting changes without approval.
- No environment variable changes without approval.
- No migration or data mutation without approval.

