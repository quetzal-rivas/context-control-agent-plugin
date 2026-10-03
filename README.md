# Context Control Platform Plugin

This Agent Plugins package bundles platform-specific Copilot guidance for the Context Control SaaS product.

## Included components

- Portable plugin manifest
- Platform operations skill
- Health audit skill
- Daily automation template
- Copilot-specific custom agent definition

## Connect the MCP server in Codespaces

The plugin does not embed an API key or a server URL. Agent Plugins 1.0 does not define portable secret references for remote MCP headers, and API keys must not be committed in plugin configuration.

Copy [examples/codespaces-mcp.json](examples/codespaces-mcp.json) into your project's `.vscode/mcp.json`, replace the example host with the current public URL for your forwarded port 3000, and use an API key whose whitelist includes the tools you need. VS Code will securely prompt for the key when the MCP server starts.

The platform MCP server is at `/api/mcp/platform`. Its available tools are:
- `list_mcp_profiles` (`mcp:profiles:read`)
- `list_scheduled_tasks` (`mcp:tasks:read`)
- `schedule_deferred_task` (`mcp:tasks:write`)

Task creation records a tenant-owned scheduled task. Actual future execution still requires the platform scheduler to be configured.

## Install the plugin

In VS Code, run **Chat: Install Plugin From Source** and enter this repository URL:

`https://github.com/quetzal-rivas/context-control-agent-plugin`

## Scope

This plugin is intentionally focused on the platform's existing architecture:
- multi-tenant workflow safety
- MCP tool usage and platform orchestration
- task scheduling and health auditing
- profile and team management guidance

It does not assume a generic SaaS setup. It is built to match the real Context Control platform described in the app README.
