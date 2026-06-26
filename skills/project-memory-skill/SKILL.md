---
name: project-memory-skill
description: Maintain persistent project memory for long-running software projects. Use when working across AI agents or sessions, preserving project context, recording decisions, tracking failed attempts, handing off active work, or setting up a repository-level memory system.
---

# Project Memory Skill

Use this skill to keep project knowledge in the repository instead of relying on temporary chat history.

## Required Memory Files

Each project should maintain this directory:

```text
.ai/
├── AGENTS.md
├── MEMORY.md
├── DECISIONS.md
├── HANDOFF.md
├── FAILED_ATTEMPTS.md
└── PROJECT_MEMORY_SKILL.md
```

## Startup Workflow

Before starting substantive work in a project:

1. Read `.ai/AGENTS.md` for permanent project rules.
2. Read `.ai/DECISIONS.md` for prior decisions.
3. Read `.ai/MEMORY.md` for accumulated findings.
4. Read `.ai/HANDOFF.md` for current task state.
5. Read `.ai/FAILED_ATTEMPTS.md` for approaches that should not be repeated.

If a file is missing, note that gap and continue with the files that exist.

## Working Rules

- Treat `DECISIONS.md` as the highest-priority project memory.
- Reuse existing conclusions before re-analyzing a solved problem.
- Check `FAILED_ATTEMPTS.md` before retrying a risky or expensive approach.
- When source code conflicts with recorded memory, analyze the reason before changing either.
- Keep updates factual, dated, and useful for the next agent.

## End Of Session Workflow

Before ending work, update the relevant memory files:

- `MEMORY.md` for durable findings.
- `DECISIONS.md` for important choices and rationale.
- `HANDOFF.md` for current state and next steps.
- `FAILED_ATTEMPTS.md` for failed approaches that should inform future work.

## Detailed Reference

Read `references/project-memory-skill.md` when you need the full file responsibilities, templates, and operating rules.

Use `templates/ai-memory/` when initializing a new project's `.ai/` memory directory.

Read `examples/basic-project-memory.md` when you need a compact example of how the memory files should be used during a task.
