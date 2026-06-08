---
argument-hint: [timeframe or question]
description: Read Sheet-backed trade status for the demo
---

# Trade Ops Demo Status

Answer the trade status request: **$ARGUMENTS**

## Critical Rules

- Use the Google Sheet through the trade repo status scripts.
- Do not answer from Slack history.
- Do not manually run `scripts/trade_confirmation_pipeline.py`.
- If the repo is not already selected, locate or clone
  `https://github.com/rajshah4/trade-confirm-demo`.

## Repo Setup

Use the first available repo location:

1. Current workspace, if it contains `scripts/demo.py` and `DEMO_SETUP.md`.
2. `/workspace/project/trade-confirm-demo`, if present.
3. Clone `https://github.com/rajshah4/trade-confirm-demo` into the workspace.

Change into that repo directory. Then run:

```bash
git pull --ff-only origin main
uv sync
```

## Commands

Default status command:

```bash
uv run python scripts/demo.py status
```

For JSON if the user asks for detailed rows or averages:

```bash
uv run python scripts/get_status.py --last-day --include-trades --format json
```

For Slack-formatted output:

```bash
uv run python scripts/get_status.py --last-day --include-trades --format slack
```

## Output Format

- **Timeframe used**
- **Total trades**
- **Confirmed trades**
- **Exception trades**
- **Average notional / trade**
- **Most recent trades**
- **Source**

For source, say: Google Sheet via `scripts/get_status.py`.
