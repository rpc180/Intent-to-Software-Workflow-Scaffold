---
name: workflow-slice-planning
description: "Turn approved discovery, backlog, or bug scope into a bounded implementation slice plan. Use when the user asks to plan a slice, convert a workstream into implementation scope, choose bugs for a slice, or prepare an approval-ready implementation plan."
---

# Workflow Slice Planning

## Purpose

Produce a decision-complete implementation slice plan. The plan must be bounded enough that implementation can begin after user approval without re-deciding scope.

## Required Inspection

Inspect:

- `intent/00-active-context.md`
- the relevant workstream `CURRENT.md`, if present
- the compact feature status map and slice ledger, if the feature is already in Feature Slice Context Compaction Mode
- the source discovery packet, accepted review, bug row, or backlog row that authorizes planning
- targeted rows in `intent/roadmap/03-feature-backlog.md`, `intent/roadmap/04-agent-discovered-workstreams.md`, or `intent/roadmap/05-bug-ledger.md` using `rg`
- affected implementation files and tests only enough to make the plan implementable

Open `intent/README.md`, `intent/intent-taxonomy.md`, `intent/agent-team-operating-model.md`, full roadmap files, older packets, or prior slice plans only when placement, scope, review team, or acceptance criteria cannot be resolved from the current summaries and targeted rows.

Use `intent/templates/slice-plan-template.md` when a plan format is needed.

## Workflow

1. Confirm the source scope is approved for planning.
2. Identify open bug ledger rows that are blockers, same-surface regressions, security/data risks, or acceptance-gate failures.
3. If the feature has many accepted slices, repeated context-length pressure, or reviewers are relying on long historical artifact chains, propose Feature Slice Context Compaction Mode. The compact mode uses a feature status map plus slice ledger as the first-read operating picture while keeping full rationale in source artifacts.
4. Define the slice summary, first problem, users served, in-scope work, out-of-scope work, dependency order, likely touched surfaces, repository publication expectations, acceptance criteria, test plan, parity expectations, compatibility expectations, showcase stop condition, review questions, agent coverage, required review team, implementation re-consultation triggers, and approval gate.
5. Keep adjacent ideas as follow-up candidates or backlog updates.
6. Update the relevant workstream `CURRENT.md` when the plan changes current state, next-slice guidance, or compact-mode posture.
7. Do not modify runtime files while planning.

## Artifacts

Create or update the next numbered slice-plan artifact in the active workstream, for example:

- `intent/<area>/workstreams/<date-topic>/01-slice-plan-<topic>.md`

Optional compaction artifacts for long-running feature chains:

- `intent/<area>/workstreams/<date-topic>/<NN>-feature-status-map-<feature>.md`
- `intent/<area>/workstreams/<date-topic>/<NN>-slice-ledger-<feature>.md`

Recommend any needed backlog or bug ledger updates, but keep feature priority canonical in `03-feature-backlog.md`.

## Agent Use

When current user or project instructions authorize subagent use, consult project subagents as appropriate under the Agent Use guardrails.

Before spawning new subagents, apply agent lifecycle hygiene from `intent/agent-team-operating-model.md`: reuse active, recent, or recorded specialist coverage for the same scope when it is still valid; send follow-up input or resume an existing agent when useful; spawn a new agent only when reuse is insufficient; close completed agents after their findings are integrated when agent management is available.

Use the existing project agents when planning decisions need review:

- Core: `delivery_lead`, `product_owner`, `solution_architect`, `qa_engineer`.
- Add frontend, backend, data, security, compliance, platform, or network specialists only for touched domains.

Document agent coverage in the slice plan. A domain being mentioned in the plan does not mean a specialist reviewed it unless that consultation is recorded. Include:

- reused agent findings and why they still apply
- newly spawned agents and why reuse was insufficient, when applicable
- completed agents closed after use, when applicable
- agents consulted and what decisions or risks they reviewed
- specialists intentionally excluded and why their domain is not material to the slice
- findings during implementation that should trigger focused re-consultation, even if the domain was already mentioned or reviewed in planning

## Stop Condition

Stop when the slice plan includes scope, exclusions, dependency order, repository publication expectations, acceptance criteria, validation plan, agent coverage, review team, implementation re-consultation triggers, showcase or review stop condition, and explicit approval gate. Implementation starts only after user approval.
