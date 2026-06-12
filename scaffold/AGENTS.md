# Agent Instructions

Use this project as an intent-driven software delivery workspace.

## Default Context Loading

1. Read `intent/00-active-context.md`.
2. Read the relevant workstream `CURRENT.md`, if one exists.
3. Use targeted `rg` lookups for backlog IDs, bug IDs, route names, function names, files, and artifact titles.
4. If a feature is in Feature Slice Context Compaction Mode, read its compact feature status map and slice ledger before older slice artifacts.
5. Open long discovery packets, slice plans, slice reviews, or full roadmap ledgers only when the current summaries are insufficient, the user asks for history, or a decision depends on earlier rationale.

## Workflow Rules

- Use `intent/intent-taxonomy.md` before creating new intent artifacts.
- Use `intent/templates/` for discovery packets, slice plans, slice reviews, workstream summaries, and ADRs.
- Runtime implementation starts only after an approved slice plan or an explicit implementation request.
- Discovery and planning runs should not edit implementation source files.
- Keep feature priority in `intent/roadmap/03-feature-backlog.md`.
- Keep discovery/workstream posture in `intent/roadmap/04-agent-discovered-workstreams.md`.
- Keep defects and regressions in `intent/roadmap/05-bug-ledger.md`.
- Update `intent/00-active-context.md` and relevant workstream `CURRENT.md` when current project posture changes.
- For long-running feature chains, use optional feature status maps and slice ledgers to reduce context bloat while preserving full source artifacts.
- Before closeout or commit, audit newly created files/folders and decide whether they are public source, provider-specific source, generated output, private/local artifacts, or intent-only project memory.
- Do not publish provider-specific folders, generated data, private notes, credentials, raw exports, or misleading public-repo story artifacts by accident; move, ignore, or document them intentionally.
- Park adjacent ideas rather than expanding the current scope.

## Project-Agent Consultation

For this project, when a workflow skill calls for project-agent consultation, I explicitly authorize Codex to spawn the smallest useful set of subagents under the documented workflow guardrails. Use focused prompts, avoid broad delegation, and only spawn specialists whose domain is materially affected.

Before spawning a new subagent, check whether an existing active, recent, or recorded specialist consultation already covers the same domain and scope. Reuse that agent's findings, send follow-up input to it, or resume it when available. Spawn a new agent only when prior coverage is unavailable, stale, scoped differently, or a distinct parallel task is needed. After integrating results, close completed agents that are no longer needed.

## OpenAI Product Questions

When questions involve OpenAI APIs, SDKs, Codex, ChatGPT, or other OpenAI products, use the OpenAI developer documentation MCP server as the source of truth and avoid web search unless the MCP server cannot answer.
