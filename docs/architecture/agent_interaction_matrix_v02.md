# Agent Interaction Matrix v02

## Rule

Agents do not exchange free-form messages.  
They exchange typed work artifacts.

## Matrix

| From | To | Artifact | Purpose |
|---|---|---|---|
| Intake & Triage | Technical Health | `incident_ticket` | Route technical issue |
| Intake & Triage | SEO & Crawl | `seo_issue_ticket` | Route search/crawl issue |
| Intake & Triage | Content Strategy | `content_opportunity_ticket` | Route content work |
| Intake & Triage | Monetization & Merchandising | `monetization_test_ticket` | Route monetization work |
| Technical Health | Governance | `risk_escalation` | Request approval or halt |
| Technical Health | Analytics & Evaluation | `incident_outcome` | Score impact and recurrence |
| SEO & Crawl | Technical Health | `technical_fix_request` | Request canonical, sitemap, template, or speed fix |
| SEO & Crawl | Content Strategy | `content_gap_request` | Request hub, refresh, or cluster coverage |
| Content Strategy | Brand Steward | `brand_brief_review` | Validate idea fit before production |
| Content Strategy | Pedagogical Steward | `pedagogy_brief_review` | Validate educational value before production |
| Content Strategy | Content Production | `approved_brief` | Start production |
| Content Production | Brand Steward | `brand_draft_review` | Validate draft identity |
| Content Production | Pedagogical Steward | `pedagogy_draft_review` | Validate draft pedagogy |
| Content Production | SEO & Crawl | `seo_safety_check_request` | Check indexing and internal link implications |
| Content Production | Technical Health | `technical_publish_check_request` | Check page and template risk |
| Content Production | Monetization & Merchandising | `monetization_safety_check_request` | Check ad and affiliate implications |
| Any operator | Governance | `approval_request` | Risky write, external action, or policy-sensitive change |
| Any operator or guardian | Analytics & Evaluation | `verification_bundle` | Submit structured verification evidence |
| Analytics & Evaluation | Memory | `approved_pattern_writeback` | Promote proven pattern |
| Analytics & Evaluation | Memory | `regression_case_writeback` | Preserve failure pattern |
| Analytics & Evaluation | Content Strategy | `revise_brief` | Send back weak outcome |
| Analytics & Evaluation | Governance | `rollback_recommendation` | Flag reversion need |

## Interaction rule summary

- Operators move work forward.
- Guardians approve or block.
- Evaluation critiques and controls learning.
- Governance protects boundaries.
- The harness supervises the sequence and completion criteria.
