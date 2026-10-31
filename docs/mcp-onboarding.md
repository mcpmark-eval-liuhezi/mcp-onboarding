# Model Context Protocol (MCP) Onboarding Briefing

**Audience:** Three new engineers joining the team this week.
**Purpose:** A short, self-contained briefing covering what MCP is, where it stands today, further reading, and open questions before the team briefing on Monday.

---

## 1. Short Overview

The Model Context Protocol (MCP) is an open protocol, announced by Anthropic on 25 November 2024, that standardizes how AI applications (hosts) connect to external data sources and tools (servers) through a client. Messages between hosts, clients, and servers use JSON-RPC 2.0. Servers expose capabilities such as Resources, Prompts and Tools; clients can request Elicitation (server-initiated requests from users, including multi-round trips and inter-client agreement on end negotiations) and use the Registry to discover available servers.

Governance note: as of 9 December 2025, the MCP donation went to the AGENTIC AI foundation (AAIF), a Linux Foundation directed fund co-founded with OpenAI and Block; the project code, specs, SDKs and registry now live under the AAIF umbrella.

Real-world adoption includes MCP clients in OpenAI's Agents SDK (2025) and GCP's 2026 build, MCP integration in Google DeepMind's Gemini and Google Cloud connectors, MCP support in Microsoft's Azure AI Foundry and Copilot Studio (with a public MCP Test channel), and Cloudflare's MCP compatibility event plus fixes to the MCP registry. Security considerations include resource limits, compliance monitoring, key management, and personal-data privacy controls; the project also maintains an open public MCP registry and published API best-practices and threat-model documentation. The latest spec version is 2026-07-28, released 28 July 2026.

## 2. Further Reading

The Wikipedia lookup for "Model Context Protocol" returned no article data — searches came back empty and every article-content tool timed out or returned nothing — so the following adjacent topics are listed from general knowledge rather than the article's link list:

- **JSON-RPC 2.0** — The wire format MCP uses for messages between hosts, clients, and servers.
- **Anthropic** — The company that created and initially open-sourced MCP.
- **AGENTIC AI foundation (AAIF)** — The Linux Foundation directed fund that now hosts the MCP project, specs, SDKs and registry.
- **OpenAI Agents SDK** — Organizations shipping MCP clients into their agent toolkits.
- **Google Gemini / Google Cloud** — Projects embedding or exposing MCP-type connectors.
- **Microsoft Azure AI Foundry / Copilot Studio** — Microsoft's MCP support and public MCP Test channel.
- **Cloudflare MCP compatibility event** — Vendor event and registry fixes; useful reliability/security lessons.

## 3. Team Scope Decisions from Slack

No such discussion was found. Workspace-wide Slack search for "Model Context Protocol", "onboarding briefing", "briefing", "scope skip", and "cover skip what to cover" returned only automated weekly-signal digest posts and a single "FIX THIS" correction message in #所有-mcp-atlas from linyue ma (malinyue199); that thread has no replies. There is no recorded team-wide discussion that agreed what this briefing should cover and what to skip, so no scope decisions can be folded in — this section stands as "none found" rather than inventing decisions.

## 4. Current Release Status

No releases have been published on `mcpmark-eval-liuhezi/mcp-onboarding` — the latest-release query returned 404 Not Found. The repository exists (created 2026-10-20, default branch `main`) but has no published version; this briefing is the first content landing in it. Once merged, branch `add-mcp-onboarding-briefing` becomes the source.

## 5. Open Questions

- Which canonical spec version should the briefing cite as the working baseline (2026-07-28, or later)?
- How deep should the security section go (resource limits, compliance monitoring, key management, personal-data privacy) versus a pointer to the official threat-model docs?
- Which SDK should the new engineers practice with for hands-on work (Python, TypeScript, or another)?
- What internal MCP Test channel access will be needed, and who should it be opened for?
- Who is the internal point of contact for MCP questions (the Slack discussion noted linyue ma maintains the official channels)?

---

*Briefing generated as part of the MCP onboarding effort. Wikipedia background was unavailable at retrieval time; further reading items above are from general knowledge and should be verified against primary sources.*
