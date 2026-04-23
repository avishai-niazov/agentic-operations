# Output Contracts v02

## Rule

Each agent must write outputs in a predictable shape so downstream agents do not infer intent from prose alone.

## Output classes

- issue ticket
- incident report
- content brief
- draft artifact
- guardian review
- approval request
- verification bundle
- evaluation scorecard
- approved pattern writeback
- regression case writeback

## Minimum output fields

Every typed output must state:
- artifact type
- owner agent
- purpose
- key evidence or inputs used
- risks or open questions
- next step recommendation

## Quality rule

An output is invalid if:
- it lacks required fields
- it mixes recommendation with approval without saying which is which
- it omits severity for risky conditions
- it assumes permission it does not have
- it claims completion without required verification
