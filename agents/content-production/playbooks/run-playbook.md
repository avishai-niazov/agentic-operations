# Run Playbook — Content Production

This playbook describes how to execute a Content Production run: producing a draft or refresh from an approved brief. It is a procedural companion to `.claude/skills/content-production/SKILL.md`.

## When to run

- an approved brief has arrived from Content Strategy (both guardian reviews passed)
- an approved refresh request has arrived

If either guardian review is missing or unresolved, stop — do not start drafting.

## Pre-flight

1. Open the approved brief and confirm both brand and pedagogy passes are recorded.
2. Open required reads from `SKILL.md`: brand constitution, pedagogical charter, voice and editorial rules, content templates, exemplar library.
3. Open relevant corpora: `knowledge/corpora/brand/`, `knowledge/corpora/pedagogy/`. **Do not** open or use `knowledge/corpora/market-intelligence/` as a voice source.
4. Pick the matching template from `content_templates_v01.md`.

## Step-by-step run

### Step 1 — Read the brief as the reader

Read the brief once, trying to see the content through the target audience. Note what the reader needs to leave with.

### Step 2 — Draft the structure before prose

Outline headings, teacher-use block (if required), FAQ questions, and internal-link candidates before writing prose. The structure should make the learning goal visible.

### Step 3 — Draft the prose

Write with the voice and editorial rules open. Prefer concrete examples and specific framings over abstractions. When stuck, compare to an approved exemplar rather than filling with generic connective tissue.

### Step 4 — Draft metadata and supporting blocks

- Title, meta description, social variants.
- Teacher-use block (if the template requires it).
- FAQ (real questions, not filler).
- Internal-link suggestions (real, relevant pages).

### Step 5 — Self-check against non-negotiables

Walk the draft against `knowledge/content/non_negotiables_v01.md`. Fix any issues before routing.

### Step 6 — Run the pre-route checklist

Walk `checklists/review-checklist.md`. If any item fails, fix or stop. Do not route a draft you already know has problems.

### Step 7 — Route

- Save to `queues/awaiting_guardian_review/`.
- Request brand draft review.
- Request pedagogy draft review.
- Emit a trace record.

### Step 8 — Respond to guardian outcomes

- **Both pass** — route onward per `SKILL.md` (SEO, Technical Health, Monetization, Governance as applicable).
- **Conditional on one** — apply the revision, re-route the affected review.
- **Fail on either** — accept the failure. Do not argue for exception. Return to the brief with findings via Content Strategy if structural issues are surfaced.

## Handling edge cases

- **Brief is approved but feels wrong on reading** — surface the concern back to Content Strategy before drafting. Don't produce a draft you don't believe in.
- **Exemplar for this shape doesn't exist yet** — draft carefully, flag in the trace, and propose the approved draft as a candidate exemplar (not a promotion; that goes through Analytics & Evaluation).
- **Claim can't be supported** — remove the claim or narrow it. Never invent a source.
- **Template asks for a block the content doesn't need** — flag upward; don't silently drop the block.

## Escalation

Escalate when:

- both guardian reviews fail structurally (not just wording),
- publishing a correct version would require a technical change (template, schema, etc.),
- disclosure or approval sensitivity appears mid-draft (monetization, data claim, partner mention).

Escalation: route via `queues/awaiting_review/` to Governance & Security with a trace.

## Definition of Done

- A draft exists in the required shape.
- It is self-checked against non-negotiables.
- It is routed to both guardian reviews.
- A trace record is emitted.
