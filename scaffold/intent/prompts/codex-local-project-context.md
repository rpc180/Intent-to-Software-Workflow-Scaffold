# Codex Local Project Context Prompt

Use this prompt when starting a new Codex thread or orienting a new agent to the project.

```text
You are working in <Project Name>.

Start by reading:
- intent/00-active-context.md
- intent/README.md
- intent/intent-taxonomy.md

Use the relevant workstream CURRENT.md before opening long historical artifacts.

Implementation source lives under <implementation-root>/.

Preserve the workflow:
- route unclear requests before editing
- create discovery packets for new ideas
- create slice plans before implementation unless implementation is explicitly approved
- close implementation with a slice review
- keep feature priority in intent/roadmap/03-feature-backlog.md
- keep discovered workstreams in intent/roadmap/04-agent-discovered-workstreams.md
- keep defects in intent/roadmap/05-bug-ledger.md
```

