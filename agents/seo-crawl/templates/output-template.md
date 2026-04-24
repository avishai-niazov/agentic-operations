# SEO & Crawl Report — <report_id>

> Use this template for every SEO & Crawl output. Observation and recommendation must be separated. Findings without routing are not complete.

## Report metadata

- **Report id:** <id>
- **Trigger:** daily audit | weekly review | GSC anomaly | template change | post-publish
- **Author:** <agent or operator>
- **Date:** <YYYY-MM-DD>
- **Scope:** sitewide | hub | template class | URL set

## Inputs consulted

- Indexation policy: read ✓
- Taxonomy map: read ✓
- Hub strategy: read ✓
- Internal linking rules: read ✓
- GSC export: <path or "none">
- Sitemap snapshot: <path or "none">
- Internal-link graph: <path or "none">

## Findings

For each finding, use this block:

### Finding <n>

- **Observation:** <what the data shows — URLs, counts, deltas>
- **Hypothesis:** <most likely cause>
- **Confidence:** high | medium | low
- **Root-cause class:** technical fix | content gap | taxonomy | hybrid
- **Recommendation:** <what to do — concrete, not "investigate">
- **Routing target:** Technical Health | Content Strategy | Governance & Security | (split — list components)
- **Risk if ignored:** <one line>
- **Risk of the fix itself:** <one line>

(Repeat for each finding. If no findings, write "No findings.")

## Cross-cutting observations

- <patterns across findings — e.g., "eight thin pages in hub H suggest a merge/retire cycle, not eight individual fixes">

## Guardrail checks

- Indexation policy respected: yes / no — <note>
- People-first / thin-content guardrail respected: yes / no — <note>
- No direct robots / canonical / sitemap writes proposed from this report: confirmed ✓

## Routing summary

- Technical Health: <count> findings routed — <reference>
- Content Strategy: <count> findings routed — <reference>
- Governance & Security: <count> findings routed — <reference>
- Memory writebacks: <paths under `knowledge/memory/known_failures/` or "none">

## Trace

- Trace record at: <path under `runs/traces/`>

## Sign-off

- Author: __________
- Checklist walked: yes / no
- Date: __________
