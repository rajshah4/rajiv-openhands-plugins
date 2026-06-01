---
argument-hint: <change description>
description: Build a rollout, validation, and rollback checklist for a release
---

# Release Readiness Check

Create a rollout checklist for: **$ARGUMENTS**

## Instructions

1. Interpret the requested change as a release candidate.
2. Produce a practical checklist covering:
   - pre-release validation
   - rollout steps
   - monitoring and success signals
   - rollback triggers
   - post-release follow-up
3. If the repo or current workspace suggests specific risks, include them.
4. Keep the checklist concrete enough that an engineer or operator could actually use it.

## Output format

- **Change summary**
- **Pre-release checks**
- **Rollout plan**
- **Monitoring plan**
- **Rollback triggers**
- **Follow-up tasks**

## Notes

- Prefer explicit checks and metrics over generic “test thoroughly” wording.
- If the change description is vague, make reasonable assumptions and name them.
