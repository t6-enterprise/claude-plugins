# T6 Enterprise for Claude

Connects Claude Code through the shared T6 Enterprise MCP service. After you sign in, Claude can use the tools your selected tenant exposes for Explorer, forms, data tables, workflows and scenarios. Each call runs with your T6 Enterprise permissions.

## Install

```
claude plugin install t6-enterprise --marketplace t6-enterprise/claude-plugins
```

Inside Claude Code, run `/plugin install t6-enterprise --marketplace t6-enterprise/claude-plugins`. Installation does not ask for a tenant URL.

## Sign in

Run `/mcp`, choose `plugin:t6-enterprise:t6` and **Authenticate**. Enter your company name or registered tenant address on the shared T6 Enterprise page. The service redirects only to the configured sign-in host of an enabled tenant. Sign in there and approve the consent request for `Claude Code (plugin:t6-enterprise:t6)`. Manage connected clients in T6 Enterprise under Profile → Options → External Access.

## Requirements

- The tenant administrator has turned on the **MCP Server** preview feature.
- Your user has the **Access MCP server** permission.
- The tenant is available through the shared T6 Enterprise MCP service.

## Switch tenants

The plugin connects to one tenant at a time. Clear its current authorization, sign in again, and select the other company.

```sh
claude mcp logout plugin:t6-enterprise:t6
claude mcp login plugin:t6-enterprise:t6
```

## Connect outside the plugin

If your Claude app uses custom connectors, add `https://tai-mcp.tech6cloud.com/mcp` for a tenant available through the shared service. For an on-premises or private tenant outside the shared service, use the tenant MCP URL from your administrator. In Claude Code, run these commands from a network that can reach the tenant.

```sh
claude mcp add --transport http t6-direct https://tenant.example.com/mcp
claude mcp login t6-direct
```

## Update from version 1.0.1

Update the plugin and restart Claude Code to load the shared server URL. Authenticate again and choose your company. If your previous `tenant_url` is outside the shared service, use the direct connection above.

## Data and privacy

Tech6 operates the shared MCP service. It receives the company name or tenant address you enter during selection. Your tenant's site handles sign-in and consent. MCP requests and responses, including tool inputs and results that may contain business data, pass through the shared service to and from your selected tenant. Claude Code manages the OAuth connection.

When tenant security auditing is enabled, its audit trail can record the user, client, tool name, duration, outcome and error details.

- [Tech6 privacy policy](https://tech6group.com/en/home-en/privacy-policy/)
- [Support](https://tech6group.com/en/home-en/contact/)
