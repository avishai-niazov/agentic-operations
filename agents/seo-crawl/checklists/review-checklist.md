# Review Checklist — SEO & Crawl

Use this checklist before routing any SEO finding or recommendation. A recommendation routed without this check can cause sitewide search damage.

## 1. Signal and scope

- [ ] The signal source is named (GSC, sitemap scan, crawl log, internal-link graph, analytics).
- [ ] The scope is specified (single URL, template class, hub, sitewide).

## 2. Root-cause classification

- [ ] The finding has been classified as: **technical fix** | **content gap** | **taxonomy issue** | **hybrid**.
- [ ] Observation is separated from recommendation.
- [ ] "Hybrid" findings are split into component work items.

## 3. Indexation policy

- [ ] The finding respects `knowledge/seo/indexation_policy_v01.md`.
- [ ] No recommendation to index low-value or thin pages.
- [ ] Any noindex implication is explicit.

## 4. Canonical and sitemap integrity

- [ ] Proposed canonical changes are reviewed for cascade effects.
- [ ] Sitemap changes respect structure rules.
- [ ] Direct robots / canonical / sitemap writes are **not** proposed here — route to governance.

## 5. Hub and linking

- [ ] The finding respects `knowledge/seo/hub_strategy_v01.md` and `internal_linking_rules_v01.md`.
- [ ] No link-padding recommendations.
- [ ] Orphan handling, if proposed, is grounded in real audience value, not rescue-by-linking.

## 6. People-first and thin-content guardrails

- [ ] The recommendation does not optimize for search at the expense of reader value.
- [ ] No "produce more thin variants" patterns.
- [ ] No keyword-first framings that would steer voice.

## 7. Routing correctness

- [ ] Technical blockers → Technical Health.
- [ ] Content gaps → Content Strategy.
- [ ] Sensitive changes (robots, canonical at scale, sitemap at scale) → Governance & Security.
- [ ] Monetization surface impact, if any → Monetization & Merchandising for awareness.

## 8. Evidence discipline

- [ ] The finding cites observable data (URLs, counts, dates, GSC metrics).
- [ ] Hypotheses are labeled as hypotheses.
- [ ] Confidence level is stated.

## 9. Prohibited-action check

- [ ] No direct noindex or robots change from here.
- [ ] No voice shaping from competitor content.
- [ ] No approval of low-value scale ideas.

## Sign-off

- Reviewer: __________
- Finding id: __________
- Class: technical / content / taxonomy / hybrid
- Routed to: __________
- Date: __________
