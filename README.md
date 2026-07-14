# BubblaV for Claude Code

Connect [Claude Code](https://claude.com/claude-code) to your **BubblaV** AI chatbot. Once installed, Claude can search your knowledge base, read analytics, surface content gaps, manage conversations and leads, tune your chatbot persona, and more — all over OAuth. No API key to manage.

This is a [Model Context Protocol](https://modelcontextprotocol.io/) plugin that connects Claude Code to the BubblaV remote MCP server at `https://www.bubblav.com/mcp`.

## Install

```bash
# 1. Add the marketplace
/plugin marketplace add bubblav-org/bubblav-claude

# 2. Install the plugin
/plugin install bubblav@bubblav
```

The first time Claude calls a BubblaV tool, your browser opens the BubblaV OAuth consent screen. Sign in, pick the website you want Claude to manage, and approve. Claude Code handles the OAuth 2.1 + PKCE flow automatically — there are no secrets or tokens to copy.

> Don't have a BubblaV account yet? Create one (free) at [bubblav.com](https://www.bubblav.com) and add a website first.

## What you can do

Once connected, Claude has access to your chatbot's data and configuration:

- **Knowledge base** — search, add, delete, upload files, sync support tickets, and list knowledge sources.
- **Analytics & reports** — read reports, visitor insights, and hourly activity.
- **Conversations & leads** — list and search conversations, view unanswered questions, and export leads.
- **Insights** — most-asked questions, content gaps, and answerable questions.
- **Chatbot persona & widget** — read and update website settings, persona, and widget appearance.
- **Crawl sources & forms** — manage crawl URLs/sitemaps and build forms.
- **Handoff scenarios** (Pro+) — define when the bot hands off to a human.
- **Web scraping** — scrape a URL into your knowledge base.

## How it works

- The plugin declares a single remote MCP server (`type: http`) pointing at `https://www.bubblav.com/mcp`.
- On the first request the server returns `401` with a `WWW-Authenticate` header; Claude Code discovers the OAuth endpoints via `/.well-known` and runs the authorization flow with PKCE + dynamic client registration (RFC 7591).
- The resulting access token is a long-lived BubblaV MCP key, stored in your OS keychain. It never appears in the manifest.

## Requirements

- A BubblaV account with at least one website.
- Claude Code v2.x or later (for remote MCP server + OAuth support).

## Support

- Docs: [docs.bubblav.com](https://docs.bubblav.com)
- Email: [support@bubblav.com](mailto:support@bubblav.com)

## License

MIT
