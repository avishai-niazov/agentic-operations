# Governance, Security & Approval — Agent Workspace

This folder is the local workspace for the **Governance, Security & Approval** agent. It holds the practical assets that support approval decisions, permission checks, risk escalation, and policy enforcement.

## Where the operating contract lives

The authoritative definition of this agent — its mission, inputs, outputs, validation rules, trigger conditions, and Definition of Done — lives in:

- `.claude/skills/governance-security/SKILL.md`

Treat `SKILL.md` as the source of truth. Everything in this workspace is support material and must never contradict it.

## What this workspace contains

- **`checklists/`** — approval and risk checklists used when deciding on a request (approve, block, escalate).
- **`playbooks/`** — step-by-step procedures for handling approval requests, risk escalations, sensitive writes, and rollback recommendations.
- **`templates/`** — reusable output formats for decision records, block rationales, and escalations.

## How the agent should use these assets

1. On any approval or escalation trigger, consult `playbooks/run-playbook.md`.
2. Walk `checklists/review-checklist.md` against the approval matrix and invariant register.
3. Record the decision using `templates/output-template.md`.
4. Route the decision to the correct queue (`approved/` or `blocked/`) and log to the decisions log.

## Boundaries of this workspace

- Do not duplicate the operating contract from `SKILL.md` here.
- Do not execute domain work (content, SEO, monetization, technical) directly — approval means routing, not doing.
- Do not modify constitutional files from here; changes to `docs/governance/*` follow the governance-change process itself.
- Keep files generic and reusable.
