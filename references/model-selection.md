# Model Selection (Tiered Routing)

## Principle
Use the **cheapest capable** model for the task. Escalate only after failure or when clearly justified.

## Tiers
- **Lightweight / frequent**: routine tasks, web search loops, formatting, quick scripts.
- **Main coding / orchestration**: multi-file edits, coordinating sub-agents, integration work.
- **Deep reasoning / architecture**: design decisions, critical risk analysis, large refactors.

## OpenClaw Practice
- **Source of truth**: live config (`config.get`) and `MEMORY.md` model routing.
- **Sub-agents**: assign lightweight tiers by default; upgrade only if required.
- **Ask on ambiguity**: “Recommend mid-tier for this. OK to proceed?”

## Anti-patterns
- Using highest tier for simple tasks.
- Repeatedly asking user for model choice when the task is routine.
