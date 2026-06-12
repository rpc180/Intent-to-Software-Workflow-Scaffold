---
name: workflow-bug-intake
description: "Capture bugs and regressions in one project ledger from chat reports, screenshots, browser preview notes, code snippets, terminal output, or test failures. Use when the user reports broken behavior, visual defects, failed checks, or asks whether a defect belongs in a slice."
---

# Workflow Bug Intake

## Purpose

Convert bug evidence into one canonical bug ledger row and recommend when the defect should enter slice work.

## Required Inspection

Inspect:

- `intent/00-active-context.md`
- relevant existing bug rows from `intent/roadmap/05-bug-ledger.md` using `rg`
- related backlog/workstream rows using targeted `rg`
- the active workstream `CURRENT.md` or slice plan when the bug affects current work
- relevant implementation files, routes, tests, fixtures, or assets only when needed to identify the affected surface

To choose the next bug ID, use a targeted ledger listing such as `rg -n "^\\| BUG-" intent/roadmap/05-bug-ledger.md` instead of reading the whole ledger unless table structure or context is unclear.

## Evidence Handling

Accept evidence from:

- Chat descriptions
- Attached screenshots
- Annotated screenshots
- Browser preview observations
- Local image paths
- Code snippets pasted in chat
- Terminal output, stack traces, and failed test output

If evidence is attached only in chat, summarize what is visible and leave `Evidence Link` as `chat attachment only`. Do not claim the raw file is stored in the repo.

If the user provides a local image path inside the project, link it from the ledger. If the image is outside the project and should be preserved, ask before copying it into `intent/roadmap/bug-assets/`.

## Workflow

1. Read the existing ledger and choose the next `BUG-###` ID.
2. Inspect attached visual or code evidence before writing the row.
3. Record the symptom, expected behavior, reproduction/evidence, affected surface, severity, disposition, status, verification gate, and related backlog IDs.
4. Use one of these dispositions: `current slice blocker`, `current slice opportunistic`, `next bugfix slice`, `feature backlog input`, `needs reproduction`, `wont fix / parked`.
5. Keep the bug in the ledger only. Do not create per-bug markdown files.
6. If the bug is actually a feature request, record it as `feature backlog input` and recommend a `workflow-backlog-refinement` follow-up.
7. Update the relevant workstream `CURRENT.md` or `intent/00-active-context.md` only if the bug changes active follow-up posture.

## Artifacts

Primary artifact:

- `intent/roadmap/05-bug-ledger.md`

Optional supporting assets:

- `intent/roadmap/bug-assets/` only when the user approves preserving a screenshot or annotated image as a project file.

## Agent Use

When current user or project instructions authorize subagent use, consult project subagents as appropriate under the Agent Use guardrails.

Before spawning new subagents, apply agent lifecycle hygiene from `intent/agent-team-operating-model.md`: reuse active, recent, or recorded specialist coverage for the same scope when it is still valid; send follow-up input or resume an existing agent when useful; spawn a new agent only when reuse is insufficient; close completed agents after their findings are integrated when agent management is available.

Use `qa_engineer` by default for ambiguous, high-impact, or current-slice bugs. Add `frontend_engineer`, `backend_engineer`, `security_engineer`, `data_dba`, or `ux_designer` only when the defect materially touches that domain.

## Stop Condition

Stop when the bug has a ledger row with severity, disposition, status, verification gate, evidence summary, and related backlog/workstream context. Do not implement the fix unless the user explicitly approves a slice implementation.
