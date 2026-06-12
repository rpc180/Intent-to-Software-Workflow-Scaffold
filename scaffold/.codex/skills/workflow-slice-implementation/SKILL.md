---
name: workflow-slice-implementation
description: "Implement approved slices and complete built-in review and closeout. Use only after a slice plan is approved or the user explicitly approves implementation, including validation, showcase evidence, slice review notes, bug and backlog recommendations, and parked follow-ups."
---

# Workflow Slice Implementation

## Purpose

Implement approved slices end to end. Implementation is not complete until validation, showcase/review evidence, residual risks, and tracking recommendations are recorded.

## Required Inspection

Inspect:

- `intent/00-active-context.md`
- the approved slice plan or explicit implementation request
- the relevant workstream `CURRENT.md`, if present
- the compact feature status map and slice ledger, if the feature is in Feature Slice Context Compaction Mode
- targeted backlog, tracker, and bug rows using `rg`
- affected implementation and test files

Open the source discovery packet, older accepted reviews, `intent/README.md`, `intent/intent-taxonomy.md`, `intent/agent-team-operating-model.md`, or full roadmap files only when the approved plan and current summaries do not resolve scope, terminology, review gates, or dependencies.

## Workflow

1. Confirm approval to implement. If approval is absent, route to `workflow-slice-planning` and stop before edits.
2. Re-read the slice plan and open bug ledger rows that are selected for, or block, the slice.
3. Implement only the approved scope.
4. Preserve project constraints documented in intent: domain-oriented contracts, clear ownership boundaries, parity expectations, additive/reversible data changes unless explicitly approved otherwise, and honest non-claims for parked governance or compliance features.
5. Validate with the slice plan's test plan and any additional focused checks required by touched code.
6. Run a repository publication check before closeout when files or folders were created, moved, generated, or newly tracked. Classify new paths as public source, provider-specific source, generated output, private/local artifact, or intent-only project memory. Use `git status --short`, `git ls-files -o --exclude-standard`, and staged diff/name-status checks when Git is available. Move, ignore, or park files that should not be published; do not let provider-specific folders, generated data, private notes, credentials, or misleading public repo story artifacts drift into tracked source by accident.
7. Compare the plan's agent coverage and re-consultation triggers against the actual touched files, validation results, repository publication findings, and newly uncovered edge cases; request focused project-agent review when needed before closeout.
8. Produce closeout: what changed, validation performed, showcase path, repository publication decision, agent review performed or intentionally skipped, residual risks, parked follow-ups, bug/backlog status recommendations, and the next best slice development topic.
9. Update the relevant workstream `CURRENT.md`, `intent/00-active-context.md`, and any compact feature status map or slice ledger when acceptance, release, or follow-up posture changes current project state.

## Artifacts

Runtime edits belong under the implementation root defined in `intent/README.md`.

Intent updates are limited to closeout and tracking:

- Slice review or closeout artifact in the active workstream, usually the next numbered `*-slice-review-*.md` file.
- Bug ledger status recommendations in `intent/roadmap/05-bug-ledger.md`.
- Backlog/workstream tracker recommendations when scope is complete or deferred.
- Optional compact feature status map and slice ledger updates for long-running feature chains.

Do not create a standalone slice-review skill. Review is part of this skill.

## Agent Use

When current user or project instructions authorize subagent use, consult project subagents as appropriate under the Agent Use guardrails.

Before spawning new subagents, apply agent lifecycle hygiene from `intent/agent-team-operating-model.md`: reuse active, recent, or recorded specialist coverage for the same scope when it is still valid; send follow-up input or resume an existing agent when useful; spawn a new agent only when reuse is insufficient; close completed agents after their findings are integrated when agent management is available.

Use specialists for focused review, not broad delegation:

- Use `qa_engineer` for validation and release confidence when implementation changes runtime behavior, tests, or validation gates.
- Use `security_engineer` for XSS, auth, sensitive data, export, or write-path risk.
- Use `frontend_engineer`, `backend_engineer`, `data_dba`, `ux_designer`, or `compliance_reviewer` only when the approved scope, touched files, validation results, or newly uncovered edge cases materially affect their domain.
- A domain being mentioned or reviewed in the approved plan does not block re-consultation during implementation when concrete implementation findings need another focused pass.
- Keep agent prompts bounded to the approved scope and ask for risk, fit, and validation review; use their input to make within-scope adjustments or park scope expansion for separate approval.

## Stop Condition

Stop when the approved slice is demonstrable against its review gate, validation results and repository publication decisions are recorded, remaining risks are explicit, bug/backlog follow-ups are parked or recommended, compact feature summaries are current when used, and the next best slice development topic is named in the slice review. Do not expand into the next slice opportunistically.
