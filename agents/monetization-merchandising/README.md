# Monetization & Merchandising — Agent Workspace

This folder is the local workspace for the **Monetization & Merchandising** agent. It holds the practical assets that support monetization review and experiment design.

## Where the operating contract lives

The authoritative definition of this agent — its mission, inputs, outputs, validation rules, trigger conditions, and Definition of Done — lives in:

- `.claude/skills/monetization-merchandising/SKILL.md`

Treat `SKILL.md` as the source of truth. Everything in this workspace is support material and must never contradict it.

## What this workspace contains

- **`checklists/`** — review checklist that forces UX, speed, trust, and rollback considerations before recommending any monetization change.
- **`playbooks/`** — step-by-step procedure for weekly monetization review, experiment design, and rollback flagging.
- **`templates/`** — reusable output format for monetization recommendations and experiment specs.

## How the agent should use these assets

1. On trigger (weekly review, traffic mix shift, template safety request), consult `playbooks/run-playbook.md`.
2. Use `templates/output-template.md` for every recommendation.
3. Walk `checklists/review-checklist.md` before sending any recommendation for governance approval.
4. Route sitewide or risky changes to Governance & Security; route speed risks to Technical Health.

## Boundaries of this workspace

- Do not duplicate the operating contract from `SKILL.md` here.
- Do not execute sitewide monetization writes from this workspace; recommendations need governance approval.
- Do not override brand or pedagogy review; monetization never outranks identity or learning quality.
- Keep files generic and reusable.
