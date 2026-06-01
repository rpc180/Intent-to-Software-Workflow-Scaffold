# External AI and Data Policy

## Purpose

Use this file when the project may send context to external AI, LLM, agent, analytics, or automation providers.

## Allowed Context

External requests may include only:

- `<Allowlisted field>`
- `<Allowlisted metadata>`

## Disallowed Context

External requests must not include:

- secrets, keys, tokens, credentials, or connection strings
- private user data unless explicitly approved and documented
- sensitive operational data
- internal-only URLs or infrastructure details
- records marked sensitive by policy or metadata
- full prompt bodies or raw artifacts when summarized metadata is sufficient

## Required Processing Controls

Before sending any external request:

1. Construct a sanitized context pack from allowlisted fields only.
2. Run an explicit denylist scrub for sensitive tokens and fields.
3. Attach metadata describing payload classification.
4. Log only request metadata unless full prompt logging is explicitly approved.

## Output Handling

AI or automation outputs are advisory until a human or approved workflow accepts them.

- Label generated suggestions clearly.
- Reconcile suggestions against existing source-of-truth data.
- Require approval before persistence when data or definitions change.
- Record provenance and rationale for accepted changes.

## Non-Negotiable Principle

If a field is not explicitly allowlisted for external sharing, treat it as disallowed.

