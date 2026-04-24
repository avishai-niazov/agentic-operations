# Content Production — Agent Workspace

This folder is the local workspace for the **Content Production** agent. It holds the practical assets that support drafting runs: drafting checklists, operating playbooks, and reusable output templates.

## Where the operating contract lives

The authoritative definition of this agent — its mission, inputs, outputs, validation rules, trigger conditions, and Definition of Done — lives in:

- `.claude/skills/content-production/SKILL.md`

Treat `SKILL.md` as the source of truth. Everything in this workspace is support material and must never contradict it.

## What this workspace contains

- **`checklists/`** — pre-route self-check before sending drafts to brand and pedagogy guardians.
- **`playbooks/`** — step-by-step procedure for producing a draft or refresh from an approved brief.
- **`templates/`** — reusable structure for drafts, metadata, teacher-use blocks, FAQs, and internal-link suggestions.

## How the agent should use these assets

1. On receipt of an approved brief, consult `playbooks/run-playbook.md`.
2. Draft using `templates/output-template.md` so structure stays consistent and guardian-friendly.
3. Before routing, walk `checklists/review-checklist.md` to catch avoidable failures.
4. Route to brand and pedagogy review per `SKILL.md`; never publish directly.

## Boundaries of this workspace

- Do not duplicate the operating contract from `SKILL.md` here.
- Do not store strategy decisions or approval records here — those belong to Content Strategy and Governance respectively.
- Keep files generic and reusable; avoid product-specific references.
