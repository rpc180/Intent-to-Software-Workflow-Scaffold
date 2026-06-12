# Intent Artifact Templates

This folder contains reusable documentation templates for Codex and agent-team planning work.

These are writing scaffolds for intent artifacts such as discovery briefs, ideation packets, slice plans, workstream summaries, ADRs, and slice reviews.

Before using a template:

1. Review `../intent-taxonomy.md`.
2. Decide the correct destination folder for the new artifact.
3. Preserve the template's placement, scope, and stop-condition sections.
4. Move unrelated ideas to a backlog or follow-up section instead of expanding the current artifact.

Available templates:

- `ideation-packet-template.md`: discovery and ideation packet template for agent-team workstreams.
- `slice-plan-template.md`: approval-ready implementation slice plan template.
- `slice-review-template.md`: implementation closeout and review template.
- `current-workstream-template.md`: lightweight workstream summary template.
- `feature-status-map-template.md`: compact operating map for long-running feature chains.
- `slice-ledger-template.md`: compact accepted-slice history for long-running feature chains.
- `adr-template.md`: durable architecture decision record template.

Use feature status maps and slice ledgers only when a feature grows large enough that repeatedly loading older slice plans/reviews creates context bloat or decision drift. They supplement, not replace, source artifacts.
