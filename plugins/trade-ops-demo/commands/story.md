---
argument-hint: [audience or focus]
description: Tell the Trade Ops Agent demo story and live sequence
---

# Trade Ops Demo Story

Use this command to explain the Rajistics/OpenHands Trade Ops Agent demo. The
requested focus is: **$ARGUMENTS**

## Demo Context

This demo lives in `rajshah4/trade-confirm-demo`.

The live system is:

```text
Gmail trade confirmation email
  -> Gmail watch / Google Pub/Sub
  -> Cloud Run signing shim
  -> Rajistics automation
  -> OpenHands conversation clones trade-confirm-demo
  -> Claude validates the trade
  -> Google Sheet + Slack + Rajistics analytics
```

## Instructions

1. If the trade repo is available in the workspace, read `README.md`,
   `SETUP_QUICKSTART.md`, and `DEMO_SETUP.md` before answering.
2. If the trade repo is not available, use the context in this command and say
   that the repo was not present.
3. Frame this as a trade operations agent, not a script or parser.
4. Include the LangChain/LangSmith comparison point:
   - Rajistics/OpenHands is the agent control plane.
   - Rajistics analytics / Laminar provides model-call observability.
   - The model gateway story covers Azure routing, usage data, budgets, and
     limits.
5. Keep the output presentation-ready.

## Output Format

- **One-sentence pitch**
- **What the agent can do**
- **Live demo sequence**
- **What to show on screen**
- **Observability and gateway story**
- **Close**

## Demo Phrases

Use language like:

```text
This is a trade operations agent. It receives trade confirmations over email,
processes them automatically, keeps a live book of confirmed and exception
trades, and answers questions from Slack about what happened.
```

Avoid framing this as only a Gmail integration, parser, spreadsheet automation,
or local script.
