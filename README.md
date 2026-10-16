# BubblaV for Claude

Manage your [BubblaV](https://www.bubblav.com) AI chatbot from Claude. BubblaV is an AI chatbot for businesses: it answers your customers' questions 24/7 with what you teach it, and hands chats to your team when needed.

With this plugin, Claude can check how your chatbot performs, find the questions it could not answer, teach it new knowledge, review conversations and leads, and change its persona and widget. The plugin connects to the BubblaV remote [MCP](https://modelcontextprotocol.io/) server at `https://www.bubblav.com/mcp` over OAuth. You do not need an API key.

The plugin works in Claude Code, Claude Desktop, claude.ai, and Cowork.

## Install

**From the Claude directory.** Find **BubblaV** in the [Claude directory](https://claude.ai/directory) and install it. In Claude Code, open `/plugin`, go to **Discover**, and search for BubblaV.

**From this repository (Claude Code).**

```bash
/plugin marketplace add bubblav-org/bubblav-claude
/plugin install bubblav@bubblav
```

**Connector only.** You can also add BubblaV as a connector without the plugin. In Claude, open **Customize → Connectors**, select **+**, then **Add custom connector**, and enter `https://www.bubblav.com/mcp`.

## Connect your account

The first time Claude calls a BubblaV tool, your browser opens the BubblaV sign-in page.

1. Sign in to BubblaV, or create an account.
2. Select the chatbot (website) that Claude can manage. If you do not have a website, you can create a chatbot without one.
3. Approve the request.

Claude runs the OAuth 2.1 flow with PKCE for you. There are no secrets or tokens to copy.

## What you can do

- **Check performance**: conversations, resolution rate, ratings, and response times for any date range.
- **Find gaps**: questions your chatbot could not answer, content gaps, and the questions people ask most.
- **Teach your chatbot**: add or remove knowledge, upload documents, add pages and sitemaps to crawl, and check crawl status.
- **Review conversations**: list, read, and search conversations, captured leads, and visitor insights.
- **Configure**: change the chatbot persona and instructions, the chat widget, the AI search widget, forms, flows, and custom webhook tools.
- **Install the widget**: get the embed code for your site.

Example prompts:

- "How is my chatbot performing this month?"
- "Which questions could my chatbot not answer last week?"
- "Add to my chatbot's knowledge: we are open Monday to Friday, 9 AM to 5 PM."

## Skills included

- **`add-chat-widget`**: gets the embed snippet for your chatbot and shows where to put it in your site or framework. In Claude Code, Claude can add the snippet to your project files when you ask.
- **`manage-custom-tools`**: creates, updates, lists, deletes, and turns on or off the custom webhook tools that your chatbot can call during a conversation.

## Data and privacy

- **What the plugin contains**: one MCP server declaration (`.mcp.json`) and two skills (Markdown files). It has no hooks, scripts, or executable code. It does not read your environment variables or local files on its own.
- **Where data goes**: the plugin sends requests only to `https://www.bubblav.com/mcp`. A request contains the tool name and the arguments that Claude sends for your request.
- **What data comes back**: data from the BubblaV chatbot that you authorized. This includes analytics, knowledge content, settings, and conversations. Conversations and leads can contain your visitors' names, email addresses, and messages.
- **Access**: one connection gives access to one chatbot. BubblaV creates an API key labeled **Claude** in your account for the connection. To disconnect, revoke that key in the BubblaV dashboard.
- **Audit log**: BubblaV logs every tool call. See **Integrations → MCP Settings → Audit Logs** in the dashboard.
- **Custom tools**: when you create a custom webhook tool, BubblaV's servers call the URL that you give, during visitor conversations. For `bearer` and `hmac` tools, BubblaV shows the secret key one time, in the tool response.
- **Policies**: [Privacy Policy](https://www.bubblav.com/privacy) · [Terms of Service](https://www.bubblav.com/terms)

## Requirements

- A BubblaV account. You can create one during the sign-in step.
- A Claude app with remote MCP support: Claude Code, Claude Desktop, claude.ai, or Cowork.

## Support

- Setup guide: [docs.bubblav.com/user-guide/integrations/claude](https://docs.bubblav.com/user-guide/integrations/claude)
- Tool reference: [docs.bubblav.com/developer-guide/mcp-server](https://docs.bubblav.com/developer-guide/mcp-server)
- Email: [support@bubblav.com](mailto:support@bubblav.com)

## License

MIT. See [LICENSE](LICENSE).
