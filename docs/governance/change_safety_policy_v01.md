# Change Safety Policy v01

## Purpose

State where faster AI-driven changes are acceptable and where stronger human review is required.

## Two scopes

### Leaf work
Isolated outputs that do not define the architecture other work depends on.

Examples:
- one-off reports
- explainers
- helper scripts
- demo assets
- documentation drafts
- local formatting utilities

### Core work
The trunk and branch parts of the system that many other parts depend on.

Examples:
- harness logic
- runtime states
- contracts and schemas
- permissions and governance rules
- constitutional files
- evaluation and promotion logic

## Policy

- Leaf work may move faster with lighter review.
- Core work requires stronger review, explicit reasoning, and better verification.
- AI must not refactor core architecture casually.
- A leaf change that touches a core file becomes core work.

## Required checks

### For leaf work
- trace
- basic sanity check
- obvious risk review

### For core work
- trace
- explicit change rationale
- contract impact review
- regression thinking
- verification bundle
- governance approval when the blast radius is meaningful
