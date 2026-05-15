# Repo Audit Prompt

Use this prompt when auditing a repo or workspace before implementation.

```md
Audit the specified workspace without modifying files.

Report:

- Whether the path exists.
- Whether it is a Git repo.
- Current branch and remote, if available.
- Top-level files and folders.
- Package and lock files.
- Env file presence without reading values.
- Obvious product, deployment, and documentation surfaces.
- Risks, blockers, and recommended next commands.

Do not delete, rename, move, overwrite, install dependencies, modify remotes, read secrets, commit, or push.
```

