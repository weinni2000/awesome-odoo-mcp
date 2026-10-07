# Awesome Odoo MCP

A curated list of MCP (Model Context Protocol) servers, tools, and resources for Odoo.

Missing something? [Open a PR](https://github.com/weinni2000/awesome-odoo-mcp/pulls) or send a mail to [weinni2000@gmail.com](mailto:weinni2000@gmail.com).

---

## Official Odoo MCP Server (built into the AI app)

Odoo's own MCP server, shipped with the **AI** app. Documented for Odoo 20.0 and Odoo Online saas-19.4 (no MCP page in the 19.0 docs). The AI module is not in the public Community repository.

| Item | Details |
|---|---|
| Endpoint | `<database_url>/mcp` (e.g. `https://example.odoo.com/mcp`) |
| Authentication | Static API key: My Preferences → Security → Add API Key, scope **MCP**, with an expiry period |
| Tools | Server actions. Exposed by default: Get Fields, Get Models, MCP Retrieve initial context, Search, Read group |
| Write access | Other tools must be exposed manually: Settings → Technical → Server Actions (developer mode) → *Usage* tab → **Available in MCP** |
| Readonly Tool flag | Only tells the client the tool can run without user approval; it does not hide the tool |
| Documented clients | Claude (Desktop / Code), Antigravity, Codex — via `npx mcp-remote` (Node.js required on the client) |
| Docs | [20.0](https://www.odoo.com/documentation/20.0/applications/productivity/ai/mcp_server.html) · [saas-19.4](https://www.odoo.com/documentation/saas-19.4/applications/productivity/ai/mcp_server.html) |

---

## External MCP Servers (standalone Python)

These run as a separate process alongside your AI client (Claude Desktop, Cursor, VS Code, etc.) and connect to Odoo via XML-RPC, JSON-RPC, or (Odoo 19+) the JSON-2 External API.

> **Note:** Since Odoo 19.0, the XML-RPC and JSON-RPC endpoints (`/xmlrpc`, `/xmlrpc/2`, `/jsonrpc`) are deprecated and scheduled for removal in Odoo 22 (fall 2028) and Odoo Online 21.1 (winter 2027). The JSON-2 External API replaces them and is not affected by this deprecation (in the table below, AlanOgic/odoo-mcp-19 already uses JSON-2). See the [deprecation notice](https://www.odoo.com/documentation/19.0/developer/reference/external_rpc_api.html).

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
| Much | — | [mcp_server (17.0)](https://apps.odoo.com/apps/modules/17.0/mcp_server) / [mcp_server (19.0)](https://apps.odoo.com/apps/modules/19.0/mcp_server) | [weinni2000](https://github.com/weinni2000) | Odoo-side server component; pairs with a separate Python MCP client package |
| OE Service | — | [oe_mcp (18.0)](https://apps.odoo.com/apps/modules/18.0/oe_mcp) | — | MCP Connector Suite; supports Anthropic Claude, OpenAI, Azure OpenAI |
| unknown | — | [odoo_mcp (19.0)](https://apps.odoo.com/apps/modules/19.0/odoo_mcp) | — | REST API + XML-RPC endpoint; compatible with Claude, Cursor, VS Code Copilot |
| unknown | — | [odoo_ai_mcp (19.0)](https://apps.odoo.com/apps/modules/19.0/odoo_ai_mcp) | — | AI Agent + Copilot; MCP protocol support |
| keshrath | — | [blazing_mcp_server (18.0)](https://apps.odoo.com/apps/modules/18.0/blazing_mcp_server) | — | Native Odoo MCP server; Claude, Cursor, Codex can drive Odoo directly |
| unknown | — | [llm_mcp_server (18.0)](https://apps.odoo.com/apps/modules/18.0/llm_mcp_server) | — | LLM-focused MCP server addon |
| unknown | — | [mcp_connector (16.0)](https://apps.odoo.com/apps/modules/16.0/mcp_connector) | — | Early MCP connector for Odoo 16 |
| Niyu Labs | — | [niyu_mcp_server (16.0–20.0)](https://apps.odoo.com/apps/modules/19.0/niyu_mcp_server) | — | Commercial; Community & Enterprise 16–20 incl. Odoo.sh/on-prem; OAuth 2.1 + PKCE, per-user access bundles, audit log, rate limiting, IP allowlist; works with Claude, ChatGPT, Gemini, Cursor, n8n |
| Brain Grain | — | [safe_mcp_connector (19.0)](https://apps.odoo.com/apps/modules/19.0/safe_mcp_connector) | — | Commercial; every create/edit returns a before→after preview with single-use confirm; customer emails held until a person approves in Odoo; deletes off by default; per-user OAuth (user's own access rights); audit log; lives at `/safe_mcp` so it coexists with other `/mcp` addons; Claude desktop/web/mobile, Claude Code, Cursor |

---

## Resources

- [Model Context Protocol — official docs](https://modelcontextprotocol.io/)
- [Odoo Developer Docs](https://www.odoo.com/documentation/master/developer.html)
- [Odoo AI MCP server — official docs (20.0)](https://www.odoo.com/documentation/20.0/applications/productivity/ai/mcp_server.html)
- [Odoo External JSON-2 API (19.0)](https://www.odoo.com/documentation/19.0/developer/reference/external_api.html)
- [GitHub topic: odoo-mcp](https://github.com/topics/odoo-mcp)
- [GitHub topic: odoo-mcp-server](https://github.com/topics/odoo-mcp-server)
- [Odoo forum: How to connect Odoo to your AI using an MCP server](https://www.odoo.com/forum/help-1/how-to-connect-odoo-to-your-ai-using-an-mcp-server-297529)
- [Every Odoo MCP Server Compared (2026)](https://www.pantalytics.com/post/odoo-mcp-server-comparison-2026)
