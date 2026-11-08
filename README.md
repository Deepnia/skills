<p align="center"><img src="https://cdn.deepnia.com/emails/offre-850-v2/logo.png" width="96" alt="Deepnia"></p>

<h1 align="center">Deepnia</h1>

<p align="center">Create AI images, short videos and voice-overs, then publish them everywhere automatically.<br>
Use Deepnia from ChatGPT, Claude, Cursor and any AI agent.</p>

<p align="center"><a href="https://deepnia.com/en">Website</a> · <a href="https://deepnia.com/en/connectors/chatgpt-claude">Connector guide</a> · <a href="mailto:support@deepnia.com">Support</a></p>

## MCP server

| | |
|---|---|
| URL | `https://deepnia.com/mcp` |
| Transport | Streamable HTTP |
| Sign-in | OAuth with your [Deepnia account](https://deepnia.com/en) |

- **Claude**: Customize → Connectors → **+** → Add custom connector, URL `https://deepnia.com/mcp`.
- **ChatGPT** (web): chatgpt.com/plugins → **+** → Add custom MCP server, URL `https://deepnia.com/mcp`, OAuth.
- **Claude Code**: `claude mcp add --transport http deepnia https://deepnia.com/mcp`

The agent always gets the price first and shows it to you. Nothing is created until you accept.

## Agent skill

[`skills/deepnia/SKILL.md`](skills/deepnia/SKILL.md) teaches an agent how to use the Deepnia connector: price first, then create, then share the link.

```bash
npx skills add Deepnia/skills
```

## What you can create

- **Images**: square, vertical or horizontal, from text or from up to 4 photos of your product.
- **Short videos**: vertical for TikTok, Reels and Shorts, or horizontal.
- **Voice-overs**: many languages and voices.

Every creation is saved in **My media** on deepnia.com. A failed creation gives its credits back automatically.

This repository holds only the public agent skill and the MCP registry listing. It contains no application code.
