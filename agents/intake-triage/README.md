# Intake & Triage — Agent Workspace

This folder is the local workspace for the **Intake & Triage** agent. It holds the practical assets that support turning raw signals into typed, routed work items.

## Where the operating contract lives

The authoritative definition of this agent — its mission, inputs, outputs, validation rules, trigger conditions, and Definition of Done — lives in:

- `.claude/skills/intake-triage/SKILL.md`

Treat `SKILL.md` as the source of truth. Everything in this workspace is support material and must never contradict it.

## What this workspace contains

- **`checklists/`** — triage checklist for confirming a signal is well-formed before routing.
- **`playbooks/`** — step-by-step procedure for signal classification, severity tagging, and routing.
- **`templates/`** — reusable work-item template covering task class, severity, required corpus, and target queue.

## How the agent should use these assets

1. On every incoming signal (alert, email, anomaly, manual request), consult `playbooks/run-playbook.md`.
2. Normalize the signal into a work item using `templates/output-template.md`.
3. Walk `checklists/review-checklist.md` before routing.
4. Route to the correct downstream queue and emit a trace.

## Boundaries of this workspace

- Do not duplicate the operating contract from `SKILL.md` here.
- Do not execute downstream work (content, SEO, technical, monetization) — route, don't do.
- Do not approve risky writes; escalate those to Governance & Security.
- Keep files generic and reusable.
