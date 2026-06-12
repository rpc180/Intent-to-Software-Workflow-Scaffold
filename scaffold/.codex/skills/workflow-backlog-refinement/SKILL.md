---
name: workflow-backlog-refinement
description: "Refine backlog, workstream tracker, and bug ledger alignment without creating a second priority source. Use for backlog cleanup, post-review tracking, priority posture updates, bug disposition alignment, or moving discovered work toward discovery, slice planning, implementation, or parking."
---

# Workflow Backlog Refinement

## Purpose

Keep roadmap tracking coherent across feature backlog, agent-discovered workstreams, and bug intake. Preserve one canonical home for each item and make the next artifact visible.

## Required Inspection

Inspect:

- `intent/00-active-context.md`
- the relevant workstream `CURRENT.md`, if present
- the compact feature status map and slice ledger, if the feature is in Feature Slice Context Compaction Mode
- targeted rows in `intent/roadmap/03-feature-backlog.md`, `intent/roadmap/04-agent-discovered-workstreams.md`, or `intent/roadmap/05-bug-ledger.md` using `rg`
- the specific discovery, slice plan, or slice review artifact that prompted the refinement

Open `intent/README.md`, `intent/intent-taxonomy.md`, `intent/agent-team-operating-model.md`, full roadmap files, or older historical artifacts only when current summaries and targeted rows are insufficient.

## Workflow

1. Identify whether each item is a feature, discovered workstream, bug, dependency, or parked follow-up.
2. Keep feature priority canonical in `03-feature-backlog.md`.
3. Keep discovery/workstream status in `04-agent-discovered-workstreams.md`.
4. Keep defects and regressions in `05-bug-ledger.md`.
5. Link related backlog IDs, bug IDs, and workstream paths instead of copying long rationale between files.
6. Update status, priority posture, proposed slice, next artifact, and notes only where needed.
7. For long-running feature chains, create or maintain Feature Slice Context Compaction Mode artifacts when accepted slices are producing context bloat or repeated history rereads. Keep the compact feature status map focused on current decisions and next choices, and keep the slice ledger focused on accepted slice history.
8. Update `intent/00-active-context.md` or relevant workstream `CURRENT.md` when the active posture changes.
9. Park adjacent ideas rather than expanding the current scope.

## Artifacts

Update only the necessary tracking files:

- `intent/roadmap/03-feature-backlog.md`
- `intent/roadmap/04-agent-discovered-workstreams.md`
- `intent/roadmap/05-bug-ledger.md`
- optional compact feature status map and slice ledger artifacts in the active workstream

Do not edit runtime files.

## Agent Use

Before spawning new subagents, apply agent lifecycle hygiene from `intent/agent-team-operating-model.md`: reuse active, recent, or recorded specialist coverage for the same scope when it is still valid; send follow-up input or resume an existing agent when useful; spawn a new agent only when reuse is insufficient; close completed agents after their findings are integrated when agent management is available.

Use `delivery_lead` and `product_owner` when priority posture or sequencing is unclear. Add `solution_architect` for taxonomy conflicts. Add domain specialists only when technical risk changes priority or placement.

## Stop Condition

Stop when each item has one canonical home, status, priority posture or severity, related IDs, next artifact, and clear parked or active disposition. Do not convert backlog refinement into discovery or implementation unless explicitly requested.
