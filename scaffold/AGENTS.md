# Agent Instructions

Use this project as an intent-driven software delivery workspace.

## Default Context Loading

1. Read `intent/00-active-context.md`.
2. Read the relevant workstream `CURRENT.md`, if one exists.
3. Use targeted `rg` lookups for backlog IDs, bug IDs, route names, function names, files, and artifact titles.
4. Open long discovery packets, slice plans, slice reviews, or full roadmap ledgers only when the current summaries are insufficient, the user asks for history, or a decision depends on earlier rationale.

## Workflow Rules

- Use `intent/intent-taxonomy.md` before creating new intent artifacts.
- Use `intent/templates/` for discovery packets, slice plans, slice reviews, workstream summaries, and ADRs.
- Runtime implementation starts only after an approved slice plan or an explicit implementation request.
- Discovery and planning runs should not edit implementation source files.
- Keep feature priority in `intent/roadmap/03-feature-backlog.md`.
- Keep discovery/workstream posture in `intent/roadmap/04-agent-discovered-workstreams.md`.
- Keep defects and regressions in `intent/roadmap/05-bug-ledger.md`.
- Update `intent/00-active-context.md` and relevant workstream `CURRENT.md` when current project posture changes.
- Park adjacent ideas rather than expanding the current scope.

## Project-Agent Consultation

For this project, when a workflow skill calls for project-agent consultation, I explicitly authorize Codex to spawn the smallest useful set of subagents under the documented workflow guardrails. Use focused prompts, avoid broad delegation, and only spawn specialists whose domain is materially affected.

## OpenAI Product Questions

When questions involve OpenAI APIs, SDKs, Codex, ChatGPT, or other OpenAI products, use the OpenAI developer documentation MCP server as the source of truth and avoid web search unless the MCP server cannot answer.
