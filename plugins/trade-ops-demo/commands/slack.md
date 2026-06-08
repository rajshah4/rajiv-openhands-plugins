---
argument-hint: [slack question or desired action]
description: Provide Slack prompts and operating guidance for the Trade Ops Agent demo
---

# Trade Ops Demo Slack Commands

Help with Slack usage for the Trade Ops Agent demo. The requested focus is:
**$ARGUMENTS**

## Context

The native OpenHands Slack app in `#trades` creates Rajistics conversations.
Until the instance supports a permanent channel default repo/plugin, include the
repo name in natural-language Slack prompts.

## Recommended Slack Prompts

Use:

```text
@OpenHands in trade-confirm-demo what can you do for the trade demo?
@OpenHands in trade-confirm-demo what are the last day's trades?
@OpenHands in trade-confirm-demo run the trade confirmation demo
```

If plugin commands are available in the Slack-created conversation, use:

```text
/trade-ops-demo:story
/trade-ops-demo:status last day
/trade-ops-demo:run
/trade-ops-demo:preflight
```

## Rules for Slack Answers

- Status answers must come from the Google Sheet through the repo status
  scripts.
- Do not answer status questions from Slack message history.
- Demo runs should send test emails and let the Gmail automation trigger.
- Do not manually run `scripts/trade_confirmation_pipeline.py`.

## Output Format

- **Best prompt to use**
- **What it should trigger**
- **What to watch**
- **Known limitation**

For known limitation, say that no-repo Slack conversations may not load repo
skills, so including `in trade-confirm-demo` is still the safest prompt.
