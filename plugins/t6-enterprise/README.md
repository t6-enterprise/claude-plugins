# T6 Enterprise for Claude

Connects Claude Code to your T6 Enterprise tenant. After you sign in with your own T6 Enterprise user, Claude can use the operations your tenant exposes through its MCP server: Explorer, forms, data forms, workflows, scenarios, security and more, plus `ask_tai`, which hands a multi-step request to Tai, the T6 Enterprise assistant. Every call runs with your permissions and is recorded in your tenant's audit trail.

## Install

```
claude plugin install t6-enterprise --marketplace t6-enterprise/claude-plugins --config tenant_url=https://<your-tenant>
```

Inside Claude Code, `/plugin install t6-enterprise --marketplace t6-enterprise/claude-plugins` asks for the **Tenant URL** instead. Type the address of your tenant without a trailing slash and without `/mcp`.

## Sign in

Run `/mcp`, choose `plugin:t6-enterprise:t6` and **Authenticate**. Your browser opens your tenant's sign-in page and then a consent window naming `Claude Code (plugin:t6-enterprise:t6)`; approve it to connect. Connected clients can be revoked at any time in T6 Enterprise under Profile → Options → External Access.

## Requirements

- The tenant administrator has turned on the **MCP Server** preview feature.
- Your user has the **Access MCP server** permission.

## Notes

- One tenant per install. To change it, run `/plugin configure t6-enterprise@t6-enterprise`, restart Claude Code and sign in again.
- The plugin contains no tools and no credentials. It registers your tenant's `/mcp` endpoint; the tools are the ones your tenant lists.
- Claude Desktop and Claude.ai do not load Claude Code plugins. There, add `https://<your-tenant>/mcp` as a custom connector.
