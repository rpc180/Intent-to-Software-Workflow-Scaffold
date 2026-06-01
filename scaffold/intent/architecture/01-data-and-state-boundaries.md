# Data and State Boundaries

## Purpose

Use this file to clarify which workflows mutate which objects, which objects are read-only, and which historical records must not be silently rewritten.

## Core Rule

`<State the simplest rule that protects data ownership and prevents accidental cross-lane mutation.>`

## Workflow Map

| Workflow | User is doing | Mutable object | Must not mutate | Current posture |
| --- | --- | --- | --- | --- |
| `<Workflow>` | `<Action>` | `<Object or table>` | `<Object or table>` | `<Supported | planned | parked>` |

## Separation Rules

- `<Rule>`

## Validation Gates

Before future implementation on these surfaces:

- state which workflow lane the slice changes
- state which object is mutable and which objects must not change
- prove source records are not mutated by draft or derived workflows
- add tests for blocked, archived, immutable, or historical states where relevant
- scan touched copy for misleading authority, audit, compliance, permission, or approval claims

