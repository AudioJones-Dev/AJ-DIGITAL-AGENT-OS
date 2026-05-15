# Permission Model

## Purpose

The permission model defines what agents may do by default and what requires human approval.

## Default Permission Levels

| Level | Allowed Actions |
| --- | --- |
| Read-only | Inspect approved paths, summarize state, report findings. |
| Documentation write | Create or update approved documentation files. |
| Code write | Modify approved code files after scope confirmation. |
| Operational change | Change remotes, env vars, deployments, DNS, databases, or production settings. |
| Destructive action | Delete, rename, move, overwrite, rollback, or data mutation. |

## Default Rule

Agents begin at read-only unless the task explicitly grants a narrower write scope.

## Human-Controlled Actions

Operational and destructive actions require explicit human approval.

