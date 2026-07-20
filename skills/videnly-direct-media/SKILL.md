---
name: videnly-direct-media
description: Safely generate a standalone image or video through the connected Videnly MCP. Use when a user requests direct media generation, wants a model or price estimate, supplies reference media, or asks to monitor and deliver a Videnly generation. Always estimate first and require explicit confirmation before spending credits.
---

# Videnly Direct Media

Generate standalone media with a strict estimate-confirm-generate boundary.

## Workflow

1. Call `list_media_models` and verify the canonical model ID and supported parameters.
2. Construct the smallest valid request that preserves the user's explicit prompt and constraints.
3. Call `estimate_media_generation`. This validates the request, returns the canonical credit cost, and produces a short-lived confirmation token without spending credits.
4. Present the model, output type, important settings, and exact credit charge. Stop and wait for explicit confirmation.
5. After confirmation, call `generate_media` with the unchanged estimated request, its matching token, and the required confirmation value.
6. Poll `get_generation_status` at a reasonable interval until the generation completes or fails.
7. Deliver the resulting media and summarize only useful settings. Explain failures in plain language.

## Safety and correctness

- Never generate before confirmation, even if the user originally said “generate.”
- Re-estimate after any model, prompt, reference, duration, size, quality, or count change.
- Never fabricate a confirmation token or reuse one for a different request.
- Do not guess model IDs. For example, use the live canonical ID returned for GPT Images 2.0.
- If authentication fails, report the exact Videnly MCP error and do not use a fallback generator.
- If credits are insufficient, present the shortage and, when possible, a cheaper enabled alternative.
- Treat generation count as billable. Show the total cost before offering multiple variants.

Read [references/videnly-mcp.md](references/videnly-mcp.md) for the expected tool sequence and recovery rules.
