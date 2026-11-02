# Model Context Protocol (MCP) — Onboarding Briefing

**Audience:** Three new engineers starting this week.
**Purpose:** A single, lasting reference for the team's MCP onboarding briefing — landed as a pull request rather than stored in anyone's downloads.

---

## 1. Short Overview

The Model Context Protocol (MCP) is an open standard and open-source framework introduced by Anthropic in November 2024 to standardize the way artificial intelligence (AI) systems like large language models (LLMs) integrate and share data with external tools, systems, and data sources. MCP provides a standardized interface for reading files, executing functions, and handling contextual prompts.

Key points for onboarding:

- **Messaging:** MCP uses JSON-RPC 2.0 messages exchanged between hosts, clients, and servers.
- **Server features:** expose Resources, Prompts, and Tools.
- **Client features:** include Elicitation (server-initiated requests from users, including multi-round-trip requests on the latest spec), Agreements between clients on end negotiations, and a Registry to discover available servers.
- **Governance:** In December 2025, Anthropic donated MCP to the Agentic AI Foundation (AAIF), a fund under the Linux Foundation.
- **Adoption:** Following its announcement, the protocol was adopted by major AI providers, including OpenAI and Google DeepMind.
- **Security & extensions:** MCP maintenance has published API best practices and a threat model, plus an open public MCP registry (open since July 2025); key security considerations include resource limits, compliance monitoring, key management, and data privacy controls around personal data. Extensions include tasks, MCP Apps, and AI GitHub skills.

---

## 2. Further Reading

Wikipedia article: [Model Context Protocol](https://en.wikipedia.org/wiki/Model_Context_Protocol). The article's link list was retrieved successfully; the most relevant linked entries with one-line descriptions:

- **JSON-RPC** — JSON-based wire protocol for remote procedure calls; MCP messages are built on JSON-RPC 2.0 (transport-independent; no built-in authentication).
- **Anthropic** — The American AI public benefit corporation behind Claude and the creator of MCP; founded January 2021 by former OpenAI members.
- **Large language model** — The model class (typically transformer neural networks trained on vast text) that MCP helps integrate with external tools and data.
- **Language Server Protocol** — Open, JSON-RPC-based protocol for editor/IDE–language-server communication; a useful conceptual sibling to MCP.
- **OAuth 2.0** — Open standard for access delegation; commonly used for secure delegated access in MCP server deployments.
- **Prompt injection** — Cybersecurity exploit targeting LLMs; relevant security consideration when exposing MCP tools to untrusted inputs.
- **OpenAI** — Adopted MCP; its Agents SDK shipped MCP clients in 2025.
- **GitHub** — Host for MCP specs, SDKs, and the public MCP registry.
- **Agent2Agent (A2A)** — Open protocol for AI agents to discover one another and coordinate tasks across vendors/frameworks.

---

## 3. Team Scope Decisions (from Slack)

No such discussion was found. Slack searches for "Model Context Protocol", "onboarding briefing", "briefing", "MCP", and "scope" returned only automated weekly-signal digest posts and a single "FIX THIS" correction message from one user (linyue ma / malinyue199) in #所有-mcp-atlas — none of these record a scoping decision about what the briefing should cover or skip. The thread under that message contains only the message itself. Per instructions, this is recorded as "none found" rather than inventing decisions.

---

## 4. Current Release Status

No releases have been published on `mcpmark-eval-liuhezi/mcp-onboarding`. The latest-release query returned 404 and the full releases list is empty — this is the first content landing in the repo. The briefing therefore states no current version number; the canonical spec version should be confirmed before the briefing is presented.

---

## 5. Open Questions

- What is the canonical current MCP spec version to cite?
- How deep should the security section go for onboarding?
- Which SDK should new engineers practice with (Python, TypeScript, or another)?
- Is access to an internal MCP Test channel available for hands-on work?
- Who is the internal point of contact for MCP-related questions?

---

*Briefing landed as a pull request into `main` of `mcpmark-eval-liuhezi/mcp-onboarding`. Wikipedia research returned article and link data; Slack returned no scoping discussion; no pending draft PR review was found on authored PRs; notification clearance could not be performed (403 from the personal access token).*
