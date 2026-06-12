# Active Project Context

Last updated: `<YYYY-MM-DD>`

Purpose: lightweight first-read context for project agents. Read this file before opening long historical workstream packets. Use linked `CURRENT.md` files and targeted `rg` lookups before loading full backlog, bug, or slice history.

## Context Loading Rule

Default path:

1. Read this file.
2. Read the relevant workstream `CURRENT.md`, if one exists.
3. If the feature is in Feature Slice Context Compaction Mode, read its compact feature status map and slice ledger.
4. Use targeted `rg` for backlog IDs, bug IDs, route names, file names, or artifact titles.
5. Open detailed historical artifacts only when the current summaries are insufficient, the user asks for history, or a decision depends on earlier rationale.

Do not reread every accepted slice plan or review by default.

## Project Snapshot

| Field | Current Value |
| --- | --- |
| Project name | `<Project Name>` |
| Implementation root | `<implementation-root>/` |
| Current phase/posture | `<discovery | planning | implementation | stabilization | maintenance>` |
| Primary product goal | `<one sentence>` |
| Primary users | `<users>` |
| Current release or milestone | `<milestone>` |

## Active Grounding

- `<Principle 1 that should constrain current work>`
- `<Principle 2 that should constrain current work>`
- `<Known non-claim or future-gated capability>`
- `<Validation or parity expectation that agents must preserve>`

## Active Workstream Index

| Workstream | Current summary | Status | Next useful artifact |
| --- | --- | --- | --- |
| `<Workstream name>` | `intent/<area>/workstreams/<date-topic>/CURRENT.md` | `<status>` | `<next artifact or decision>` |

## Open Items To Keep Visible

- `<Backlog ID or BUG-ID>`: `<short current posture>`

## Fast Lookup Hints

- Backlog row: `rg -n "<F-###>" intent/roadmap/03-feature-backlog.md`
- Bug row: `rg -n "<BUG-###>" intent/roadmap/05-bug-ledger.md`
- Workstream row: `rg -n "<Workstream name>" intent/roadmap/04-agent-discovered-workstreams.md`
- Touched runtime surface: use `rg` in `<implementation-root>/` for route/function/file names before opening broad files.
