<div align="center">

<a href="https://patcherly.com"><img src="https://patcherly.com/assets/img/logo_patcherly_light.png" alt="Patcherly" width="280" /></a>

**Connect your AI assistant to Patcherly**

Official IDE plugins and MCP install configs for [Patcherly](https://patcherly.com): triage errors, review sites, and export workspace data with your Patcherly account permissions.

**For a limited time**, new accounts include a **30-day trial** of the full **Pro** plan — **no credit card required**. Cancel anytime. [Sign up](https://patcherly.com) · [Pricing](https://patcherly.com/pricing) · [Trial help](https://help.patcherly.com/billing/trial/).

[![MCP Plugins](https://img.shields.io/github/v/release/Patcherly-Official/patcherly-mcp-plugins?label=MCP%20Plugins&style=flat-square&color=10b981)](https://github.com/Patcherly-Official/patcherly-mcp-plugins/releases)
[![Help](https://img.shields.io/badge/help.patcherly.com-1869f5?style=flat-square)](https://help.patcherly.com/integrations/connect-ai-assistant/)
[![Discord](https://img.shields.io/badge/Discord-join-5865f2?logo=discord&logoColor=white&style=flat-square)](https://discord.gg/7yZkD9KNsS)

</div>

---

## What's in this repo

| Path | Client | What’s included |
|------|--------|-----------------|
| [`cursor/`](cursor/) | Cursor | Hosted MCP connection + agent rules + skills (`patcherly-triage-error`, `patcherly-export-workspace-data`) |
| [`claude/`](claude/) | Claude Code | Hosted MCP connection + the same skills |
| [`codex/`](codex/) | ChatGPT / Codex | Hosted MCP connection + the same skills |

Public packages live in [Patcherly-Official/patcherly-mcp-plugins](https://github.com/Patcherly-Official/patcherly-mcp-plugins). Every client uses the same hosted MCP URL — no API keys to paste.

**Server URL:** `https://mcp.patcherly.com/mcp`

---

## Quick install

| Client | Action |
|--------|--------|
| **Cursor (one-click MCP)** | [Install Patcherly MCP in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=patcherly&config=eyJ1cmwiOiJodHRwczovL21jcC5wYXRjaGVybHkuY29tL21jcCJ9) |
| **Cursor (full plugin)** | [Cursor Directory](https://cursor.directory/plugins/patcherly), Cursor marketplace, or clone/use the [`cursor/`](cursor/) folder in this repo |
| **Claude Code** | `claude mcp add --transport http patcherly https://mcp.patcherly.com/mcp` then complete OAuth when prompted — or install the [`claude/`](claude/) plugin |
| **Codex CLI** | `codex mcp add patcherly --url https://mcp.patcherly.com/mcp` then complete OAuth when prompted — or install the [`codex/`](codex/) plugin |
| **VS Code / Copilot** | Add remote HTTP MCP at `https://mcp.patcherly.com/mcp` — see [MCP client setup](https://help.patcherly.com/integrations/mcp-client-setup/) |

After install, approve the connection in the Patcherly dashboard when your assistant asks you to sign in.

Manage or revoke connections anytime under **Profile → MCP**.

Help Docs: **[Connect your AI assistant](https://help.patcherly.com/integrations/connect-ai-assistant/)** · **[MCP client setup](https://help.patcherly.com/integrations/mcp-client-setup/)**.

---

## Support

- **[help.patcherly.com](https://help.patcherly.com)** — documentation and troubleshooting
- **[Discord](https://discord.gg/7yZkD9KNsS)** — community and questions
- **[Dashboard](https://app.patcherly.com)** — Profile → MCP for connections
- **[Report a bug](https://github.com/Patcherly-Official/patcherly-mcp-plugins/issues)** — plugin / install issues on this repo

---

## Licensing

IDE plugin trees in this repository are licensed under the [Apache License, Version 2.0](cursor/LICENSE).

**Patcherly** is a registered trademark, property of Shambix.

Using the **Patcherly service** is governed by our [Terms of Service](https://patcherly.com/legal/terms-of-service) and [Acceptable Use](https://patcherly.com/legal/acceptable-use) policy.
