# SEO & Crawl — Agent Workspace

This folder is the local workspace for the **SEO & Crawl** agent. It holds the practical assets that support indexation, canonical, sitemap, and internal-linking reviews.

## Where the operating contract lives

The authoritative definition of this agent — its mission, inputs, outputs, validation rules, trigger conditions, and Definition of Done — lives in:

- `.claude/skills/seo-crawl/SKILL.md`

Treat `SKILL.md` as the source of truth. Everything in this workspace is support material and must never contradict it.

## What this workspace contains

- **`checklists/`** — review checklist covering indexation policy, canonical integrity, sitemap hygiene, orphan detection, and thin-content risk.
- **`playbooks/`** — step-by-step procedures for daily audits, weekly crawl reviews, GSC anomaly triage, and post-publish safety checks.
- **`templates/`** — reusable SEO report template covering root-cause analysis and correct routing (technical fix vs. content gap).

## How the agent should use these assets

1. On trigger (daily audit, weekly review, GSC anomaly, template change, post-publish check), consult `playbooks/run-playbook.md`.
2. Produce findings using `templates/output-template.md`.
3. Walk `checklists/review-checklist.md` before routing.
4. Route technical blockers to Technical Health; route content gaps to Content Strategy; route sensitive changes (canonical, robots, sitemap at scale) to Governance & Security.

## Boundaries of this workspace

- Do not duplicate the operating contract from `SKILL.md` here.
- Do not change robots, canonicals, or sitemaps directly — those require governance approval.
- Do not use market-intelligence data to shape voice or content style; SEO may identify opportunity, never style.
- Keep files generic and reusable.
