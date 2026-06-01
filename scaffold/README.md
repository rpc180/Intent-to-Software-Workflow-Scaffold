# Workflow Template

This folder is a reusable project workflow scaffold for turning early intent into bounded software delivery work.

It is designed to be copied into a new repository before or during ideation. The template gives future agents and collaborators a shared memory model, clear artifact placement rules, scoped discovery packets, approval-ready slice plans, implementation closeout reviews, a feature backlog, a workstream tracker, a bug ledger, and Codex project skills/agents that reinforce the workflow.

## What This Template Provides

- `intent/`: durable project memory for rationale, taxonomy, discovery, plans, reviews, decisions, roadmap, and reusable prompts.
- `.codex/agents/`: read-only specialist roles for product, delivery, architecture, UX, frontend, backend, QA, security, data, platform, network, and compliance review.
- `.codex/skills/`: project workflow skills for routing, discovery, slice planning, implementation, bug intake, and backlog refinement.
- `AGENTS.md`: default instructions for agents working in a project that uses this structure.

## Quick Start

1. Copy the contents of this folder into the root of a new project.
2. In `intent/README.md`, set the implementation root, for example `app/`, `src/`, `service/`, or `prototype/`.
3. Fill in `intent/00-active-context.md` with the current project summary, active workstreams, and fast lookup hints.
4. Review `intent/intent-taxonomy.md` and rename or add durable top-level folders only when the project needs different categories.
5. Capture early ideas with `intent/templates/ideation-packet-template.md`.
6. Move approved discovery into numbered slice plans using `intent/templates/slice-plan-template.md`.
7. After implementation, close the loop with `intent/templates/slice-review-template.md`.
8. Keep prioritization canonical in `intent/roadmap/03-feature-backlog.md`, discovered workstream status in `04-agent-discovered-workstreams.md`, and defects in `05-bug-ledger.md`.

## Artifact Flow

```text
idea or problem report
  -> intent router
  -> discovery packet
  -> workstream CURRENT.md summary
  -> feature backlog / workstream tracker / bug ledger as needed
  -> approved slice plan
  -> implementation
  -> slice review and closeout
  -> tracker updates and active-context refresh
```

## Operating Principles

- One run should produce one primary artifact.
- Read `intent/00-active-context.md` before opening long historical artifacts.
- Read the relevant workstream `CURRENT.md` before opening every packet, plan, or review in that workstream.
- Use targeted search for backlog IDs, bug IDs, file names, routes, functions, or artifact titles.
- Do not edit runtime code from a discovery or planning run unless the user explicitly approves implementation.
- Park adjacent ideas in backlog or follow-up sections instead of expanding the current scope.
- Link related artifacts instead of copying long rationale across files.
- Keep feature priority, workstream status, and bug status in their canonical ledgers.

## Folder Map

```text
workflow-template/
|-- AGENTS.md
|-- README.md
|-- TEMPLATE-MAP.md
|-- .codex/
|   |-- config.toml
|   |-- agents/
|   `-- skills/
`-- intent/
    |-- 00-active-context.md
    |-- README.md
    |-- intent-taxonomy.md
    |-- agent-team-operating-model.md
    |-- architecture/
    |-- api-design/
    |-- workflow/
    |-- validation/
    |-- visualization/
    |-- roadmap/
    |-- templates/
    |-- decisions/
    |-- diagrams/
    |-- glossary/
    `-- prompts/
```
