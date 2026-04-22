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
- evaluation scorecard
- approved pattern writeback
- regression case writeback

## Quality rule

An output is invalid if:
- it lacks required fields
- it mixes recommendation with approval without saying which is which
- it omits severity for risky conditions
- it assumes permission it does not have
