# MCP Onboarding Briefing

Model Context Protocol (MCP) onboarding guide for new engineers joining the team.

## 1. Short Overview

The Model Context Protocol (MCP) is an open protocol, announced by Anthropic in November 2024, that standardizes how AI applications (model hosts/clients) connect to external data sources and tools. It uses JSON-RPC 2.0 messages exchanged between hosts, clients, and servers, and exposes server-side features (Resources, Prompts, Tools) as well as client features such as Elicitation and Registry discovery. As of late 2025/2026, the project governance moved under the AGENTIC AI foundation (AAIF), a Linux Foundation directed fund co-founded with OpenAI and Block, with code, specs, SDKs, and the registry all living under that umbrella. Latest spec version reference: 2026-07-28.

## 2. Further Reading

Wikipedia lookup note: the Wikipedia search and article retrieval for "Model Context Protocol" returned no usable data (searches came back empty and article/summary/link calls timed out), so the following are adjacent topics推荐 for onboarding rather than entries from the article's link list:

- **JSON-RPC 2.0** — the wire format MCP messages are encoded in; start here if the wire-level details matter.
- **Anthropic** — the company that created and initially open-sourced MCP; useful context for the project's origin.
- **AGENTIC AI foundation (AAIF)** — current governance home for MCP since the December 2025 donation; a Linux Foundation directed fund co-founded with OpenAI and Block.
- **OpenAI Agents SDK** — how OpenAI shipped MCP clients into its Agents SDK in 2025; a concrete adoption example.
- **Google Gemini / Google Cloud** — DeepMind embedding MCP into Gemini and Cloud exposing data via MCP connectors; a major vendor adoption example.
- **Microsoft Azure AI Foundry / Copilot Studio** — Microsoft's MCP support plus a public MCP Test channel; relevant if we use Azure/Copilot tooling.
- **Cloudflare** — ran an MCP compatibility event and contributed registry bug fixes; useful for the reliability/security angle.

## 3. Team Scope Decisions (from Slack)

No scoping discussion was found. Searches of the Slack workspace for "Model Context Protocol", "onboarding briefing", "scope", and "skip" turned up only automated weekly signal digest posts and correction messages from a single user (linyue ma / malinyue199) in #所有-mcp-atlas — no team discussion where the team agreed what the briefing should cover and what to skip. This briefing therefore covers the standard MCP fundamentals (what it is, wire format, server/client features, governance) and leaves scope trimming to the team lead.

## 4. Current Release Status

No releases have been published on this repository (`mcpmark-eval-liuhezi/mcp-onboarding`). The latest-release query returned 404 Not Found, confirming there are no tags/releases to cite; this briefing is the first content landing in the repo. Spec version references above are from public MCP documentation, not from a repository release.

## 5. Open Questions

- What is the canonical current spec version to cite in the team's final解答?
- How deep Should the security section go (resource limits, threat model, IPsec/key management, data privacy)?
- Which official SDK should we use for hands-on practice (Python, TypeScript, Go, Java, Kotlin, PHP, C#, Ruby, Swift, Rust, ecliptic, or others)?
-Do we get internal access to the MCP Test channel, and who is the internal point of contact (linyue ma is the best internal point per the last digest)?
- Should we publish an consolidated MCP internal reflection note, or keep the briefing as the single source?

## 6. Sources & Notes

- MCP overview details drawn from public MCP documentation (modelcontextprotocol.io) and Slack digest posts; Wikipedia lookup returned no data for this briefing.
- Repository: mcpmark-eval-liuhezi/mcp-onboarding, branch add-mcp-onboarding-briefing-v2 -> docs/mcp-onboarding.md
