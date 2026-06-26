# Awesome Odoo MCP

A curated list of MCP (Model Context Protocol) servers, tools, and resources for Odoo.

Contributions welcome — open a PR and add your entry.

---

## External MCP Servers (standalone Python)

These run as a separate process alongside your AI client (Claude Desktop, Cursor, VS Code, etc.) and connect to Odoo via XML-RPC or JSON-RPC.

| Vendor / Author | GitHub | Odoo App Store | Human Tested | Description |
|---|---|---|---|---|
| ivnvxd | [mcp-server-odoo](https://github.com/ivnvxd/mcp-server-odoo) | — | — | Full CRUD, standardized resources & tools; also on PyPI as `mcp-server-odoo` |
| tuanle96 | [mcp-odoo](https://github.com/tuanle96/mcp-odoo) | — | — | Turns any Odoo 16+ DB into an MCP server; no app install or admin access required |
| pantalytics | [odoo-mcp-pro](https://github.com/pantalytics/odoo-mcp-pro) | [mcp_server_odoo (19.0)](https://apps.odoo.com/apps/modules/19.0/mcp_server_odoo) | — | Claude, ChatGPT, Cursor, Windsurf connector; single `/mcp` endpoint; PRO version on App Store |
| Vauxoo | [mcp.odoo](https://github.com/Vauxoo/mcp.odoo) | — | — | MCP server + CLI; 12 tools (search_read, create, write, unlink, export/import, list_models, …) |
| alberto-re | [mcp-server-odoo](https://github.com/alberto-re/mcp-server-odoo) | — | — | Lightweight, extensible server focused on LLM tool integration |
| hachecito | [odoo-mcp-improved](https://github.com/hachecito/odoo-mcp-improved) | — | — | Extended fork with dedicated tools for sales, purchases, inventory, and accounting |
| AlanOgic | [odoo-mcp-19](https://github.com/AlanOgic/odoo-mcp-19) | — | — | Odoo 19+ only; uses v2 JSON-2 API; 5 tools, 27 resources, 13 prompts |
| sameeroz | [odoo-mcp-server](https://github.com/sameeroz/odoo-mcp-server) | — | — | General-purpose server; AI-driven automation and workflow management |
| yourtechtribe | [mcp-odoo-for-finance](https://github.com/yourtechtribe/model-context-protocol-mcp-odoo) | — | — | Finance-focused MCP server; accounting and invoice data access |
| keboola | [odoo-mcp](https://github.com/keboola/odoo-mcp) | — | — | OAuth 2.1 per-user identity, employee self-service, document signing |
| DalahmasDev | [odoo-sh-mcp-server](https://github.com/DalahmasDev/odoo-sh-mcp-server) | — | — | SSH-based; targets Odoo.sh with Git workflow tools for AI-assisted module dev |
| mart337i | [odoo-dev-mcp](https://github.com/mart337i/odoo-dev-mcp) | — | — | Developer-oriented; 302+ pages of Odoo docs searchable by AI; version-aware code generation for 17–19 |
| sarakhanx | [odoo-mcp-server](https://github.com/sarakhanx/odoo-mcp-server) | — | — | MVP / minimal implementation |

---

## Native Odoo Addons (installable modules)

These install directly into Odoo and expose an MCP endpoint from within Odoo itself.

| Vendor / Author | GitHub | Odoo App Store | Human Tested | Description |
|---|---|---|---|---|
| MuK IT GmbH | — | [muk_mcp (19.0)](https://apps.odoo.com/apps/modules/19.0/muk_mcp) | — | LGPL-3, open-source; `@mcp_tool` decorator for Python tools + UI-managed tools; works with Claude Code, Cursor, Codex CLI |
| foggy-projects | [foggy-odoo-bridge](https://github.com/foggy-projects/foggy-odoo-bridge) | — | — | Odoo addon with governed MCP access; preserves Odoo permission model; built-in AI chat |
| pantalytics | [odoo-mcp-pro](https://github.com/pantalytics/odoo-mcp-pro) | [mcp_server_odoo (19.0)](https://apps.odoo.com/apps/modules/19.0/mcp_server_odoo) | — | PRO App Store edition; single stable `/mcp` endpoint; build modules via AI |
| unknown | — | [mcp_base (19.0)](https://apps.odoo.com/apps/modules/19.0/mcp_base) | — | Odoo MCP Framework; `@mcp_tool` decorator; auto-discovery on startup |
| unknown | — | [mcp_server (17.0)](https://apps.odoo.com/apps/modules/17.0/mcp_server) | — | Odoo-side server component; pairs with a separate Python MCP client package |
| OE Service | — | [oe_mcp (18.0)](https://apps.odoo.com/apps/modules/18.0/oe_mcp) | — | MCP Connector Suite; supports Anthropic Claude, OpenAI, Azure OpenAI |
| unknown | — | [odoo_mcp (19.0)](https://apps.odoo.com/apps/modules/19.0/odoo_mcp) | — | REST API + XML-RPC endpoint; compatible with Claude, Cursor, VS Code Copilot |
| unknown | — | [odoo_ai_mcp (19.0)](https://apps.odoo.com/apps/modules/19.0/odoo_ai_mcp) | — | AI Agent + Copilot; MCP protocol support |
| keshrath | — | [blazing_mcp_server (18.0)](https://apps.odoo.com/apps/modules/18.0/blazing_mcp_server) | — | Native Odoo MCP server; Claude, Cursor, Codex can drive Odoo directly |
| unknown | — | [llm_mcp_server (18.0)](https://apps.odoo.com/apps/modules/18.0/llm_mcp_server) | — | LLM-focused MCP server addon |
| unknown | — | [mcp_connector (16.0)](https://apps.odoo.com/apps/modules/16.0/mcp_connector) | — | Early MCP connector for Odoo 16 |

---

## Resources

- [Model Context Protocol — official docs](https://modelcontextprotocol.io/)
- [Odoo Developer Docs](https://www.odoo.com/documentation/master/developer.html)
- [GitHub topic: odoo-mcp](https://github.com/topics/odoo-mcp)
- [GitHub topic: odoo-mcp-server](https://github.com/topics/odoo-mcp-server)
- [Odoo forum: How to connect Odoo to your AI using an MCP server](https://www.odoo.com/forum/help-1/how-to-connect-odoo-to-your-ai-using-an-mcp-server-297529)
- [Every Odoo MCP Server Compared (2026)](https://www.pantalytics.com/post/odoo-mcp-server-comparison-2026)
