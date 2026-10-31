# Model Context Protocol (MCP) — Onboarding Briefing

Prepared for three new engineers joining the team. This briefing lands the MCP onboarding
background, further reading, team scope decisions, release status, and open questions in one
file so it does not live in someone's downloads.

## 1. Short Overview

The Model Context Protocol (MCP) is an open protocol, announced by Anthropic on November 25,
2024, that standardizes how AI applications (hosts and clients) connect to external data
sources and tools (servers). Messages between hosts, clients, and servers use JSON-RPC 2.0.
Servers expose features such as Resources, Prompts, and Tools; clients can initiate actions
such as Elicitation (server-initiated requests from users, including multi-round-trip
negotiation on the latest spec). Governance moved to the AGENTIC AI foundation (AAIF), a
Linux Foundation directed fund co-founded with OpenAI and Block, as of December 9, 2025; the
code, specs, SDKs, and registry now live under that umbrella. Latest spec version:
2026-07-28, released July 28, 2026.

## 2. Further Reading

Wikipedia lookup note: the Wikipedia search for "Model Context Protocol" returned no article
matches, and the article summary/links lookups timed out without returning data. The links
below are the most relevant adjacent topics for onboarding, described in one line each;
they are NOT from the article's link list (that data was unavailable).

- **JSON-RPC 2.0** — the message format MCP uses for host-client-server communication.
- **Anthropic** — the company that introduced MCP as an open protocol in November 2024.
- **AGENTIC AI foundation (AAIF)** — the Linux Foundation directed fund that now governs MCP.
- **OpenAI Agents SDK** — OpenAI's SDK that ships MCP client support (2025).
- **Google Gemini / Google Cloud** — DeepMind embedding MCP; Cloud exposing data via MCP connectors.
- **Microsoft Azure AI Foundry / Copilot Studio** — MCP support plus a public MCP Test channel.
- **Cloudflare** — ran an MCP compatibility event and fixed registry security/reliability bugs.

## 3. Team Scope Decisions (from Slack)

No such discussion was found. Slack searches for "Model Context Protocol", "briefing onboarding",
and "scope skip team discussion" returned only automated weekly digest posts from a single
poster (linyue ma / malinyue199) in #所有-mcp-atlas — these are digest/circular-refresh posts,
not a team discussion deciding what the briefing should cover and what to skip. No scope
decisions to fold in; this briefing therefore covers the neutral technical overview above and
leaves scope choices as open questions.

## 4. Current Release Status

No releases have been published on `mcpmark-eval-liuhezi/mcp-onboarding` — the latest-release
query returned 404 Not Found. This is the first content landing in the repo; the briefing
itself is the initial content release for the team.

## 5. Open Questions

- Canonical spec version to target for hands-on practice (2026-07-28 latest per current docs).
- Security depth: resource limits, compliance monitoring, key management, data privacy.
- Which SDK to use for hands-on practice (official SDKs under the AAIF umbrella).
- Internal MCP Test channel access for the team.
- Internal point of contact for MCP questions (linyue ma noted as the best internal point).
