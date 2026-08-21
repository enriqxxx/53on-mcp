# 53ON MCP Server

Official MCP (Model Context Protocol) server for **53ON** — a directory and marketplace of local businesses and independent professionals.

Agents find who does a job near a user, read ratings and prices, and get a direct link to request a quote and pay.

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
