# Tool Contracts v02

## Contract fields

- tool_name
- purpose
- allowed_agents
- access_class
- required_inputs
- expected_outputs
- failure_modes
- retry_policy
- escalation_condition

## Contract examples

### GSC reader
- access_class: read_only
- allowed_agents: SEO & Crawl, Analytics & Evaluation, Content Strategy
- failure_modes: API unavailable, stale export, empty result
- escalation_condition: repeated query failure or data mismatch

### CMS publish writer
- access_class: sensitive_write
- allowed_agents: Governance-approved flows only
- failure_modes: auth failure, template mismatch, malformed payload
- escalation_condition: public-output risk

### DB cleanup writer
- access_class: sensitive_write
- allowed_agents: Technical Health only with governance approval
- escalation_condition: any integrity uncertainty
