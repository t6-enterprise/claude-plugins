# T6 Enterprise for Claude

Connects Claude Code to your T6 Enterprise tenant. After you sign in, Claude can use your tenant's MCP tools for Explorer, forms, data tables, workflows, scenarios and more. Each call runs with your T6 Enterprise permissions. Tenants with audit logging enabled record tool calls in their audit trail.

## Install

```
claude plugin install t6-enterprise --marketplace t6-enterprise/claude-plugins
```

Inside Claude Code, run `/plugin install t6-enterprise --marketplace t6-enterprise/claude-plugins`. Installation does not ask for a tenant URL.

## Sign in

Run `/mcp`, choose `plugin:t6-enterprise:t6` and **Authenticate**. Your browser opens the shared T6 Enterprise page, where you enter your company name or tenant address. You are then sent to that tenant's sign-in page and a consent window naming `Claude Code (plugin:t6-enterprise:t6)`; approve it to connect. Connected clients can be revoked at any time in T6 Enterprise under Profile → Options → External Access.

## Requirements

- The tenant administrator has turned on the **MCP Server** preview feature.
- Your user has the **Access MCP server** permission.

## Notes

- The tenant is selected when you authorize the MCP connection. To use another company, start a new MCP authorization and select that tenant.
- The plugin contains no tools and no credentials. It registers `https://tai-mcp.tech6cloud.com/mcp`; the tools are the ones your selected tenant lists.
- If your Claude app can't use this plugin, add `https://tai-mcp.tech6cloud.com/mcp` as a custom connector instead and choose your company when signing in.

## Update from version 1.0.1

Update the plugin and restart Claude Code so it loads the shared server URL. Authenticate the MCP connection again and choose your company on the T6 Enterprise page. The previous `tenant_url` setting is no longer used.

## Data and privacy

The plugin sends MCP requests through `https://tai-mcp.tech6cloud.com/mcp`, which routes them to the tenant selected during authorization. Sign-in and consent happen on your tenant's own site. Tool calls and their results travel between Claude and T6 Enterprise under your own user. The plugin has no tenant-address setting and bundles no credentials or business data; Claude manages the OAuth connection.

- Privacy policy: https://tech6group.com/en/home-en/privacy-policy/
- Support: https://tech6group.com/en/home-en/contact/
