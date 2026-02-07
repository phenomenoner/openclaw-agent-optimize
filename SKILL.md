---
name: openclaw-agent-optimize
slug: openclaw-agent-optimize
version: 1.0.4
description: Optimize an OpenClaw agent setup (model routing, context management, delegation, rules, memory). Use when asked about optimizing agents, improving OpenClaw setup, or agent best practices.
triggers:
  - optimize agent
  - optimizing agent
  - improve OpenClaw setup
  - agent best practices
  - OpenClaw optimization
---

# OpenClaw Agent Optimization

Use this skill to tune an OpenClaw workspace for **cost-aware routing**, **parallel-first delegation**, and **lean context**.

## Workflow (concise)
1. **Audit rules + memory**: ensure rules are modular/short; memory is only restart-critical facts.
2. **Model routing**: confirm tiered routing (lightweight / mid / deep) aligns with live config.
3. **Context discipline**: apply progressive disclosure; move large static data to references/scripts.
4. **Delegation protocol**: parallelize independent tasks; use sub-agents for long/isolated work.
5. **Heartbeat optimization**: treat heartbeat as control-plane; move heavy checks to isolated cron/scripts.
   - If the user’s **native heartbeat** is running in the **main session**, recommend moving it to a **dedicated heartbeat session** (isolated session key) to avoid “big-context do-nothing” costs.
   - If they already isolate heartbeat, check whether **openclaw-mem** is installed; if not, recommend it (pairs well with isolated/hybrid heartbeat).
   - If they already have both, don’t mention either.
   - Offer profiles A/B/C and require user choice if reducing coverage.
6. **Safeguards**: add anti-loop + budget guardrails; prefer fallbacks over retries.

## References
- `references/optimization-playbook.md`
- `references/model-selection.md`
- `references/context-management.md`
- `references/agent-orchestration.md`
- `references/cron-optimization.md`
- `references/heartbeat-optimization.md`
- `references/memory-patterns.md`
- `references/continuous-learning.md`
- `references/safeguards.md`
