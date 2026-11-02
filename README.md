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
| erpipe-org | [mcp-odoo](https://github.com/erpipe-org/mcp-odoo) | — | — | Gated writes, multi-instance; hosted version at erpipe.com |
| rosenvladimirov | [odoo-claude-mcp](https://github.com/rosenvladimirov/odoo-claude-mcp) | — | — | Self-hosted, Odoo 15–19; 197+ tools, multi-tenant, Bulgarian localization |
| marcfargas | [odoo-toolbox](https://github.com/marcfargas/odoo-toolbox) | — | — | TypeScript SDK, CLI, skill modules and MCP server; CI-tested against 17 and 18 |
| infovpcs | [odoo18_mcp_project](https://github.com/infovpcs/odoo18_mcp_project) | — | — | MCP integration server for Odoo 18.0 |
| rachmataditiya | [odoo-rust-mcp](https://github.com/rachmataditiya/odoo-rust-mcp) | — | — | Written in Rust; Odoo 14–19+ via JSON-RPC and REST API |
| AlanOgic | [mcp-odoo-adv](https://github.com/AlanOgic/mcp-odoo-adv) | — | — | Enhanced server with STDIO, SSE and Streamable HTTP transports |
| pandeussilvae | [mcp-odoo-panda](https://github.com/pandeussilvae/mcp-odoo-panda) | — | — | MIT; stdio and Streamable HTTP; CRUD plus custom method calls |
| FGRibreau | [mcp-odoo](https://github.com/FGRibreau/mcp-odoo) | — | — | Odoo 19+ via the JSON-2 API |
| altinkaya-opensource | [odoo-mcp](https://github.com/altinkaya-opensource/odoo-mcp) | — | — | No external dependencies |
| hamzatrq | [odoo-forge](https://github.com/hamzatrq/odoo-forge) | — | — | Odoo 18 configuration engine; 71 tools in 16 categories |
| jjaraujoa | [Odoo-AI-Client-Agent](https://github.com/jjaraujoa/Odoo-AI-Client-Agent) | — | — | Copilot, MCP server and workflow engine for Odoo 19 via native JSON-2; no custom addons |
| parth-unjiya | [odoo-mcp-gateway](https://github.com/parth-unjiya/odoo-mcp-gateway) | — | — | Security-first, Odoo 17–19; YAML-driven security, no Odoo-side code; 27 tools, 5 resources, 7 prompts |
| parth-unjiya | [openclaw-odoo](https://github.com/parth-unjiya/openclaw-odoo) | — | — | Odoo 19 connector: CLI, MCP server (43 tools) and OpenClaw skill; no server-side modules |
| twtrubiks | [odoo19-mcp-server](https://github.com/twtrubiks/odoo19-mcp-server) | — | — | Odoo 19 via JSON-2 API, built with FastMCP |
| bmya | [claude-odoo-api](https://github.com/bmya/claude-odoo-api) | — | — | Odoo 19 JSON-2 API; multi-company, image processing, retries and connection pooling |
| techniondigitalsolutions | [odoo-mcp](https://github.com/techniondigitalsolutions/odoo-mcp) | — | — | Safety-first, Odoo 16–19; controlled changes, audit journal, rollback |
| solutionsunity | [odoo-surface-mcp](https://github.com/solutionsunity/odoo-surface-mcp) | — | — | Gives agents the same access as a regular Odoo user |
| oconsole | [odoo-mcp-server](https://github.com/oconsole/odoo-mcp-server) | — | — | General-purpose server for any AI agent |
| elewa-git | [odoo-mcp-server](https://github.com/elewa-git/odoo-mcp-server) | — | — | Open-source server for Claude |
| mah007 | [odooMCP](https://github.com/mah007/odooMCP) | — | — | Compatible with n8n and other agent frameworks |
| avanserv | [odouche](https://github.com/avanserv/odouche) | — | — | Unofficial Odoo.sh toolkit: Python library, CLI and MCP server |
| CData | [odoo-mcp-server-by-cdata](https://github.com/CDataSoftware/odoo-mcp-server-by-cdata) | — | — | Read-only, via the CData JDBC driver |
| VatsalChauhan36 | [odoo-devkit-mcp](https://github.com/VatsalChauhan36/odoo-devkit-mcp) | — | — | Developer-oriented, Odoo 17–19; token-efficient structured access to code and models |
| havmedia | [odoo-boost](https://github.com/havmedia/odoo-boost) | — | — | Developer-oriented; coding agents introspect a running Odoo instance |
| Viindoo | [odoo-semantic-server](https://github.com/Viindoo/odoo-semantic-server) | — | — | Code intelligence: semantic graph of Odoo code exposed via MCP; client plugin in [odoo-mcp-client](https://github.com/Viindoo/odoo-mcp-client) |
| dannyg-sys | [odoo-mcp-server](https://github.com/dannyg-sys/odoo-mcp-server) | — | — | Developer-oriented; 19 tools for server control, modules, tests and databases |
| krishnakantjoshi | [odoo-osi-mcp](https://github.com/krishnakantjoshi/odoo-osi-mcp) | — | — | Unofficial; search and compare open-source Odoo/OCA modules before writing custom code |

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
| woodwosj | [OdooDevMCP](https://github.com/woodwosj/OdooDevMCP) | — | — | Odoo 19 module; gives agents terminal, database, filesystem and ORM access |
| cicdoo | [grokoo](https://github.com/cicdoo/grokoo) | — | — | In-Odoo assistant using the xAI Grok CLI; permission-aware ORM tools and read-only SQL over a sandboxed MCP bridge |
| Brain Grain | — | [safe_mcp_connector (19.0)](https://apps.odoo.com/apps/modules/19.0/safe_mcp_connector) | — | Commercial; every create/edit returns a before→after preview with single-use confirm; customer emails held until a person approves in Odoo; deletes off by default; per-user OAuth (user's own access rights); audit log; lives at `/safe_mcp` so it coexists with other `/mcp` addons; Claude desktop/web/mobile, Claude Code, Cursor |

---

## Hosted / Managed MCP Services

Hosted by the vendor: users connect their AI client to a public MCP URL and nothing runs inside Odoo or next to the client.

| Vendor / Author | GitHub | Odoo App Store | Human Tested | Description |
|---|---|---|---|---|
| Tuqui | — | [tuqui_mcp (16.0–19.0)](https://apps.odoo.com/apps/modules/19.0/tuqui_mcp) | — | Commercial, hosted MCP at tuqui.com; nothing to install in Odoo (the app is an optional OAuth bridge), so it works on Odoo Online, Odoo.sh and on-prem, Odoo 16 to 20, Community & Enterprise; per-user OAuth, read-only by default; works in Claude, ChatGPT and its own web/mobile chat; free plan |

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
- [Case study: Odoo 19 Community, an MCP server and Claude Code replace Holded for a quarter close (Agents Finance)](https://agentsfinance.io/entries/case-odoo-community-claude-code-mcp-replaces-holded-quarter-close-2026/)
