---
argument-hint: [focus]
description: Build a quick repo primer with architecture, entry points, and likely edit paths
---

# Repo Primer

Create a compact repo tour for the current workspace with emphasis on: **$ARGUMENTS**

## Instructions

1. Inspect the current repository structure before making assumptions.
2. Identify:
   - top-level app or service boundaries
   - entry points or bootstrap files
   - likely edit points for the requested focus
   - test or verification commands you would reach for first
3. Call out any missing context or risky assumptions.
4. Present the result as a concise working brief, not a long essay.

## Output format

- **What this repo appears to do**
- **Key directories and why they matter**
- **Entry points**
- **Likely edit surfaces for the requested focus**
- **How I would verify changes**

## Notes

- Prefer actual repo evidence over generic architecture language.
- If the workspace is very large, prioritize the files and directories most likely to matter first.
