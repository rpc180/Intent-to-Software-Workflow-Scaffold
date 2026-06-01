# Bug Ledger

Use this file as the single canonical bug and regression ledger for the project.

For faster agent runs, start with `intent/00-active-context.md` and targeted `rg` lookups for specific `BUG-###` rows before reading this full ledger. Use `rg -n "^\\| BUG-" intent/roadmap/05-bug-ledger.md` to choose the next bug ID without loading all details.

## Intake Rules

- Add one row per defect or regression.
- Keep supporting evidence summarized in the row.
- Use `chat attachment only` in `Evidence Link` when a screenshot or annotated image was attached to the chat but not saved in the repo.
- Link a project file only when the evidence already lives in the repo or the user approved preserving it under `intent/roadmap/bug-assets/`.
- Do not create per-bug markdown files.
- If the report is really new product scope, set `Slice Disposition` to `feature backlog input` and refine `03-feature-backlog.md` separately.

## Disposition Values

- `current slice blocker`
- `current slice opportunistic`
- `next bugfix slice`
- `feature backlog input`
- `needs reproduction`
- `wont fix / parked`

## Severity Values

- `Critical`
- `High`
- `Medium`
- `Low`

## Bug Table

| ID | Title | Observed Behavior | Expected Behavior | Evidence Type | Evidence Summary | Evidence Link | Affected Surface | Severity | Slice Disposition | Status | Verification Gate | Related Backlog IDs | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| BUG-001 | `<Bug title>` | `<Observed behavior>` | `<Expected behavior>` | `<chat | screenshot | test failure | browser note | code inspection>` | `<Evidence summary>` | `<path or chat attachment only>` | `<Surface>` | `<Severity>` | `<Disposition>` | `<Open | Accepted / closed | Parked>` | `<How fix will be verified>` | `<F-### or none>` | `<Notes>` |

