---
name: deepnia
description: Create AI images, short videos and voice-overs on Deepnia from any AI agent through its MCP connector, price first then create, and get the link. Use it when the user asks for a picture, a video, an ad or a voice-over "with Deepnia".
---

# Deepnia

[Deepnia](https://deepnia.com/en) is an AI studio that creates images, short videos and voice-overs and publishes them to social networks. This skill lets an agent create on the user's Deepnia account through the Deepnia MCP server.

## Connect

MCP server (remote, HTTP, OAuth): `https://deepnia.com/mcp`

The user needs a Deepnia account with credits ([sign up](https://deepnia.com/en)). The first call opens a deepnia.com sign-in page; the user signs in and clicks **Allow**.

- **Claude**: Customize → Connectors → **+** → Add custom connector. Name it `Deepnia`, URL `https://deepnia.com/mcp`, then Connect.
- **ChatGPT** (web): chatgpt.com/plugins → **+** → Add custom MCP server. Name it `Deepnia`, URL `https://deepnia.com/mcp`, authentication OAuth.
- **Claude Code**: `claude mcp add --transport http deepnia https://deepnia.com/mcp`
- **Cursor and other MCP clients**: add a remote server named `deepnia` with the URL `https://deepnia.com/mcp`.

## Tools

| Tool | What it does |
|---|---|
| `get_credit_balance` | The user's credit balance. |
| `list_creation_options` | Models, formats, durations and voices available. |
| `quote_image`, `quote_video`, `quote_voiceover` | Price a creation. Nothing is charged. |
| `create_image`, `create_video`, `create_voiceover` | Create it from an accepted quote. |
| `get_creation` | Follow a creation and get its link. |
| `list_my_creations` | The creations this app started. |

## How to create (always in this order)

1. Understand the request: subject, format (square, vertical 9:16, horizontal 16:9), length for a video, language and tone for a voice-over.
2. Call `list_creation_options` when you need a model, a format or a voice you are not sure about.
3. Call the matching `quote_*` tool and **show the user the price in credits**.
4. **Create only after the user accepts that price.** Call the `create_*` tool with the quote. Never create without an accepted quote, and never re-run a create without a new quote.
5. Call `get_creation` until it is ready, then give the user the link. Every creation is also saved in **My media** on deepnia.com.

## Good to know

- Photos: for an image or a short video you can send up to 4 photos as public https links (JPEG, PNG or WebP, up to 10 MB), for example the user's product. Only send photos the user has the right to use.
- A refused or failed creation gives its credits back automatically. Suggest other words, another photo or another model.
- The user sets how many credits each connected app may spend per day in **Settings → Apps** on deepnia.com, and can disconnect the app there at any time.
- The app receives the user's e-mail address, credit balance and the creations it starts. Never a password or payment details.

## Examples

- "Make a square image of a lemon on a blue background with Deepnia."
- "Create a short vertical video of waves at sunset with Deepnia."
- "With Deepnia, read this text as a voice-over in a calm voice: 'Welcome to our shop.'"

## Links

- Website: https://deepnia.com/en
- Connector guide: https://deepnia.com/en/connectors/chatgpt-claude
- Support: support@deepnia.com
