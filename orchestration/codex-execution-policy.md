# Codex Execution Policy

## Purpose

This policy defines how Codex should operate inside AJ Digital workspaces.

## Default Behavior

- Inspect current workspace state before editing.
- Respect explicit path boundaries.
- Preserve active user work.
- Use smallest safe changes.
- Avoid destructive commands.
- Validate with real commands when validation is allowed.
- Report what changed, what was skipped, and what remains gated.

## Blocked Without Approval

- Delete, rename, move, or overwrite existing files.
- Commit or push changes.
- Modify remotes.
- Install dependencies.
- Run migrations.
- Modify secrets or environment files.
- Modify active product code outside the approved scope.

## Output Expectations

Codex should produce concise final reports with changed files, skipped files, validation status, Git state, and recommended manual commands.

