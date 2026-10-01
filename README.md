# Context Control Platform Plugin

This local Agent Plugins package bundles a platform-specific Copilot plugin for the Context Control SaaS product.

## Included components

- Portable plugin manifest
- MCP server configuration for the platform gateway
- Platform operations skill
- Health audit skill
- Daily automation template
- Copilot-specific custom agent definition

## Enable in VS Code

Add the folder to `chat.pluginLocations` in your settings:

```json
{
  "chat.pluginLocations": {
    "/path/to/context-control-platform": true
  }
}
```

Then reload the window or reopen the Agent Customizations view.

## Scope

This plugin is intentionally focused on the platform's existing architecture:
- multi-tenant workflow safety
- MCP tool usage and platform orchestration
- task scheduling and health auditing
- profile and team management guidance

It does not assume a generic SaaS setup. It is built to match the real Context Control platform described in the app README.
