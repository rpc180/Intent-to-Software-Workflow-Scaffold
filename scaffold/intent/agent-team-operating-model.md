# Agent Team Operating Model

This operating model defines how project-scoped agent teams should coordinate intent discovery, slice planning, implementation, review, and showcase work.

It supplements `intent/intent-taxonomy.md`; the taxonomy remains the source of truth for artifact placement.

## Purpose

Use this model when a workstream needs more than one agent perspective or when a feature moves from discovered idea to slice planning.

The operating goal is traceability without churn: assemble the smallest useful team, produce one primary artifact, move adjacent ideas into backlog or follow-up candidates, and stop at the agreed gate.

## Context Loading

Agents should start with `intent/00-active-context.md` and the relevant workstream `CURRENT.md` before opening full historical discovery packets, slice plans, or slice reviews.

When a feature is in Feature Slice Context Compaction Mode, agents should read the compact feature status map and slice ledger before older slice artifacts. Propose compact mode when a feature has many accepted slices, repeated context-length pressure, or decision drift caused by rereading long historical chains.

Use targeted `rg` lookups for backlog IDs, bug IDs, route names, function names, and artifact titles. Open older long artifacts only when the current summaries are insufficient, the user asks for history, or a decision depends on earlier rationale.

When a run changes current state, update the relevant `CURRENT.md` and active tracker rows instead of copying long rationale into multiple files.

## Team Assembly Pattern

Every agent-team run starts with a core coordination group:

- `delivery_lead`: coordinator for run type, dependencies, stop condition, next artifact, and handoff.
- `solution_architect`: taxonomy placement reviewer and architecture alignment reviewer.
- `product_owner`: priority, user value, scope, and acceptance reviewer.
- `qa_engineer`: acceptance criteria, review gate, regression, and parity reviewer when the run is moving toward a slice or implementation.

Add specialists only when their domain is materially affected:

- UI, workflow, visualization, and human-facing screens: add `ux_designer`, `frontend_engineer`, and `qa_engineer`.
- Backend/API contracts and service boundaries: add `backend_engineer`, `solution_architect`, and `qa_engineer`.
- Data, schema, migrations, seeds, query safety, retention, and reporting data models: add `data_dba`, `backend_engineer`, and `qa_engineer`.
- Security, permissions, sensitive data, credentials, XSS, auth, export control, and connector risk: add `security_engineer`.
- Compliance, auditability, control evidence, records, reporting, and decision traceability: add `compliance_reviewer`.
- Delivery sequencing, dependency tracking, stop gates, and backlog hygiene: keep `delivery_lead` active through handoff.

Do not add a specialist only because the topic is adjacent. If the current run will not make a decision or produce an artifact in that domain, capture the idea as a follow-up candidate.

Agent coverage should be explicit. A domain being mentioned in a discovery packet or slice plan does not mean the relevant specialist reviewed it unless the artifact records that consultation. Discovery and planning artifacts should list consulted agents, intentionally excluded specialists, and implementation-phase findings that should trigger focused re-consultation.

## Agent Lifecycle Hygiene

Before spawning a new subagent, check whether an existing active, recent, or recorded specialist consultation already covers the same domain and scope. Prefer reuse when the prior agent reviewed the same artifact set, decision, risk, or implementation surface and the inputs have not materially changed.

Reuse can mean relying on the recorded findings, sending follow-up input to the existing agent, or resuming a closed agent when the runtime supports it. Spawn a new agent only when prior coverage is unavailable, stale, scoped differently, inaccessible, or a distinct parallel task is needed. When a new agent is spawned despite existing related coverage, record why reuse was insufficient.

After integrating a subagent's result, close completed agent threads that are no longer needed when the runtime exposes agent management. If live agent status is not inspectable, rely on the current thread, artifact notes, and recorded consultation history; do not invent agent state.

## Coordinator Responsibilities

The `delivery_lead` is responsible for:

- declaring the run type: discovery, slice planning, implementation, review, or showcase
- naming the primary artifact before work starts
- enforcing the stop condition
- separating current-scope work from backlog or follow-up candidates
- checking that taxonomy placement is explicit
- keeping related backlog IDs, dependencies, and next artifacts visible
- confirming review participation from `solution_architect`, `product_owner`, and `qa_engineer` when the run prepares future implementation
- stopping the run when the next useful artifact is known

The coordinator does not replace specialist review. They keep the team from drifting into unbounded improvement.

## Stop Gates

### Discovery Gate

Stop when the discovery packet has:

- intent placement and placement rationale
- current project evidence
- problem/opportunity
- in-scope and out-of-scope boundaries
- risks and open questions
- acceptance criteria for the packet
- one recommended next slice or next artifact
- backlog/follow-up candidates for adjacent ideas

Discovery runs must not implement runtime changes. If implementation would require editing runtime files, stop and request an approved slice plan.

### Slice Planning Gate

Stop when the slice plan has:

- bounded scope and exclusions
- dependency order
- acceptance criteria
- test and review approach
- parity expectations where relevant
- rollback or compatibility expectations
- required agent team for implementation and review

Slice planning may identify implementation tasks, but it should not perform them unless implementation was explicitly requested and approved.

### Implementation Gate

Start implementation only after a slice plan or explicit user request authorizes code changes.

Implementation must honor the project constraints captured in intent:

- domain boundaries remain clear
- service and data ownership stays explicit
- demo/static/reference data remains contract-compatible when the project uses it
- security, privacy, compliance, and governance claims stay honest
- schema or persistence changes remain additive/reversible unless approved otherwise

During implementation, re-check the plan's agent coverage against actual touched files, validation results, and newly uncovered edge cases. Use project agents for focused review when concrete findings materially affect their domain, even if that domain was already mentioned or reviewed during planning. Keep those reviews bounded to the approved scope; park any recommended scope expansion for separate approval.

Before review closeout, perform a repository publication check for newly created, moved, generated, ignored, or tracked files/folders. Decide whether each is public source, provider-specific source, generated output, private/local artifact, or intent-only project memory, and do not publish files that misrepresent the architecture, expose private data, or belong only in local development.

### Review / Showcase Gate

Stop when the work can be demonstrated or reviewed against acceptance criteria.

The review handoff should include:

- what changed
- what was validated
- which agents reviewed the implementation or why additional focused review was intentionally skipped
- which risks remain
- which follow-ups were parked
- whether runtime files were changed
- whether newly created files/folders were intentionally tracked, ignored, moved, or kept local
- whether any agent-recommended workstreams need backlog updates

## Loop Controls

Use these controls to prevent endless improvement loops:

- One run produces one primary artifact.
- Every discovery packet names `In Scope`, `Out of Scope`, `Stop condition`, and `Backlog / Follow-Up Candidates`.
- Adjacent ideas are parked instead of pursued.
- Current summaries are updated instead of rereading or rewriting long historical artifacts by default.
- Long-running feature chains can use compact feature status maps and slice ledgers instead of repeatedly loading every historical slice artifact.
- Taxonomy improvements are suggested only when placement is blocked.
- Roadmap tracking does not replace the feature backlog.
- The coordinator can stop a run after the useful next artifact is known, even if more refinements are possible.
- User approval is required before moving from discovery to implementation.

## Artifact Quality Bar

Every agent-discovered artifact should make these items clear:

- recommended intent location
- related existing intent files
- related backlog IDs or "none yet"
- priority posture
- next artifact type
- stop condition
- included agents and intentionally excluded specialists
- review gate and acceptance criteria

If any of these are unknown, the artifact should say so directly rather than expand scope to solve it.
