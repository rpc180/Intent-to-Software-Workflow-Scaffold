---
name: workflow-workstream-discovery
description: "Create bounded discovery and ideation packets using the repo intent taxonomy, templates, roadmap, and project agent model. Use for new workstreams, feature ideas, workflow or architecture exploration, UI discovery, or requests to explore before implementation."
---

# Workflow Workstream Discovery

## Purpose

Create durable project memory for a bounded idea before implementation. Produce one primary discovery artifact, park adjacent ideas, and stop at the approval gate.

## Required Inspection

Inspect:

- `intent/00-active-context.md`
- `intent/README.md`
- `intent/intent-taxonomy.md`
- `intent/templates/README.md`
- `intent/templates/ideation-packet-template.md`
- `intent/agent-team-operating-model.md` only when agent-team composition is not obvious
- targeted roadmap/bug rows using `rg`

Then inspect only the intent and implementation files directly relevant to the requested topic. The implementation root is defined in `intent/README.md`.

Open full roadmap files, older workstream packets, or prior slice reviews only when current summaries and targeted rows are insufficient.

## Workflow

1. Determine the correct taxonomy location before creating an artifact.
2. Create or update one workstream packet using the ideation packet template.
3. Preserve the required `Intent Placement` header, priority posture, next artifact type, and stop condition.
4. Record current project evidence from existing intent, roadmap, implementation, and known bugs.
5. Define in scope, out of scope, risks, open questions, acceptance criteria, agent coverage, and one recommended next slice or next artifact.
6. If the discovery is likely to become a long-running feature with many slices, note when Feature Slice Context Compaction Mode might be appropriate later; do not create compact artifacts until the feature actually needs them or the user requests them.
7. Move adjacent ideas into `Backlog / Follow-Up Candidates` instead of expanding the packet.
8. Create or update the workstream `CURRENT.md` when the discovery creates a recurring workstream or changes next-artifact guidance.

## Artifacts

- Primary artifact: `intent/<area>/workstreams/<yyyy-mm-dd-topic>/00-ideation-packet.md`
- Optional tracker update: `intent/roadmap/04-agent-discovered-workstreams.md`
- Optional feature backlog recommendation: `intent/roadmap/03-feature-backlog.md`

Do not edit runtime files during discovery.

## Agent Use

When current user or project instructions authorize subagent use, consult project subagents as appropriate under the Agent Use guardrails.

Before spawning new subagents, apply agent lifecycle hygiene from `intent/agent-team-operating-model.md`: reuse active, recent, or recorded specialist coverage for the same scope when it is still valid; send follow-up input or resume an existing agent when useful; spawn a new agent only when reuse is insufficient; close completed agents after their findings are integrated when agent management is available.

Use the smallest useful team from `.codex/agents/`:

- Core: `delivery_lead`, `solution_architect`, `product_owner`.
- Add `qa_engineer` when the packet prepares future implementation.
- Add specialists only when their domain is materially affected.

Document agent coverage in the discovery packet:

- reused agent findings and why they still apply
- newly spawned agents and why reuse was insufficient, when applicable
- completed agents closed after use, when applicable
- agents consulted and the decision areas they reviewed
- specialists intentionally excluded and why their domain is not materially affected yet
- implementation-phase findings that should trigger focused re-consultation, such as touched files, validation failures, unresolved domain questions, or new edge cases

## Stop Condition

Stop when the discovery packet is complete and the next useful artifact is known. If implementation would require changing runtime files, stop and ask for approval of a slice plan or implementation request.
