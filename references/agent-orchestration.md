# Agent Orchestration (Parallel-First)

## Core Rules
- **Always parallelize independent tasks.** If task B does not depend on task A, spawn both.
- Delegate long-running or noisy work to sub-agents to keep main context clean.

## Split-Role Delegation
Use multiple sub-agents with different roles when you need diverse perspectives:
- **Engineer**: implementation details
- **Reviewer**: correctness & style
- **Security**: risk assessment

## OpenClaw Mechanics
- Use `sessions_spawn` (or equivalent) to create sub-agents.
- Pass only the minimal context (goal, constraints, relevant files).
- Log sub-agent runs to `memory/delegation_log.json` for recovery.

## When to Keep Inline
- Quick tasks (<2 min)
- Interactive debugging with user feedback
