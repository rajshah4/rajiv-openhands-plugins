# Rajiv OpenHands Plugins

A personal OpenHands plugin marketplace seeded from the public sample plugins repo and extended with a few higher-signal demo plugins.

## Marketplace structure

```text
rajiv-openhands-plugins/
├── .claude-plugin/
│   └── marketplace.json
└── plugins/
    ├── city-weather/
    ├── magic-test/
    ├── repo-primer/
    ├── incident-brief/
    └── release-ready/
```

## Included plugins

### city-weather

Sample weather lookup plugin copied from `jpshackelford/openhands-sample-plugins`.

### magic-test

Simple smoke test plugin copied from `jpshackelford/openhands-sample-plugins`.

### repo-primer

Use this when you want the agent to build a fast mental model of the current codebase, including architecture, entry points, likely edit surfaces, and test commands.

Example:

```text
/repo-primer:scan auth and request routing
```

### incident-brief

Use this when you have a bug report, outage, or failing deploy and want the agent to turn the context into a compact operator brief with hypotheses and next actions.

Example:

```text
/incident-brief:brief API 500s after latest deploy
```

### release-ready

Use this when you want the agent to turn a change description into a rollout checklist with validation, monitoring, and rollback guidance.

Example:

```text
/release-ready:check enable custom sandbox image support for enterprise
```

## Marketplace source

Once this repo is pushed to GitHub, the OpenHands marketplace source would look like:

```text
github://rajshah4/rajiv-openhands-plugins
```

## Sample next additions

Good follow-on plugins to add:

- a customer-demo plugin that turns notes into a tailored demo script
- a docs-drafter plugin for release notes or customer updates
- a bug-repro plugin that turns a failing report into a step-by-step repro plan
