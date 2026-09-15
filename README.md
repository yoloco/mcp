# Yoloco MCP Server: influencer marketing inside Claude, ChatGPT and Codex

[![MCP](https://img.shields.io/badge/MCP-remote%20server-6071FF)](https://modelcontextprotocol.io)
[![Auth](https://img.shields.io/badge/auth-OAuth%202.1-2ea44f)](SECURITY.md)
[![Networks](https://img.shields.io/badge/networks-Instagram%20%C2%B7%20TikTok%20%C2%B7%20YouTube%20%C2%B7%20Telegram-555)](#what-you-can-do)
[![Tools](https://img.shields.io/badge/tools-58-555)](TOOLS.md)

**Yoloco MCP Server** is a hosted [Model Context Protocol](https://modelcontextprotocol.io) server that
lets an AI assistant run influencer marketing on real creator data. Connect Claude, ChatGPT or Codex
to your [Yoloco](https://yoloco.io) account and ask in plain words: find creators on Instagram,
TikTok, YouTube and Telegram, check audience quality, build media plans, measure audience overlap,
see which creators your competitors sponsor and track campaign results.

Nothing to install. No API keys. You sign in with your Yoloco account, and every paid action is
priced and confirmed by you in the chat first.

```
https://mcp.yoloco.io/platform/mcp
```

Step-by-step guide with a client picker: **<https://app.yoloco.io/mcp>**

## Quick start

| Client | How to connect |
|---|---|
| **Claude** (claude.ai, Claude Desktop) | Settings → Connectors → Add custom connector → paste the server address → Add → Connect → sign in to Yoloco → Allow access. A connector added on claude.ai also appears in Claude Desktop. |
| **Claude Code** | `claude mcp add --transport http yoloco https://mcp.yoloco.io/platform/mcp`, then `/mcp` → `yoloco` → Authenticate. |
| **ChatGPT** (chatgpt.com) | Turn on Developer mode, then Settings → Apps & Connectors → Create → paste the server address, authentication OAuth → sign in to Yoloco → Allow access. |
| **Codex CLI** | `codex mcp add yoloco --url https://mcp.yoloco.io/platform/mcp`, then `codex mcp login yoloco`. |
| **Codex app / IDE extension** | Settings → MCP servers → Add server → name `yoloco`, Streamable HTTP, paste the server address → Save → restart. |
| **Cursor** | Settings → MCP → Add new MCP server, or add `"yoloco": {"url": "https://mcp.yoloco.io/platform/mcp"}` under `mcpServers` in `~/.cursor/mcp.json` → Connect → sign in to Yoloco. |
| **VS Code** (Copilot agent mode) | Command Palette → `MCP: Add Server` → HTTP → paste the server address, or add `"yoloco": {"type": "http", "url": "https://mcp.yoloco.io/platform/mcp"}` under `servers` in `.vscode/mcp.json` → Start → sign in to Yoloco. |
| **Windsurf** | Settings → Cascade → MCP servers → View raw config, add `"yoloco": {"serverUrl": "https://mcp.yoloco.io/platform/mcp"}` under `mcpServers` → Refresh → sign in to Yoloco. |

Codex app, IDE extension and CLI share `~/.codex/config.toml`:

```toml
[mcp_servers.yoloco]
url = "https://mcp.yoloco.io/platform/mcp"
```

Then ask:

> Find 20 beauty creators in Berlin with 50k to 200k followers and a real audience, then put the best
> ones into a media plan.

Not sure where to start? Ask for the menu or type `/yoloco_menu`: nine ready jobs, from finding creators to a
daily briefing, each one a single number to pick.

More ready-made requests for each stage of a campaign: [examples/PROMPTS.md](examples/PROMPTS.md).

## What you can do

| Stage | What the assistant does |
|---|---|
| **Brief** | Asks where the audience is first, never guessing it: a region, a market or a country (Europe → DACH → Germany, 199 countries). Then the missing questions one at a time, turned into a search plan with a coin budget per network. |
| **Discovery** | Searches creators on Instagram, TikTok, YouTube and Telegram by audience geo, language, age and gender, audience quality, ad readiness and topic. A smart search runs several strategies per network for free and returns one ranked list with the reasons each creator fits and flags for doubtful metrics, public pages and shops. Look-alikes of creators you already trust, saved searches. Every creator and post comes with a link. |
| **Vetting** | Paste a list of links and get a quality verdict on each: doubtful metrics, public pages and shops at once, audience quality from full reports. Full creator reports: audience demographics and quality, suspicious followers, growth, engagement, sponsored posts, contacts for outreach, ad frequency and expected ad views on Telegram. Side-by-side comparison of finalists from reports your team already opened, reused for free. |
| **Shortlists** | Lists and folders shared with the team, a list of the creators you picked in one step with their numbers filled in, free refresh of a list's data, likes and comments, "who already looked at this creator". |
| **Media plans** | Totals of reach, engagement, audience and prices; negotiated prices per creator with planned CPM before booking; Excel and PDF export. |
| **Audience overlap** | How many followers your finalists share, how much reach is really unique, and which set to keep for a number of creators or a budget (Instagram, TikTok, YouTube). |
| **Audience segments** | Instagram creators whose audience is interested in a topic, built from a plain-language description. |
| **Competitor ads** | Which creators a brand sponsored on YouTube and Telegram, how often, and how those posts performed. Who keeps coming back to a brand (repeat placements, long-term partners) and who works with several competitors. Several brands described at once, or a category's top brands. |
| **Campaign tracking** | A campaign straight from post links or the media plan with its prices; views, engagement, cost and CPM of published posts, plan against fact per creator, and a daily briefing with alerts. |
| **Team** | What each colleague did: reports opened, coins spent, creators looked at, searches, who has been idle. |

Full list of tools and slash commands: [TOOLS.md](TOOLS.md).

## How it works

1. Your AI client connects to `https://mcp.yoloco.io/platform/mcp` over streamable HTTP.
2. On the first call it opens a Yoloco page in your browser: you sign in and allow access (OAuth 2.1 with PKCE).
3. The assistant acts as you, inside your subscription, with your plan limits and your team's data.
4. Free actions happen right away. Paid actions return a price first and run only after you confirm.
5. Revoke access at any time in Yoloco: Settings → Integrations → AI assistant.

Details: [SECURITY.md](SECURITY.md).

## FAQ

**What is the Yoloco MCP server?**
A hosted connector that gives AI assistants access to Yoloco's influencer marketing data and tools
through the open Model Context Protocol. It works with Claude, ChatGPT and Codex.

**Do I need an API key or a developer?**
No. You sign in with your Yoloco account in the browser, like connecting Google Drive. It takes about
two minutes.

**Which social networks are supported?**
Instagram, TikTok, YouTube and Telegram.

**What does it cost?**
The assistant is included in Yoloco plans with the AI assistant feature and uses the coins of your
subscription, the same ones the app uses. Search previews, lists, media plans and campaign reading are
free. Full reports, paid search pages, overlaps, segments, competitor reports and some exports cost coins.

**Can the assistant spend coins without asking?**
No. Every paid action, paid search pages included, is quoted with its price and runs only after your explicit
confirmation in the chat. The billing itself refuses to charge more than the price you confirmed.

**Is my data shared with other customers?**
No. The assistant sees exactly what your account sees in the app. Conversation storage on the AI side
follows the AI provider's policy.

**Can my team use it?**
Yes. Each teammate connects with their own Yoloco login. The subscription owner sees and can revoke every
connection.

**Which languages does it understand?**
Any language the AI assistant understands. Answers come in your language.

## Links

* Connection guide: <https://app.yoloco.io/mcp>
* Plans: <https://app.yoloco.io/pricing>
* Help Center: <https://yoloco.gitbook.io/yoloco-knowledge-base-1>
* Website: <https://yoloco.io>

This repository contains documentation and the registry manifest ([`server.json`](server.json),
`io.yoloco/platform`). The server is operated by Yoloco. Changes: [CHANGELOG.md](CHANGELOG.md).

## License

This repository (documentation, examples and the server manifest) is released under the [MIT License](LICENSE).
The hosted server at `mcp.yoloco.io/platform` is a Yoloco service governed by the Yoloco terms of use.
