# openclaw-agent-optimize

> OpenClaw agent optimization skill — model routing, context management, delegation, and cron best practices.

An installable [OpenClaw](https://openclaw.ai) skill that packages battle-tested agent-optimization patterns. Drop it into your workspace and get instant guidance on cost-aware model routing, parallel-first delegation, lean context management, and more.

## 🙏 Credits & Inspiration

This skill is heavily inspired by **[affaan-m/everything-claude-code](https://github.com/affaan-m/everything-claude-code)** — a production-ready collection of Claude Code configs evolved over 10+ months by an Anthropic hackathon winner. The core philosophy of tiered model selection, progressive disclosure, parallel orchestration, and continuous learning was extracted and adapted from that work for the OpenClaw ecosystem.

Thank you [@affaan-m](https://github.com/affaan-m) 🎉

## 📦 What's Inside

| File | Purpose |
|------|---------|
| `SKILL.md` | Skill entry-point — triggers + quick-start workflow |
| `references/model-selection.md` | Tiered model routing guide |
| `references/context-management.md` | Context window discipline + progressive disclosure |
| `references/agent-orchestration.md` | Parallel-first delegation, split-role sub-agents |
| `references/cron-optimization.md` | Cron job patterns and model assignment |
| `references/memory-patterns.md` | Daily + long-term memory file design |
| `references/continuous-learning.md` | Hooks → instincts → skills pipeline |
| `references/safeguards.md` | Anti-loop + budget guardrails |

## 🚀 Install

### Via ClawHub (recommended)
[<img src="https://clawhub.ai/badge.svg" height="24">](https://clawhub.ai/phenomenoner/openclaw-agent-optimize)

```bash
clawhub install phenomenoner/openclaw-agent-optimize
```

> **Note:** If you cannot see the skill on ClawHub immediately after an update, it may be in review (審核中). Please try again later.

**Canonical page:** https://clawhub.ai/phenomenoner/openclaw-agent-optimize

**Deprecated duplicates:**
- https://clawhub.ai/phenomenoner/openclaw-agent-optimize-skill
- https://clawhub.ai/phenomenoner/openclaw-agent-token-optimizer

These exist because we didn’t realize updated skills can temporarily disappear during review, so we re-uploaded under different names. Please use the canonical page above.

### Manual
Copy the skill folder into your OpenClaw workspace:
```bash
cp -r openclaw-agent-optimize ~/.openclaw/workspace/skills/
```

## 📖 How to Use

The skill auto-triggers when you ask about optimizing your agent, improving your OpenClaw setup, or following agent best practices.

Key guidance you’ll get:
- **Native heartbeat is expensive** (it can load large main-session context) and **isn’t always reliably isolatable** in real deployments.
- Recommended strategy: disable native heartbeat and use an isolated heartbeat cron (alert-only).
- Persistent actions are **user-gated**: no config/cron mutations without explicit approval.
- Bonus: pair isolated heartbeat with **openclaw-mem** for cheap “RAG-style” task awareness.

## 📄 License

MIT
