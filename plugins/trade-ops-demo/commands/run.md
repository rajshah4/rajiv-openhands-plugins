---
argument-hint: [optional demo focus]
description: Trigger the live Trade Ops Agent demo by sending test emails
---

# Run Trade Ops Demo

Run the live email-triggered trade confirmation demo. The requested focus is:
**$ARGUMENTS**

## Critical Rules

- The demo trigger is email.
- Send the test trade emails and let Gmail/Pub/Sub trigger Rajistics.
- Do not manually run `scripts/trade_confirmation_pipeline.py`.
- Do not print secrets.
- Use `claude-sonnet-4-6`; do not change the model to Opus.

## Repo Setup

Use the first available repo location:

1. Current workspace, if it contains `scripts/demo.py` and `DEMO_SETUP.md`.
2. `/workspace/project/trade-confirm-demo`, if present.
3. Clone `https://github.com/rajshah4/trade-confirm-demo` into the workspace.

Change into that repo directory. Then run:

```bash
git pull --ff-only origin main
uv sync
GMAIL_TOKEN_JSON="${GMAIL_TOKEN_JSON}" uv run python scripts/demo.py send-emails
```

## Expected Result

- One clean AAPL trade email is sent.
- One MSFT exception trade email is sent with missing quantity.
- Gmail watch publishes to Pub/Sub.
- Cloud Run signing shim forwards the signed event to Rajistics.
- Rajistics automation starts a new OpenHands conversation.
- The automation writes one `CONFIRMED` row and one `EXCEPTION` row.
- Slack receives trade notifications if `SLACK_WEBHOOK_URL` is configured.
- Rajistics analytics receives Claude validation traces.

## Output Format

- **Emails sent**
- **Trade IDs**
- **Gmail Message IDs**
- **What to watch next**
- **Links**

Use these links:

- Rajistics: `https://app.replicated.rajistics.com/`
- Analytics: `https://analytics.app.replicated.rajistics.com/`
- Google Sheet:
  `https://docs.google.com/spreadsheets/d/1syj7m-Enbt1qpuxlAS5BkmEKQGsoVkLCc8Wek1FvFP8/edit`
