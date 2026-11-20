# T6 Enterprise Claude plugins

Claude Code plugin marketplace for [T6 Enterprise](plugins/t6-enterprise/README.md).

| Plugin | What it does |
|---|---|
| [`t6-enterprise`](plugins/t6-enterprise/) | Connects Claude to your T6 Enterprise tenant through its MCP server, signed in as your own user. |

Install:

```
/plugin install t6-enterprise --marketplace t6-enterprise/claude-plugins
```

or from a terminal:

```
claude plugin install t6-enterprise --marketplace t6-enterprise/claude-plugins
```

The plugin uses the shared MCP address. Choose your company on the T6 Enterprise page when you authenticate; no tenant URL is needed during installation.

Licensed under the [MIT License](LICENSE).
