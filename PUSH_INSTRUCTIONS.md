# Push Instructions

## Important

The connected GitHub tool in this session can write files to an existing repository, but it does not expose repository creation.

## Fast path

1. Create a new empty GitHub repository named `website-agentic-operations`
2. Upload or push this folder

## Command-line option

```bash
git init
git branch -M main
git add .
git commit -m "Initial scaffold for Website Agentic Operations Framework"
git remote add origin git@github.com:<your-user>/website-agentic-operations.git
git push -u origin main
```

## What to review first after pushing

- README.md
- CLAUDE.md
- HARNESS.md
- knowledge/content/brand_constitution_v01.md
- knowledge/content/pedagogical_charter_v01.md
- docs/architecture/runtime_state_model_v02.md
- docs/architecture/supervision_and_feedback_model_v01.md
- docs/architecture/agent_interaction_matrix_v02.md
- .claude/skills/
