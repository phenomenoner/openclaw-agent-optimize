# Cron Optimization (Patterns)

> Cron jobs are **deterministic** and should be lean. Move logic to scripts; keep prompts short.

## Patterns
- **One pass per tier**: batch same-frequency checks together.
- **Short prompts**: <300 tokens; call scripts for heavy logic.
- **No complex shell quoting**: use scripts under `/scripts`.

## Model Assignment
- Use lightweight tiers for cron unless the task is genuinely complex.
- Upgrade only if the cron task repeatedly fails.

## Guardrails
- Do not edit cron definitions unless explicitly requested.
- Favor idempotent scripts to reduce re-run risk.
