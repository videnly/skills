# Videnly Agent Skills

Portable agent skills for creating images and videos through the authenticated [Videnly MCP](https://mcp.videnly.com).

## Included skills

- `videnly-direct-media` estimates, confirms, generates, and delivers standalone media.
- `videnly-faceless-video` prepares and generates an existing Faceless AI Video project.

Every credit-spending workflow estimates the exact charge and waits for explicit user confirmation before generation.

## Connect the MCP

The repository includes `.mcp.json`:

```json
{
  "mcpServers": {
    "videnly": {
      "type": "http",
      "url": "https://mcp.videnly.com"
    }
  }
}
```

The MCP uses OAuth and restricts tools and data to the authenticated Videnly account.

## Install

Install the repository with an Agent Skills-compatible client or copy the desired folder from `skills/` into that client's skills directory. The MCP connection must also be enabled and authenticated.

## Repository catalog

`skills.json` provides machine-readable names, descriptions, source URLs, and tags for every published skill.
