# Last9 for Cursor

Stop switching tabs to debug production. Ask Cursor instead.

This plugin connects Cursor to [Last9](https://last9.io) so your AI assistant has live access to your logs, metrics, traces, and alerts. Ask "what caused the spike in errors at 3pm?" and get a real answer — from your actual production data, right there in the editor.

It works through MCP. Twenty-three tools covering logs, metrics, traces, APM, alerts, and change events. No copy-pasting. No context switching. The AI has the data.

## Get started

Install from the Cursor Marketplace. Run `/last9-setup` in chat, enter your Last9 org slug (it's in your Last9 URL: `app.last9.io/<org_slug>/...`), then reload and connect. Any Last9 role works — you don't need admin access.

Once connected, just talk to Cursor. "Show me the slowest endpoints from the last hour." "Were there any deploys before this alert fired?" "What's throwing the most exceptions?"

## Skills

`/last9-setup` — connects your Last9 account to Cursor.  
`/last9-debug` — walks through debugging a production issue with your live data.  
`/last9-investigate-alert` — investigates a firing alert end to end.

## Requirements

- [Last9 account](https://app.last9.io) with data flowing in via OpenTelemetry
- Cursor v2.6.0+

## Support

[Discord](https://discord.com/invite/Q3p2EEucx9) · [cs@last9.io](mailto:cs@last9.io) · [Docs](https://last9.io/docs/integrations/mcp/)
