---
argument-hint: [demo-day or setup focus]
description: Check readiness for the Trade Ops Agent demo
---

# Trade Ops Demo Preflight

Check readiness for the Trade Ops Agent demo. The requested focus is:
**$ARGUMENTS**

## Critical Rules

- Do not print secrets.
- Do not run the pipeline manually.
- Do not send emails unless the user explicitly asks to run the demo.
- Prefer checking readiness over changing live infrastructure.

## Repo Setup

Use the first available repo location:

1. Current workspace, if it contains `scripts/demo.py` and `DEMO_SETUP.md`.
2. `/workspace/project/trade-confirm-demo`, if present.
3. Clone `https://github.com/rajshah4/trade-confirm-demo` into the workspace.

Change into that repo directory. Then run:

```bash
git pull --ff-only origin main
uv sync
uv run python scripts/demo.py preflight
uv run python scripts/demo.py status
```

If the user says this is demo day or explicitly asks to renew Gmail watch, run:

```bash
uv run python scripts/demo.py activate-watch
```

If the user asks to repair Sheet headers, run:

```bash
uv run python scripts/demo.py preflight --create-headers
```

## Readiness Checklist

- Rajistics secrets exist:
  - `GMAIL_TOKEN_JSON`
  - `ANTHROPIC_API_KEY`
  - `LMNR_PROJECT_API_KEY`
  - `TRADE_SHEET_ID`
  - `SLACK_WEBHOOK_URL`
- Gmail watch uses label `trade-confirmations-watch`.
- Pub/Sub pushes to the Cloud Run signing shim.
- Cloud Run shim has `DEBOUNCE_SECONDS=60` and max instances `1`.
- Google Sheet is reachable.
- Status command returns Sheet-backed trade metrics.
- Analytics URL is `https://analytics.app.replicated.rajistics.com/`.

## Output Format

- **Ready**
- **Needs attention**
- **Commands run**
- **Demo-day reminder**
