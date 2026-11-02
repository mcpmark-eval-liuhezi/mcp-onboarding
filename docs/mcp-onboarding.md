# Model Context Protocol (MCP) — Onboarding Briefing

**Audience:** Three new engineers starting this week.
**Purpose:** A single, lasting reference for the team's MCP onboarding briefing — landing here as a pull request rather than in anyone's downloads.

---

## 1. Short Overview

The Model Context Protocol (MCP) is an open standard and open-source framework introduced by Anthropic in November 2024 to standardize the way AI systems such as large language models integrate and share data with external tools, systems, and data sources. It provides a standardized interface for reading files, executing functions, and handling contextual prompts. Following its announcement, the protocol was adopted by major AI providers including OpenAI and Google DeepMind; in December 2025, Anthropic donated MCP to the Agentic AI Foundation (AAIF), a fund under the Linux Foundation.

Key architectural points for onboarding:

- **Messaging:** Client and server communicate using JSON-RPC 2.0 messages.
- **Actor model:** MCP distinguishes hosts (typically an AI agent interacting with an LLM), clients (one per server, created by the host), and servers (which expose tools, resources, and prompts).
- **Server features:** Tools (database access, calculators, code/repository access), Resources (e.g., an FAQ document), and Prompts.
- **Client features:** Elicitation (server-initiated requests from users, including multi-round-trip requests on the latest spec), Agreements between clients on end negotiations, and a Registry to discover available servers.
- **SDKs:** Released in Python, TypeScript, C#, and Java, plus example server implementations.
- **Governance:** Since December 9, 2025, the protocol lives under the AAIF (Linux Foundation directed fund co-founded by Anthropic, Block, and OpenAI).
- **Adoption:** OpenAI adopted MCP in March 2025 (ChatGPT desktop app; MCP support in ChatGPT apps from September 2025); MCP can integrate with Microsoft Semantic Kernel and Azure OpenAI; servers can deploy to Cloudflare. By mid-2026, more than 10,000 MCP servers were reported in production with SDKs downloaded over 97 million times per month.
- **2026-07-28 revision:** A major revision removed protocol-level session tracking (MCP becomes stateless at the protocol layer; version/client identity/capabilities carried in a `_meta` parameter per request), deprecated sampling and roots (functional for a minimum of twelve months), and moved Tasks into optional extensions. Not all changes are backward compatible.
- **Security:** Tool poisoning attacks (hidden malicious instructions in tool descriptions — a form of prompt injection), CVE-2025-6514 (critical, CVSS 9.6, in mcp-remote, fixed in 0.1.16), and CVE-2025-49596 (MCP Inspector, no authentication by default). The spec now requires OAuth 2.1 security best practices and describes confused-deputy risks in proxy servers; token passthrough is forbidden. The U.S. NSA reported in May 2026 that MCP's rapid proliferation has outpaced its security model.
- **MCP Apps:** An official extension (built on mcp-ui) standardizing delivery of interactive UIs — dashboards, forms, data visualizations — from MCP servers to host applications such as Claude and ChatGPT (base MCP spec is restricted to text and structured data).

## 2. Further Reading (from the article's link list)

The Wikipedia article "Model Context Protocol" was retrieved successfully (summary, sections, and link list available). Most relevant linked entries with one-line descriptions:

- **JSON-RPC** — A JSON-based wire protocol for remote procedure calls; MCP messages are JSON-RPC 2.0.
- **Language Server Protocol** — An open, JSON-RPC-based protocol between editors/IDEs and language servers; MCP reuses its message-flow ideas.
- **OAuth 2.0** — The authorization framework whose best practices MCP now requires for secure deployments.
- **Prompt injection** — The attack vector (including tool poisoning, where malicious instructions are hidden in tool descriptions the model can read) relevant to MCP security.
- **Confused deputy** — A security hazard in MCP proxy servers where a malicious server can misuse the host's authority; token passthrough is forbidden.
- **Agentic AI Foundation** — The Linux Foundation directed fund (co-founded with OpenAI and Block, since December 2025) that stewards MCP.
- **Linux Foundation** — The nonprofit umbrella under which AAIF operates.
- **Anthropic** — The company that created and initially open-sourced MCP (Nov 25, 2024).
- **OpenAI** — Adopted MCP in March 2025; MCP clients in the Agents SDK; ChatGPT apps support from September 2025.
- **Google DeepMind** — Embedding MCP into Gemini; Google Cloud exposes data via MCP-type connectors.
- **Claude (language model)** — Anthropic's LLM series used in AI-assisted software development (Claude Code, Claude Cowork).
- **Agent2Agent (A2A)** — Open protocol for communication between AI agents; complementary to MCP.
- **MCP Apps** — No standalone Wikipedia article; official extension for interactive UI delivery from MCP servers.
- **OpenAPI Specification** — Often likened to MCP as a spec describing interfaces/apis.
- **Software agent / Intelligent agent** — General context for the agent concept MCP hosts are part of.

## 3. Team Scope Decisions (from Slack)

No scoping discussion was found. Slack searches for "Model Context Protocol", "onboarding", "briefing", "scope", and "skip" returned only automated weekly-signal digest posts and a single "FIX THIS" correction message from one user (linyue ma / malinyue199, U0BB6DQHKBL) in #所有-mcp-atlas (C0BBA2QSZ4L). The thread under that message contains only the message itself (no replies). None of these record a decision about what the briefing should cover or skip. Per instructions, this is recorded as "none found" rather than inventing decisions.

## 4. Current Release Status

No releases have been published on `mcpmark-eval-liuhezi/mcp-onboarding`. The latest-release query returned 404 and the releases list is empty — this is the first content landing in the repo. The briefing therefore states no published version number; the canonical spec version (2026-07-28 revision) should be confirmed before the briefing is presented.

## 5. Open Questions

- What is the canonical current MCP spec version to cite (2026-07-28 revision)?
- How deep should the security section go for onboarding (tool poisoning, CVEs, OAuth 2.1, confused deputy)?
- Which SDK should new engineers practice with (Python, TypeScript, C#, or Java)?
- Is access to an internal MCP Test channel available for hands-on work?
- Who is the internal point of contact for MCP-related questions?

---

*Briefing landed as a pull request into `main` of `mcpmark-eval-liuhezi/mcp-onboarding` (PR #9, branch `mcp-onboarding-briefing`, file `docs/mcp-onboarding.md`). Wikipedia: article retrieved (summary, sections, link list); further-reading one-liners gathered for JSON-RPC, LSP, OAuth 2.0, prompt injection, confused deputy, AAIF, Linux Foundation, Anthropic, OpenAI, Google DeepMind, Claude, Agent2Agent, MCP Apps, OpenAPI, and agent concepts. Slack: no scoping discussion found. No pending draft PR review was found on authored PRs. Notification clearance could not be performed (GitHub notifications endpoint returned 403 for the personal access token).*
