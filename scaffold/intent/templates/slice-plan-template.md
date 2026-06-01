# <Slice Name> Slice Plan

## Intent Placement

Recommended location: `intent/<area>/workstreams/<yyyy-mm-dd-topic>/<NN>-slice-plan-<topic>.md`
Reason: <Explain why this slice belongs in this workstream and how it follows from approved discovery, backlog, or bug scope.>

Related existing intent:
- `intent/...`

Related backlog or bug IDs:
- `<F-### | BUG-### | none>`

Priority posture: ready for implementation review; implementation requires approval of this slice plan
Next artifact type: implementation slice and slice review
Stop condition: Slice plan is complete and ready for user review. Do not change runtime files until this plan is approved.

## Slice Summary

<Summarize the bounded implementation outcome.>

## First Problem

<State the immediate problem this slice solves before listing implementation details.>

## Users Served

Primary users:
- <User group or role>

Secondary users:
- <Stakeholder group or role>

## In Scope

- <Approved implementation scope>

## Out of Scope

- <Explicit exclusions and future-gated work>

## Dependency Order

1. <First dependency or implementation phase>
2. <Second dependency or implementation phase>
3. <Validation or showcase phase>

## Likely Files / Contracts Touched

Frontend:
- `<implementation-root>/...`

Backend/API:
- `<implementation-root>/...`

Data / persistence:
- `<implementation-root>/...`

Tests:
- `<implementation-root>/...`

Intent docs:
- `intent/...`

## Implementation Acceptance Criteria

Functional behavior:
- <Expected behavior>

User experience:
- <Expected user-facing behavior>

Security, privacy, or governance:
- <Expected boundary or non-claim>

Compatibility:
- <Backward compatibility or migration expectation>

## Test Plan

Automated checks:
- <Command or test>

Manual or browser checks:
- <Manual validation path>

Accessibility checks:
- <Keyboard, label, focus, contrast, or screen reader check>

Regression checks:
- <Existing behavior that must continue to work>

## Reference / Demo Data Parity Expectations

Required outcome:
- <How fixtures, mock data, static mode, snapshots, or seeded data should stay aligned with runtime/API behavior, if relevant>

Not acceptable:
- <A drift, hidden limitation, or misleading demo behavior to avoid>

## Rollback / Compatibility Expectations

- <Rollback or recovery expectation>
- <Compatibility expectation>
- <Migration or data safety expectation>

## Showcase Stop Condition

Stop implementation and prepare review when the following path is demonstrable:

1. <Showcase step>
2. <Showcase step>
3. <Validation result>

Do not continue into:

- <Adjacent scope to avoid>

## Review Questions For Approval

- <Question that must be answered before implementation>

## Deferred Backlog Items

- <Item to add or update in backlog>

## Agent Coverage

- Consulted agents:
- Intentionally excluded specialists:
- Implementation re-consultation triggers:

## Required Review Team

- `delivery_lead`: confirm scope and stop condition.
- `product_owner`: confirm user value and acceptance criteria.
- `solution_architect`: confirm contract and boundary alignment.
- `qa_engineer`: verify acceptance coverage.
- `<specialist>`: <why needed>

## Approval Gate

Implementation may begin only after this slice plan is approved or revised by the user.
