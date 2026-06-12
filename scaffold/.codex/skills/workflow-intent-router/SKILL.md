---
name: workflow-intent-router
description: "Route project requests to the correct intent workflow, artifact type, repo files, agent team, and stop gate. Use for ambiguous requests, new ideas, bug reports, backlog questions, discovery, slice planning, implementation, review/closeout, or when Codex needs to decide where work belongs under intent/."
---

# Workflow Intent Router

## Purpose

Use this skill as the front door for project work. Classify the request, inspect the minimum project memory needed, and route to the right project workflow without doing unrelated work.

## Required Inspection

Start with lightweight current context:

- `intent/00-active-context.md`
- the relevant workstream `CURRENT.md`, if the request names or implies a workstream

When placement, artifact type, or next action is still unclear, inspect only the needed source:

- `intent/README.md`
- `intent/intent-taxonomy.md`
- `intent/agent-team-operating-model.md`
- targeted rows in `intent/roadmap/03-feature-backlog.md`, `intent/roadmap/04-agent-discovered-workstreams.md`, or `intent/roadmap/05-bug-ledger.md` using `rg`

Open full backlog, tracker, bug ledger, discovery packets, slice plans, or slice reviews only when targeted lookup and current summaries are insufficient, the user asks for history, or a decision depends on earlier rationale.

## Routing

- Route new ideas, unclear intent placement, or discovery-only requests to `workflow-workstream-discovery`.
- Route approved discovery, backlog, or bug scope that needs an implementation plan to `workflow-slice-planning`.
- Route approved slice execution to `workflow-slice-implementation`.
- Route broken behavior, regressions, screenshots, code examples, browser notes, terminal output, or test failures to `workflow-bug-intake`.
- Route backlog cleanup, status alignment, prioritization posture, or post-review tracking to `workflow-backlog-refinement`.
- Route requests to compact a long-running feature's context, create a status map, create a slice ledger, or reduce repeated slice-history loading to `workflow-backlog-refinement` unless the user is also asking for a new slice plan.
- Do not create a standalone slice review route. Review and closeout belong inside `workflow-slice-implementation`.

## Artifact Decision

Return or create only the artifact needed for the request:

- Discovery packet: `intent/<area>/workstreams/<yyyy-mm-dd-topic>/00-ideation-packet.md`
- Slice plan: next numbered workstream artifact, usually `01-slice-plan-<topic>.md`
- Slice review: next numbered workstream artifact produced during implementation closeout
- Feature compaction artifacts: compact feature status map plus slice ledger in the active workstream
- Bug ledger row: `intent/roadmap/05-bug-ledger.md`
- Backlog refinement: update `03-feature-backlog.md`, `04-agent-discovered-workstreams.md`, or `05-bug-ledger.md`

## Agent Use

Before spawning new subagents, apply agent lifecycle hygiene from `intent/agent-team-operating-model.md`: reuse active, recent, or recorded specialist coverage for the same scope when it is still valid; send follow-up input or resume an existing agent when useful; spawn a new agent only when reuse is insufficient; close completed agents after their findings are integrated when agent management is available.

Use the existing project agents in `.codex/agents/` only when their perspective changes the answer:

- Default core for discovery and planning: `delivery_lead`, `solution_architect`, `product_owner`.
- Add `qa_engineer` for slice planning, bug intake, validation gates, and implementation closeout.
- Add UI, backend, data, security, compliance, platform, or network specialists only when materially affected.

## Stop Condition

Stop when the request has a clear route, artifact type, target location, stop gate, and next skill. If the user asked for implementation but no approved slice or explicit implementation request exists, route to `workflow-slice-planning` and stop before runtime edits.
