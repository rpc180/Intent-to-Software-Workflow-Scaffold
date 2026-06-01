# Intent Taxonomy

This file tells Codex and agent teams where to place new ideation, discovery, design, and roadmap artifacts in the `intent/` tree.

Use it before creating new folders or documents. The goal is traceability: a future team should be able to find why an idea exists, where it belongs, what it depends on, and what kind of artifact should come next.

## Placement Principles

1. Reuse an existing folder when the topic clearly fits.
2. Create a new top-level folder only when the idea represents a durable category not covered here.
3. Keep implementation source code in `<implementation-root>/`; keep durable rationale, design intent, and future work records in `intent/`.
4. Prefer one focused artifact over scattered notes.
5. Link related intent files instead of copying long sections between folders.
6. Include placement rationale in every new ideation packet.

## Fast Context Loading

Before opening long historical artifacts, read:

- `intent/00-active-context.md`
- the relevant workstream `CURRENT.md`, when present

Use targeted `rg` lookups for backlog IDs, bug IDs, route names, function names, and artifact titles. Open full discovery packets, slice plans, and slice reviews only when current summaries are insufficient, the user asks for history, or a decision depends on earlier rationale.

When creating a new recurring workstream, add or update a `CURRENT.md` in that workstream folder once the first packet or slice changes the current project state.

## Agent Responsibilities

For multi-agent ideation runs:

- `delivery_lead` coordinates the packet, stop condition, dependencies, and next slice.
- `solution_architect` validates taxonomy fit and checks alignment with existing architecture intent.
- `product_owner` validates user value, scope, priority, and acceptance criteria.
- Add `ux_designer` and `frontend_engineer` for human-facing workflows and UI slices.
- Add `backend_engineer`, `data_dba`, `security_engineer`, `platform_sre`, `network_admin`, `qa_engineer`, or `compliance_reviewer` when their domain is materially affected.

## Required Ideation Packet Header

Every new discovery or ideation packet should start with:

```markdown
# Intent Placement

Recommended location: `intent/<folder>/...`
Reason: <why this folder fits>

Related existing intent:
- `intent/...`

Priority posture: <discovered | parked | ready for discovery | ready for slice planning | ready for implementation>
Next artifact type: <discovery brief | design brief | API contract | schema scaffold | slice plan | sprint review>
Stop condition: <when this run should stop>
```

Use `templates/ideation-packet-template.md` when creating a new discovery or ideation packet.

## Folder Guide

### `architecture/`

Use for durable system concepts, boundaries, design principles, governance foundations, and cross-cutting constraints.

Good fit:

- conceptual model changes
- domain boundaries
- data and state ownership
- identity, access, security, and compliance foundations
- major non-functional requirements
- integration boundaries

Do not use for:

- detailed endpoint request/response contracts
- sprint sequencing tables
- UI screen inventories unless they change architecture semantics

### `api-design/`

Use for service boundaries, endpoint groups, request/response contracts, events, and backend-composed data shapes.

Good fit:

- new API groups
- request/response contracts
- service-layer responsibility changes
- reporting/export contracts
- integration connector contracts
- frontend data needs that must be backend-supported

Do not use for:

- generic feature wish lists
- raw database seed/reference files
- visual layout explorations unless they define backend data needs

### `workflow/`

Use for operational process flows and user journeys that span screens, APIs, and data states.

Good fit:

- user journeys
- authoring/editing workflows
- review/approval handoffs
- exception or escalation flows
- external assignment lifecycles

Do not use for:

- low-level UI component details
- database schema snapshots

### `validation/`

Use for evidence, validation concepts, assertions, rules, testable readiness checks, and quality gates.

Good fit:

- acceptance semantics
- validation rule behavior
- evidence requirements
- release confidence checks
- reportable validation outcomes

Do not use for:

- unit test implementation plans unless they explain validation semantics
- general QA notes with no durable project meaning

### `visualization/`

Use for how important project state should be presented visually.

Good fit:

- dashboards
- visual drill-downs
- graph or map views
- overlays and filter concepts
- visual data needs

Do not use for:

- all UI work by default
- workflow descriptions unless the emphasis is visual decision support

### `roadmap/`

Use for prioritization, backlog, sequencing, release slices, and workstream status.

Good fit:

- discovered feature backlog items
- implementation slices
- deferred/parked status
- priority and dependency notes
- release or sprint-scale sequencing

Do not use for:

- detailed architecture rationale
- endpoint schemas
- UI mock details

### `decisions/`

Use for durable architectural decisions that should remain stable and referenceable.

Good fit:

- accepted ADRs
- decisions that constrain future implementation
- reversals or superseding decisions
- rationale for choosing one platform pattern over another

Do not use for:

- early brainstorming
- transient sprint notes

### `diagrams/`

Use for textual or diagram-oriented representations of stable concepts.

Good fit:

- conceptual topology sketches
- layered system diagrams
- graph structures that explain a model

Do not use for:

- screenshots or sprint review artifacts unless they are stable reference diagrams

### `glossary/`

Use for shared terms and definitions.

Good fit:

- canonical meaning of domain concepts
- terminology pivots that affect many files
- user, system, and lifecycle vocabulary

Do not use for:

- feature proposals
- workflow descriptions

### `prompts/`

Use for reusable Codex or agent context prompts that help recreate project understanding.

Good fit:

- local project context prompts
- setup prompts for future agent runs
- reusable context packs

Do not use for:

- one-off agent reports
- product backlog items

## New Folder Criteria

Create a new top-level folder only when all of these are true:

1. The topic will recur across multiple future artifacts.
2. It does not fit the existing folder guide.
3. Keeping it inside an existing folder would make that folder ambiguous.
4. The new folder can be named with a durable category, not a temporary task name.

When creating a new top-level folder, add a short `README.md` explaining:

- what belongs there
- what does not belong there
- related existing folders
- first known workstreams

## Stop Conditions for Ideation Runs

Agent teams should stop and report when one of these conditions is met:

- Discovery brief completed and user approval is needed to choose a slice.
- Placement conflict found and the team cannot choose a folder confidently.
- Acceptance criteria for a slice plan are complete.
- Implementation would require modifying runtime files and the current run was discovery-only.
- Remaining ideas are backlog candidates rather than part of the current scope.

Do not keep expanding scope to improve the taxonomy, roadmap, or UI indefinitely. Place the idea, document the reason, identify the next artifact, and stop.

