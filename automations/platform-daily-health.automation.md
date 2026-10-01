---
version: 1
id: context-control-daily-health
name: Context Control Daily Health
description: Review the platform for regressions, queue issues, and MCP or tenant-safety concerns.
schedule:
  kind: cron
  expression: "0 9 * * *"
  timeZone: local
---

Review the latest workspace changes for the Context Control platform.

Check for:
- MCP or tool access regressions,
- schedule or queue reliability issues,
- tenant isolation or RLS concerns,
- missing configuration or broken platform assumptions,
- any production-readiness risks that should be fixed before deployment.

Summarize the most important findings and suggest the top three next actions.
