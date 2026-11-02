# DevOps / L1 Support Engineer Challenge: Incident Triage with AI Tooling

Thank you for your interest in joining our team. This challenge reflects the work you would do as first-line support: alerts come in, you find the right runbook, check the evidence, and decide what to do or who to escalate to.

**Time:** about 2 hours. Please don't spend much more. An unfinished part with honest notes is better than a rushed one.

**AI tools:** you are expected to use an AI coding assistant (we use Claude Code). We are interested in how you build tooling around it and how you check its output.

## Context

You support a fictional blockchain network called **Orbit**. Alerts arrive from an alerting tool as JSON. Each alert has a title, a description, a team, a severity and a runbook link.

Runbooks live in a separate GitHub repository:
`https://github.com/techops-services/orbit-runbooks`

The alerts and the evidence for this challenge are in:
`https://github.com/techops-services/orbit-incidents`

```
orbit-incidents/
  alerts/        # 4 alert payloads (JSON)
  evidence/      # logs, metric snapshots and notes, one folder per alert
```

You have no access to real infrastructure. Everything you need is in these two repositories.

The scripts in `orbit-runbooks/scripts/` are stubs. In your reports, say what you would run and why. You don't need to run them.

## Tasks

### 1. Build your triage tooling (~40 min)

Create a repository with Claude Code configuration that helps an on-call engineer triage alerts quickly.

- **A skill** (`.claude/skills/<name>/SKILL.md`) that finds and reads the right runbook for an alert. It should read runbooks from the GitHub repository, not from a local copy.
- **A subagent** (`.claude/agents/<name>.md`) that triages one alert: reads the payload and the evidence, uses the skill, and returns a short report.
- **MCP configuration** (`.mcp.json`) for the GitHub MCP server, or another MCP server you find useful. Do not commit tokens.

Decide what your tools are allowed to do. Explain your choice in the README.

### 2. Triage the alerts (~60 min)

Run your tooling on each alert in `alerts/`. For each one, write a report in `reports/<alert-id>.md` with:

1. **What is happening:** one or two sentences.
2. **Evidence:** the facts that support it, each with its source file.
3. **Runbook:** which runbook and section applies, with a link.
4. **Decision:** resolve, monitor, act (what exactly) or escalate (to whom).
5. **Escalation note:** if you escalate, the message you would post to the owning team. Keep it short.
6. **Unknowns:** anything you could not confirm, or that looks wrong.

Check the reports yourself. Correct the agent where it is wrong, and say what you corrected.

### 3. Reflection (~20 min)

In the README, answer briefly:

- Where did the agent help most? Where was it wrong or risky?
- What would you add to make this tooling safe for a real on-call team?
- What would you improve in the runbooks?

## Deliverables

1. A public GitHub repository with:
   - `.claude/` (skill and subagent), `.mcp.json`
   - `reports/` (one report per alert)
   - `README.md` with setup steps, the design choices for your tooling, and the reflection
2. An export of your Claude Code session (`/export`), or the main parts of it. We want to see how you worked, not only the result.

## What we look at

- Correct decisions for each alert, backed by evidence.
- Clear, short escalation notes.
- Safe tooling: what it may and may not do.
- How you check and correct AI output.

There is no single correct design for the tooling. Simple and working beats complex and untested.

Good luck!
