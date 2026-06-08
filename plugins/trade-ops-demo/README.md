# Trade Ops Demo Plugin

OpenHands plugin for running and narrating the Rajistics trade operations agent
demo.

## Commands

```text
/trade-ops-demo:story
/trade-ops-demo:status last day
/trade-ops-demo:run
/trade-ops-demo:preflight
/trade-ops-demo:slack
```

The plugin is intentionally a control surface. The implementation remains in
`rajshah4/trade-confirm-demo`, and the live demo is still triggered through
Gmail, Pub/Sub, and the Rajistics automation.
