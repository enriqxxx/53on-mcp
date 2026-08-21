# 53ON MCP Server

Official MCP (Model Context Protocol) server for **53ON** — a directory and marketplace of local businesses and independent professionals.

Agents find who does a job near a user, read ratings and prices, and get a direct link to request a quote and pay.

## One-click install

[![Add to Cursor](https://img.shields.io/badge/Add%20to-Cursor-black?style=for-the-badge)](cursor://anysphere.cursor-deeplink/mcp/install?name=53on&config=eyJ1cmwiOiJodHRwczovLzUzb24uY29tL21jcCJ9)
[![Install in VS Code](https://img.shields.io/badge/Install%20in-VS%20Code-0098FF?style=for-the-badge)](https://insiders.vscode.dev/redirect/mcp/install?name=53on&config=%7B%22name%22%3A%2253on%22%2C%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2F53on.com%2Fmcp%22%7D)

**ChatGPT** (Developer Mode): Settings -> Connectors -> Add custom connector -> paste `https://53on.com/mcp`

**Claude Code**: `claude mcp add --transport http 53on https://53on.com/mcp`

## Connect

Remote server. No install, no npm, no auth.

```json
{
  "mcpServers": {
    "53on": { "type": "http", "url": "https://53on.com/mcp" }
  }
}
```

Transport: streamable-http (stateless). A `GET` returns 405 on purpose — POST a JSON-RPC 2.0 body.

## Tools

- **search_providers** — find businesses by what they do. Free text in Spanish or English, resolves synonyms (plumber and "destapar caneria" both map to Plumber). Pass `lat` and `lng` to narrow by area; an empty query returns the list of services covered.
- **get_business** — full public detail of one business by its slug: services, ratings, product catalog with prices, and the link where the user requests a quote and pays.

## Registry

Published on the official MCP Registry as `com.53on/directory`.

## Links

- Website: https://53on.com
- Agent guide: https://53on.com/AGENTS.md
- llms.txt: https://53on.com/llms.txt
- OpenAPI: https://53on.com/.well-known/openapi.json
- NLWeb ask endpoint: https://53on.com/ask?query=plumber

## License

MIT
