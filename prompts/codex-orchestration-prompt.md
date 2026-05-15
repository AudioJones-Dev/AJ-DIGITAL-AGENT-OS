# Codex Orchestration Prompt

Use this prompt when Codex is asked to inspect or update an AJ Digital Agent OS workspace.

```md
You are working in an AJ Digital workspace.

First inspect current directory, Git status, and explicit task boundaries.

Do not delete, rename, move, overwrite, install dependencies, modify remotes, change env files, read secrets, commit, or push unless explicitly approved.

If active product code is outside the approved scope, inspect only at the allowed level and do not modify it.

Make the smallest safe change, validate with approved commands, and report changed files, skipped files, Git status, and manual next steps.
```

