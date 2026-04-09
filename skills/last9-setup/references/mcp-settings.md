# MCP JSON Registration Reference

This reference is shared across all Last9 plugin skills. Use the flows below to check server state, locate the registration file, or edit a value.

### Do not mention file paths or variable names to the user

File paths and variable values are implementation details. Describe the state ("the Last9 MCP server is not set up") or action ("the organization has been configured") without revealing them.

## Determine `last9-server-state`

Silently determine the state of the `plugin-last9-last9` MCP server using **only** these steps:

1. Try a lightweight MCP call on `plugin-last9-last9` (e.g. list tools).
2. If the server returns actual Datadog-specific data → state is **working**.
3. If the call fails or returns empty/generic data, silently read the registration file. Check for the literal string `not-setup`:
   - If the file contains `not-setup` → state is **not-setup**.
   - Otherwise → state is **not-working**.

Do not tell the user which state was determined or what was checked.

## Registration file

The registration file is `<plugin-root>/mcp.json`. It contains a URL with one shell-style template variable:

```
${LAST9_ORG_SLUG:-<current value>}
```

### Editing rule

The variable has the form `${NAME:-default}`. When editing, replace **only the default value** — the characters between `:-` and the closing `}`. The `${`, variable name, `:-`, and `}` must always remain intact.

Example — replacing the sentinel with an org slug:

```
${LAST9_ORG_SLUG:-not-setup}  →  ${LAST9_ORG_SLUG:-acme}
```

### The `not-setup` sentinel

A fresh installation has `not-setup` as the default org slug:

```
${LAST9_ORG_SLUG:-not-setup}
```

This value prevents the MCP server from connecting. It exists only before first-time setup and is replaced by `/last9-setup` with the real org slug.

## Finding the org slug

The org slug is in the user's Last9 URL when logged in:

```
https://app.last9.io/<org_slug>/...
```

For example, if their URL is `https://app.last9.io/acme/...`, the slug is `acme`.

If the user is unsure, suggest they log into [app.last9.io](https://app.last9.io) and check the URL bar.
