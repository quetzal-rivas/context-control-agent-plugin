---
name: context-control-health-audit
description: Audit the platform for production readiness, queue health, RLS boundaries, and MCP tooling risks.
version: 1.0.0
triggers:
  - "health check"
  - "audit"
  - "mcp tool"
  - "queue"
  - "rls"
  - "production"
  - "security"
---

# Context Control Health Audit

Use this skill when the user asks for a health review, a production readiness check, or a security audit of the platform.

## Audit checklist

- Review the README and project structure for intended capabilities versus current implementation gaps.
- Confirm that tenant isolation and RLS-safe access are upheld.
- Check whether delayed tasks, MCP calls, and profile resolution paths are documented and validated.
- Look for fake or hardcoded behavior that should be backed by real services or tests.
- Inspect whether environment variables, secrets, and API keys are kept out of source control.

## Focus areas

1. Platform architecture
   - Confirm the project remains aligned with the stated multi-tenant, MCP-first architecture.

2. Task execution and scheduling
   - Review queue, scheduler, and deferred-task logic for retry, cancellation, and failure coverage.

3. Tenant safety
   - Ensure tenant IDs are enforced and that data access stays scoped to the current tenant.

4. Tooling security
   - Verify tool execution and credentials remain server-side and are not exposed to prompts.

5. Real implementation gaps
   - Flag anything fake, stubbed, or placeholder-like by comparing the code to the documented behavior.

## Recommended deliverable

Provide a short audit report with:
- strengths,
- risks,
- missing validation or safeguards,
- recommended next implementation steps with priority.

Keep output honest and concrete: do not claim success without validation or clearly call out unverified assumptions.
