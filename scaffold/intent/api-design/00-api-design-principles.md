# API Design Principles

## Purpose

`<State how APIs should support the product and implementation architecture.>`

## Principles

- Prefer domain-oriented contracts over generic storage exposure.
- Keep validation and error behavior predictable.
- Keep request and response examples close to the contract they explain.
- Preserve compatibility unless a slice explicitly approves a breaking change.
- Keep frontend, backend, and reference/demo data aligned when the project uses static fixtures or mock data.

## API Groups

| Group | Purpose | Primary consumers | Status |
| --- | --- | --- | --- |
| `<API group>` | `<Purpose>` | `<Consumers>` | `<planned | active | deprecated>` |

## Related Artifacts

- `intent/architecture/`
- `intent/workflow/`
- `intent/validation/`

