# Last9 for Cursor

Your AI assistant should know what's broken in production. This plugin makes that possible.

It connects Cursor to [Last9](https://last9.io) via MCP so you can ask questions like "what caused the spike in errors at 3pm?" and get real answers from your actual logs, metrics, and traces — without leaving your editor.

## What you get

**23 live observability tools** wired directly into Cursor's AI:

- Search and filter production logs
- Run PromQL queries against your metrics
- Inspect distributed traces for latency or errors
- View service topology and dependency graphs
- List active alerts and alert history
- Correlate issues with deployments via change events

No copy-pasting log lines into chat. No switching tabs. The AI has the data.

## Setup

Install from the Cursor Marketplace, then run `/last9-setup` in chat. You'll need your Last9 org slug — it's in your Last9 URL: `app.last9.io/<org_slug>/...`.

The skill walks you through connecting the MCP server. Any Last9 role works; no admin access required.

## Skills

| Skill | What it does |
|---|---|
| `/last9-setup` | Connect your Last9 account |
| `/last9-debug` | Debug a production issue |
| `/last9-investigate-alert` | Investigate a firing alert |

## Requirements

- [Last9 account](https://app.last9.io) with data flowing in via OpenTelemetry
- Cursor v2.6.0+

## Support

[Discord](https://discord.com/invite/Q3p2EEucx9) · [cs@last9.io](mailto:cs@last9.io) · [MCP docs](https://last9.io/docs/integrations/mcp/)
