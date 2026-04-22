# Handoff Contracts v02

## Required fields for all handoffs

- `handoff_id`
- `run_id`
- `from_agent`
- `to_agent`
- `task_class`
- `artifact_type`
- `summary`
- `reason`
- `inputs_used`
- `files_read`
- `proposed_next_step`
- `severity`
- `timestamp`

## Content-specific artifacts

### approved_brief
Must contain:
- target audience
- learning goal
- content type
- cluster or page target
- required teacher intent
- required internal linking intent
- no-go zones
- brand notes
- pedagogy notes

### brand_brief_review / brand_draft_review
Must contain:
- pass / conditional / fail
- uniqueness assessment
- Planerium-fit assessment
- filler-risk assessment
- required revisions

### pedagogy_brief_review / pedagogy_draft_review
Must contain:
- pass / conditional / fail
- learning-value assessment
- age-fit assessment
- teacher-usefulness assessment
- busywork-risk assessment
- required revisions

### rollback_recommendation
Must contain:
- change description
- observed regression
- evidence
- severity
- rollback urgency
- safer next step

## Prohibited handoffs

- untyped free-form collaboration
- content approval without guardian artifact
- risky write request without explicit severity
- memory promotion without evaluation artifact
