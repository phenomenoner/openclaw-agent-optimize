# Heartbeat Watchdog Pattern (Merged Control-Plane)

Use this pattern to prevent cron stuck-loop noise (e.g., one-shot jobs repeatedly showing `skipped/disabled`) **without** adding another frequent cron job.

## Why merge into isolated heartbeat
- Lower fixed token cost than a separate 10-minute watchdog cron.
- Fewer schedules to manage.
- Same alert channel and decision logic.

## Scope (keep it lightweight)
Only include control-plane checks:
- detect stale one-shot cron jobs that are due + disabled
- detect repeated `skipped + disabled` run signatures in recent run logs
- remove only clearly-bad jobs (backup-first)

Do **not** include heavy scans (full session audits, large file reads) in heartbeat.

## Recommended guardrail logic
1. Identify candidate job shape:
   - `schedule.kind == "at"`
   - `deleteAfterRun == true`
   - `enabled != true`
2. Confirm bad loop signature:
   - `state.nextRunAtMs <= now`
   - recent run history contains repeated `status=skipped` + `error=disabled` (e.g., >= 5 in last 10 min)
3. If matched:
   - backup `jobs.json`
   - remove job
   - emit one alert message with removed job ids and reason
4. Otherwise:
   - no alert, output `NO_REPLY`

## Delivery guidance
- Execute in isolated session.
- Keep `delivery.mode=none` for routine runs.
- Send message only when:
  - something is removed, or
  - heartbeat triage finds real non-noise attention.

## Anti-patterns
- Creating a separate watchdog cron at the same cadence unless absolutely required.
- Running heavyweight tool outputs on every heartbeat.
- Alerting on every successful no-op.
