---
description: Triage and respond to customer-facing web issues reported through GitHub issues
triggers:
  - cs-web-issues
  - cs web issue triage
  - customer web incident
  - github issue web incident
  - customer support web escalation
---

# CS Web Issue Response

Use this skill when a GitHub issue or support escalation clearly describes a customer-facing web problem that needs a repeatable triage, diagnosis, and remediation workflow.

## Purpose

This is the shared organizational skill for customer-support web incidents. It represents the workflow an engineer first proved locally, then made available through cloud automation so anyone on the team can use the same response pattern from GitHub issues.

## Workflow

1. Read the issue title, body, labels, screenshots, logs, and linked context.
2. Identify the affected surface:
   - public website
   - customer dashboard
   - authentication or signup flow
   - checkout or billing path
   - documentation or marketing page
   - unknown web surface
3. Classify severity and customer impact:
   - SEV1: broad outage, data loss risk, security exposure, or blocked revenue path
   - SEV2: major customer workflow degraded or unavailable for a segment
   - SEV3: limited workaround exists or issue affects a small segment
   - SEV4: cosmetic, documentation, or low-impact issue
4. Gather evidence before proposing a fix:
   - recent deploys or config changes
   - relevant app logs or monitoring links when available
   - reproduction steps
   - browser, device, account, region, and URL details
   - failing tests or local reproduction output
5. Diagnose the likely cause and name uncertainty explicitly.
6. Propose the smallest safe remediation.
7. If the evidence supports a code or config change, prepare a proposed change plan or PR with diagnosis, risk assessment, remediation, verification, and rollback notes.
8. Draft a concise customer-support update that can be pasted into an incident channel or support ticket.

## Guardrails

- Do not guess when evidence is missing. Ask for the missing URL, account scope, timestamp, screenshot, browser details, or reproduction steps.
- Do not perform high-risk actions without explicit human approval.
- Do not delete customer data, rotate secrets, disable security controls, or run broad destructive commands.
- Prefer reversible fixes and PR review for production-facing changes.
- Keep customer-facing language factual and non-speculative.
- Do not activate for generic website conversations unless the request is clearly about support or incident triage.

## Output Format

- **Issue summary**
- **Customer impact**
- **Severity**
- **Evidence gathered**
- **Likely cause**
- **Recommended remediation**
- **Verification plan**
- **Rollback plan**
- **Customer-support update**

## Automation Notes

When used from an OpenHands Cloud automation, the automation should be triggered by GitHub issues in the relevant product repository and should attach this plugin as the shared response policy. The resulting PR or issue comment should include enough evidence for another engineer to audit the action.
