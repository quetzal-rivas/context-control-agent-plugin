---
name: context-control-platform-ops
description: Operate the Context Control platform safely across profiles, tasks, teams, tools, and tenant configuration.
version: 1.0.0
triggers:
  - "context control"
  - "schedule task"
  - "profile"
  - "mcp"
  - "tenant"
  - "team blueprint"
  - "platform"
required_mcp_tools:
  - "list_team_blueprints"
  - "schedule_deferred_task"
  - "trigger_task_now"
  - "query_database_table"
---

# Context Control Platform Ops

Use this skill when the user needs to operate the platform, inspect state, or change workflows without breaking tenant isolation.

## Core principles

- Prefer the existing platform patterns in the repo over inventing new abstractions.
- Treat tenant isolation as a hard requirement.
- Favor the platform MCP server and task flows over ad hoc shell work.
- Keep tasks explicit: read-only inspection, scheduled workflow, or write operation.

## Working approach

1. Identify the likely area: Agent Studio, Team Builder, Task Calendar, Profiles, Sources, or MCP Hub.
2. Match the request to the repo's actual architecture and README.
3. Use MCP-backed actions for orchestration when available.
4. Keep changes small and explain the scope before executing them.
5. When a request touches secrets, vaults, or tenant data, never expose raw credentials.

## Safety checks

- Never suggest broad cross-tenant queries.
- Prefer read-only validation before executing a mutation.
- Encourage sandbox or test data for risky changes.
- Confirm target tenant, time, and expected effect before scheduling or triggering work.

## Typical tasks

- Review platform configuration and identify the likely code path.
- Inspect profile, worker, and tool-permission relationships.
- Diagnose issues with scheduling, queue execution, or event triggers.
- Suggest safe changes to context compilation, RAG ingestion, or MCP mappings.
- Draft or validate a request before invoking a platform action.

## Output style

Provide concise, concrete guidance that connects the user goal to the relevant platform module, likely file or endpoint, and the minimal next step.
