---
name: videnly-faceless-video
description: Prepare, price, generate, and monitor an existing Videnly Faceless AI Video project through the connected Videnly MCP. Use when a user wants to validate a faceless-video project, learn what is missing, estimate its credit cost, explicitly approve generation, or retrieve its finished output.
---

# Videnly Faceless Video

Operate on an existing Faceless AI Video project without silently changing it.

## Workflow

1. Resolve the project with `list_projects` or `get_project`. If multiple projects match, ask the user to choose.
2. Call `prepare_faceless_video` to validate the project. Surface missing requirements in plain language and stop until they are resolved.
3. Call `estimate_faceless_video_cost` and present the exact credit cost and relevant project summary.
4. Stop and wait for explicit confirmation of that estimate.
5. Call `generate_faceless_video` with the matching estimate token and required confirmation value.
6. Monitor with `get_generation_status` or `list_queue` until completion or failure.
7. Deliver the completed video and a concise status summary.

## Guardrails

- Never create or modify project content unless the user separately requests it and the connected MCP exposes an appropriate tool.
- Never queue generation before explicit approval.
- Re-run preparation and estimation after any project change.
- Keep project and generation lookups scoped to the authenticated account.
- Do not expose internal identifiers unless the user needs them to disambiguate or troubleshoot.

Read [references/videnly-mcp.md](references/videnly-mcp.md) for the expected tool sequence and failure handling.
