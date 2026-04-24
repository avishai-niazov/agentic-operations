# Run Playbook — SEO & Crawl

This playbook describes how to execute an SEO & Crawl run. It is a procedural companion to `.claude/skills/seo-crawl/SKILL.md`.

## When to run

- daily audit window
- weekly crawl review
- GSC anomaly detected
- major template change shipped (post-publish safety check)

## Pre-flight

1. Open required reads: `indexation_policy_v01.md`, `taxonomy_map_v01.md`, `hub_strategy_v01.md`, `internal_linking_rules_v01.md`.
2. Open the latest sitemap snapshot, GSC export, and internal-link graph if available.
3. Identify the scope of this run (sitewide scan, specific hub, specific template).

## Step-by-step run

### Step 1 — Inspect search signals

Walk GSC coverage, performance, and any anomaly report. For anomalies, note the URL or pattern, the timing, and the magnitude.

### Step 2 — Inspect crawl and index surfaces

Look at:

- sitemap coverage vs. indexed
- canonical pointers and clusters
- orphan pages (no internal inbound links)
- near-duplicate clusters
- thin-content clusters

### Step 3 — Separate observation from recommendation

For every issue, write two lines:

- **Observation:** what the data shows.
- **Hypothesis:** the most likely cause.

Only then propose a recommendation. A finding without this separation is not ready to route.

### Step 4 — Classify root cause

Classify each finding as:

- **technical fix** (template, performance, canonical implementation, sitemap generation)
- **content gap** (thin, missing hub content, orphan due to missing sibling)
- **taxonomy issue** (category, tag, hub structure misaligned)
- **hybrid** (split into component work items)

### Step 5 — Route correctly

- Technical fix → Technical Health.
- Content gap → Content Strategy.
- Taxonomy → propose updated taxonomy map and route to governance for approval if sitewide.
- Sensitive changes (noindex, canonical at scale, sitemap rewrite) → Governance & Security.

### Step 6 — Write the output

Use `templates/output-template.md`. Include observation, hypothesis, recommendation, scope, and routing target.

### Step 7 — Walk the checklist

Walk `checklists/review-checklist.md` before routing.

### Step 8 — Emit trace

Always emit a trace record. Include which reads were consulted.

## Handling edge cases

- **Traffic drop with no crawl issue** — do not recommend SEO changes. Route to Analytics & Evaluation for content performance review.
- **Many thin pages found** — do not recommend "more content." Route to Content Strategy for merge / retire / improve decisions.
- **Canonical change proposed at scale** — always go through governance, even if the change looks safe.
- **Opportunity inferred only from competitor content** — treat as opportunity sizing only; do not let competitor content shape our voice or structure.

## Escalation

Escalate to Governance & Security when:

- sitewide search impact is uncertain,
- a canonical or robots change is implied,
- a content-quality concern conflicts with a search opportunity,
- a taxonomy change would touch many hubs.

## Definition of Done

- Issue is analyzed with observation separated from recommendation.
- Root cause is classified.
- Routing target is explicit and correct.
- Report is saved to `runs/reports/seo_*`.
- A trace record is emitted.
