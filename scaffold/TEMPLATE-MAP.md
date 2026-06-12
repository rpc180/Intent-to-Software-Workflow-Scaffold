# Template Map

This file explains what was generalized into the template and what was intentionally left out.

## Included

- The `intent/` memory model for durable project rationale.
- A taxonomy that routes artifacts into architecture, API design, workflow, validation, visualization, roadmap, decisions, diagrams, glossary, and prompts.
- Workstream folders with `CURRENT.md` summaries and numbered artifacts.
- Reusable templates for ideation packets, slice plans, slice reviews, workstream summaries, and ADRs.
- Optional compact feature status map and slice ledger templates for long-running feature chains.
- Canonical lifecycle ledgers:
  - feature backlog
  - agent-discovered workstream tracker
  - bug ledger
- A specialist agent roster.
- Project skills that enforce routing, discovery, planning, implementation closeout, bug intake, and backlog refinement.
- Repository publication checks for newly created files/folders before they are tracked or pushed.

## Not Included

- Product-specific implementation code.
- Historical workstream packets from the source project.
- Product-specific architecture, domain terms, screenshots, fixture data, database scripts, or backlog rows.
- Any claim that a new project must use a particular tech stack.

## Recommended Copy Pattern

Copy this folder's contents into a new project root, then replace placeholders such as `<Project Name>`, `<implementation-root>`, `<date-topic>`, `<agent_role>`, and `<Backlog ID>`.

The intended shape is:

```text
new-project/
|-- .codex/
|-- intent/
|-- AGENTS.md
`-- <implementation-root>/
```
