# Agent Registry

This registry is the canonical index for AJ Digital agent products and orchestration surfaces.

| Agent | Product URL | Status | Purpose |
| --- | --- | --- | --- |
| Podcast OS | podcastos.ajdigital.app | Active/In Development | AI Podcast Producer Agent |
| SEO/AEO Agent | seo.ajdigital.app / aeo.ajdigital.app | Planned | Search and Answer Engine Optimization Agent |
| Diagnostics Agent | diagnostics.ajdigital.app | Planned | Bug/project diagnostic agent |
| Signal OS | signalos.ajdigital.app | Planned | Strategic signal intelligence system |
| Hermes Control Plane | hermes.ajdigital.app | Planned | Orchestration and agent memory/control layer |

> Local checkout paths are operator-specific and are not tracked here. Example: an operator may keep `PODCAST OS` at `C:\dev\AJ DIGITAL AGENTS\PODCAST OS`, but the canonical reference is the product URL.

## Registry Rules

- Product code remains in each agent's product workspace.
- Agent OS may reference product folders but does not modify active product code without an explicit task.
- New agents must define purpose, owner, workspace, product URL, status, and approval requirements before production use.

