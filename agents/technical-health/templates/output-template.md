# Technical Health Report — <report_id>

> Use this template for every Technical Health output (incident or maintenance). Observation and hypothesis must be separated. A report without risk level, blast radius, and next action is not complete.

## Report metadata

- **Report id:** <id>
- **Type:** incident | scheduled health check | performance regression | publish safety check
- **Severity (if incident):** sev-1 | sev-2 | sev-3 | low | n/a
- **Author:** <agent or operator>
- **Date:** <YYYY-MM-DD>
- **Affected surface(s):** <pages / templates / jobs / systems>

## Signal

> Copy verbatim. Do not paraphrase.

```
<raw signal, log excerpt, or diagnostic output>
```

- **First observed:** <ISO datetime>
- **Detection source:** alert | log | cron | DB diagnostic | performance snapshot | manual

## Diagnosis

### Observation

- <what is true, with evidence references>

### Hypotheses (ranked)

1. <leading hypothesis> — would be confirmed by <signal>, falsified by <signal>.
2. <alternative hypothesis> — <how to distinguish>.
3. <if applicable>

### Reads consulted

- Stack inventory ✓ / n/a
- Database map ✓ / n/a
- Filesystem map ✓ / n/a
- Tool contracts ✓ / n/a
- Approval matrix ✓ / n/a

## Risk classification

- **Technical risk:** low | medium | high | critical
- **Blast radius:** <description>
- **Data-integrity risk:** yes / no — <reasoning>
- **User-visible impact now:** <description or "none">

## Proposed action

- **Action:** <the smallest action that addresses the leading hypothesis>
- **Reversibility:** reversible within <time> | partially reversible | irreversible
- **Rollback plan:** <concrete steps, or "rollback candidate opened at <path>">

## Approval

- **Production write required:** yes / no
- **Approval matrix entry:** <reference>
- **Governance approval:** requested / granted / not required / pending
- **Reference:** <path to approval request>

## Adjacent-agent notifications

- SEO & Crawl: notified ✓ / n/a — <reason>
- Content Production: notified ✓ / n/a — <reason>
- Analytics & Evaluation: notified ✓ / n/a — <reason>
- Monetization & Merchandising: notified ✓ / n/a — <reason>

## Post-change observability

- **Signal to watch:** <what indicates success or regression>
- **Check-back time:** <ISO datetime>
- **Known-failure signature (if recognized):** <path under `knowledge/memory/known_failures/`>

## Next action

- **Status:** proposed | awaiting approval | approved | executing | resolved | blocked
- **Owner:** <agent or operator>
- **Next step:** <one line>

## Trace

- Incident / report artifact at: <path under `runs/incidents/` or `runs/reports/`>
- Trace record at: <path under `runs/traces/`>
- Rollback candidate (if any): <path under `runs/rollback_candidates/`>

## Sign-off

- Operator: __________
- Checklist walked: yes / no
- Date: __________
