# Model Context Protocol (MCP) — Onboarding Briefing

**Audience:** Three new engineers starting this week.
**Purpose:** A single, lasting reference for the team's MCP onboarding briefing — landing here as a pull request rather than in anyone's downloads.

---

## 1. Short Overview

The Model Context Protocol (MCP) is an open protocol, announced November 25, 2024, that standardizes how AI applications (hosts) connect to external data sources and tools (servers) through a common client layer. Key points for onboarding:

- **Messaging:** MCP uses JSON-RPC 2.0 messages exchanged between hosts, clients, and servers.
- **Server features:** expose Resources, Prompts, and Tools.
- **Client features:** include Elicitation (server-initiated requests from users, including multi-round-trip requests on the latest spec), Agreements between clients on end negotiations, and a Registry to discover available servers.
- **Governance:** Since December 9, 2025, the protocol donation went to the AGENTIC AI foundation (AAIF), a Linux Foundation directed fund co-founded with OpenAI and Block; code, specs, SDKs, and the registry all live under the AAIF umbrella.
- **Real-world adoption:** OpenAI shipped MCP clients into its Agents SDK in 2025; Google DeepMind is embedding MCP into Gemini; Google Cloud exposes data via MCP-type connectors; Microsoft puts MCP support in Azure AI Foundry and Copilot Studio (with a public MCP Test channel); Cloudflare ran an MCP compatibility event and fixed multiple security/reliability bugs in the MCP registry.
- **Security & extensions:** MCP maintenance published API best practices and threat model docs plus an open public MCP registry (open since July 2025); key security considerations include resource limits, compliance monitoring, key management, and data privacy controls around personal data. Extensions include tasks, MCP Apps, and AI GitHub skills.

## 2. Further Reading

Wikipedia lookup note: searches for "Model Context Protocol" and "model context protocol MCP Anthropic" both returned **no results**, and article/link fetches timed out, so the article's link list could not be retrieved. The entries below are therefore **not** from the article's link list — they are adjacent topics with one-line descriptions for orienting new engineers.

- **JSON-RPC 2.0** — The lightweight remote-procedure-call protocol MCP messages are built on; understanding its request/response and error semantics makes MCP clients much easier to read.
- **Anthropic** — The company that created and initially open-sourced MCP; useful context for the protocol's origins and early ecosystem.
- **AGENTIC AI foundation (AAIF)** — The Linux Foundation directed fund (co-founded with OpenAI and Block, since December 2025) that now stewards MCP code, specs, SDKs, and the registry.
- **OpenAI Agents SDK** — The OpenAI framework that shipped MCP clients in 2025; a concrete place to see MCP in production.
- **Google Gemini / Google Cloud** — Google DeepMind is embedding MCP into Gemini; Google Cloud exposes data via MCP-type connectors.
- **Microsoft Azure AI Foundry / Copilot Studio** — Microsoft's MCP-support surface, including a public MCP Test channel for hands-on experimentation.
- **Cloudflare** — Ran an MCP compatibility event and fixed multiple security/reliability bugs in the MCP registry; registry docs are also published by Microsoft.

## 3. Team Scope Decisions (from Slack)

No such discussion was found. Slack searches for "Model Context Protocol", "onboarding", "briefing", "scope", and "skip" returned only automated weekly-signal digest posts and a single "FIX THIS" correction message from one user (linyue ma / malinyue199) in #所有-mcp-atlas — none of these record a scoping decision about what the briefing should cover or skip. The thread under the "FIX THIS" message contains only that one message itself. Per instructions, this is recorded as "none found" rather than inventing decisions.

## 4. Current Release Status

No releases have been published on `mcpmark-eval-liuhezi/mcp-onboarding`. The latest-release query returned 404 and the full releases list is empty — this is the first content landing in the repo. The briefing therefore states no current version number; the canonical spec version should be confirmed before the briefing is presented.

## 5. Open Questions

- What is the canonical current MCP spec version to cite?
- How deep should the security section go for onboarding?
- Which SDK should new engineers practice with (Python, TypeScript, or another)?
- Is access to an internal MCP Test channel available for hands-on work?
- Who is the internal point of contact for MCP-related questions?

---

*Briefing landed as a pull request into `main` of `mcpmark-eval-liuhezi/mcp-onboarding`. Wikipedia research returned no article or link data; Slack returned no scoping discussion; no pending draft PR review was found on authored PRs; notification clearance could not be performed (403 from the personal access token).*
