# Project Intent Package

This `intent/` tree contains architecture intent, design rationale, workflow discovery, API planning notes, roadmap tracking, decisions, prompts, and reusable planning templates for `<Project Name>`.

Use this folder as project memory for Codex or other development agents. The implementation repository may live under `<implementation-root>/`, while this folder preserves why the system exists, what decisions shape it, and how future work should move from concept to implementation.

For routine agent work, start with the lightweight active context digest:

- `00-active-context.md`

Then read the relevant workstream `CURRENT.md` file before opening full historical discovery packets, slice plans, or slice reviews. Use targeted `rg` lookups for specific backlog IDs, bug IDs, route names, source files, and artifact titles. Open long historical artifacts only when the current summaries are insufficient, the user asks for history, or a decision depends on earlier rationale.

Recommended local structure:

```text
<project-root>/
|-- intent/                 # project memory, decisions, discovery, plans, reviews
|-- .codex/                 # project-scoped agents and workflow skills
`-- <implementation-root>/  # executable application or library source
```

## Project Setup Fields

Set these values when adopting the template:

| Field | Value |
| --- | --- |
| Project name | `<Project Name>` |
| Project slug | `<project-slug>` |
| Implementation root | `<implementation-root>/` |
| Primary users | `<primary users>` |
| Primary runtime stack | `<stack>` |
| Current project posture | `<discovery | planning | implementation | stabilization | maintenance>` |

## Canonical Trackers

Feature intake and prioritization are tracked in:

- `roadmap/03-feature-backlog.md`

Discovered workstream state and next artifacts are tracked in:

- `roadmap/04-agent-discovered-workstreams.md`

Defects and regressions are tracked in:

- `roadmap/05-bug-ledger.md`

Current workstream state and fast-loading guidance are summarized in:

- `00-active-context.md`

Intent artifact placement rules are defined in:

- `intent-taxonomy.md`

Reusable writing scaffolds are available in:

- `templates/`

Agent team guidance is defined in:

- `agent-team-operating-model.md`
