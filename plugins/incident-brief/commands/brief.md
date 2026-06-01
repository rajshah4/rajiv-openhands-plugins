---
argument-hint: <incident context>
description: Turn incident context into a brief with hypotheses and next actions
---

# Incident Brief

Use this command when the user needs an operator-style incident brief for: **$ARGUMENTS**

## Instructions

1. Restate the incident clearly in operational terms.
2. Identify:
   - current symptoms
   - likely blast radius
   - top hypotheses
   - missing data that would reduce uncertainty
   - immediate next actions
3. If there is repo or runtime context available, use it.
4. Keep the output brief enough for a Slack or incident-channel update.

## Output format

- **Situation**
- **Likely impact**
- **Top hypotheses**
- **What to check next**
- **Suggested status update**

## Notes

- Prefer concrete next actions over generic advice.
- If evidence is weak, say so explicitly instead of pretending certainty.
