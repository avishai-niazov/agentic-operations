# Content Strategy — Agent Workspace

This folder is the local workspace for the **Content Strategy** agent. It holds the practical assets that support brief creation and refresh prioritization: review checklists, operating playbooks, and reusable brief templates.

## Where the operating contract lives

The authoritative definition of this agent — its mission, inputs, outputs, validation rules, trigger conditions, and Definition of Done — lives in:

- `.claude/skills/content-strategy/SKILL.md`

Treat `SKILL.md` as the source of truth. Everything in this workspace is support material and must never contradict it.

## What this workspace contains

- **`checklists/`** — review checklist for briefs before they go to brand and pedagogy review.
- **`playbooks/`** — step-by-step procedure for building a brief from an opportunity, running a refresh decision, and handling hub gaps.
- **`templates/`** — reusable brief template covering audience, learning goal, target surface, teacher intent, and no-go zones.

## How the agent should use these assets

1. On trigger (new opportunity, refresh request, hub gap, seasonal window), consult `playbooks/run-playbook.md`.
2. Draft the brief using `templates/output-template.md`.
3. Walk `checklists/review-checklist.md` before routing to guardian reviews.
4. Only after both guardian passes, hand the approved brief to Content Production.

## Boundaries of this workspace

- Do not duplicate the operating contract from `SKILL.md` here.
- Do not write drafts or final content here — that is Content Production's role.
- Do not use competitor style as a brief input; market intelligence may identify opportunity, not voice.
- Keep files generic and reusable.
