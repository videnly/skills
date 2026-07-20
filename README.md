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

Install from the public repository with the [Skills CLI](https://www.skills.sh/docs/cli):

```bash
npx skills add videnly/skills
```

The CLI discovers the included skills and installs them for supported agents. Depending on the detected client and terminal mode, it may install automatically or present a selector containing:

- `videnly-direct-media`
- `videnly-faceless-video`

Install one skill globally:

```bash
npx skills add videnly/skills \
  --skill videnly-direct-media \
  --global
```

Install every skill non-interactively:

```bash
npx skills add videnly/skills --all
```

The Skills CLI supports Codex, Claude Code, Cursor, GitHub Copilot, and other Agent Skills-compatible clients.

### MCP authentication

Installing a skill does not universally configure or authenticate its MCP dependency. If the client does not configure it automatically from the included metadata, connect the Videnly MCP manually:

```text
https://mcp.videnly.com
```

The client will open Videnly's OAuth flow. Sign in and approve the requested permissions before using either skill.

## Repository catalog

`skills.json` provides machine-readable names, descriptions, source URLs, and tags for every published skill.
