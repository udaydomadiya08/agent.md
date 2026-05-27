# 🤖 agent.md — AI Agent Behavior Skill

A plug-and-play skill file that tells any AI agent (Claude, GPT, or any LLM-based system) **how to behave safely, reliably, and usefully** when operating autonomously.

---

## What Is This?

`agent.md` is a **skill file** — a structured instruction document written in Markdown that an AI agent reads to understand the rules it must follow during execution.

Think of it like a **code of conduct for AI agents**. Instead of hoping your agent behaves correctly, you give it explicit, opinionated instructions covering safety, goal clarity, tool use, memory, security, and more.

It follows the skill file format used by systems like [Claude](https://claude.ai), but the principles apply to any agentic AI system.

---

## Why Does This Exist?

Most agent failures aren't caused by a weak model. They're caused by a weak *system around the model* — vague goals, unrestricted tool access, no human checkpoints, no cost limits, no logging.

This skill file encodes 15 hard-won principles for building agents that don't go off the rails.

---

## What's Inside

| # | Principle | What It Covers |
|---|-----------|---------------|
| 1 | **Define Goals Before Acting** | Objective, constraints, success criteria |
| 2 | **Principle of Least Privilege** | Only use tools that are necessary |
| 3 | **Human-in-the-Loop** | Approval gates for high-risk actions |
| 4 | **Memory Management** | Short-term, long-term, retrieval, decay |
| 5 | **Hallucination Control** | Verification, confidence flagging |
| 6 | **Prompt Injection Defense** | Handling adversarial external content |
| 7 | **Loop & Cost Limits** | Iteration caps, timeouts, budget ceilings |
| 8 | **Reliability Over Intelligence** | Determinism, retries, fallbacks |
| 9 | **Observability & Logging** | What to record and why |
| 10 | **Multi-Agent Coordination** | Orchestration, ownership, conflict resolution |
| 11 | **Data Privacy** | PII, consent, compliance (GDPR / HIPAA) |
| 12 | **Context Window Discipline** | Avoiding instruction dilution at scale |
| 13 | **Specialization Over Generalization** | Focused agents outperform "do-it-all" ones |
| 14 | **Adversarial Input Handling** | Contradictions, edge cases, ambiguity |
| 15 | **Core Mental Model** | The right mindset for building agent systems |

Plus a **winning architecture diagram** and a **pre-execution checklist**.

---

## How to Use It

### With Claude
Place `agent.md` in your skills directory. Claude will automatically read and follow it when operating agentically.

### With Any Other LLM
Paste the contents of `agent.md` into your system prompt, or reference it as a context document at the start of an agentic session.

### As a Design Reference
Even without direct injection, use this as a checklist when designing or reviewing any agentic workflow.

---

## The Architecture It Recommends

```
User Input
 ↓
Planner Agent        ← breaks goal into steps
 ↓
Specialized Sub-Agents  ← each owns one task type
 ↓
Tool Layer           ← APIs, files, databases
 ↓
Validation Layer     ← checks outputs before use
 ↓
Human Approval       ← required for high-risk actions
 ↓
Execution
 ↓
Logging + Monitoring ← always, without exception
```

---

## Pre-Execution Checklist

Before any agent starts running, verify:

- [ ] Goal is specific, bounded, and measurable
- [ ] Tools needed are identified and permissions confirmed
- [ ] Human approval gates defined for high-risk steps
- [ ] Loop/cost limits are set
- [ ] Logging is active
- [ ] Sensitive data handling is planned
- [ ] Fallback path exists if a step fails

---

## The Golden Rule

> An AI agent should behave like a **highly capable intern with tools** — not an all-knowing god system you blindly trust.

Controlled autonomy wins. The moat in agentic systems is **orchestration + execution quality**, not just the underlying model.

---

## File Structure

```
agent-skill/
└── agent.md        ← the skill file (this repo)
```

---

## Contributing

Found a failure mode not covered here? Open a PR. The goal is a living document that grows with real-world agentic deployments.

---

## License

MIT — use freely in personal or commercial projects.
