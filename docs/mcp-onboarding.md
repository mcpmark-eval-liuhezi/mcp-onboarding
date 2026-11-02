# Model Context Protocol (MCP) — Onboarding Briefing

**Audience:** Three new engineers starting this week.
**Purpose:** A single, lasting reference for the team's MCP onboarding briefing — landed as a pull request rather than stored in anyone's downloads.

---

## 1. Short Overview

The Model Context Protocol (MCP) is an open standard and open-source framework introduced by Anthropic in November 2024 to standardize the way AI systems such as large language models integrate and share data with external tools, systems, and data sources. It provides a standardized interface for reading files, executing functions, and handling contextual prompts. Following its announcement, the protocol was adopted by major AI providers including OpenAI and Google DeepMind. In December 2025, Anthropic donated MCP to the Agentic AI Foundation (AAIF), a directed fund under the Linux Foundation.

Key points for onboarding:

- **Messaging:** MCP communicates using JSON-RPC 2.0 messages between hosts, clients, and servers.
- **Actor model:** An MCP host (typically an AI agent/LLM application) creates dedicated MCP clients for each MCP server it uses; clients and hosts usually run on the same machine while servers may be local or remote.
- **Server features:** Each server provides one or more tools or resources. Tools might include database access, calculators, or access to code/repositories; a resource might be a document such as an FAQ. The client asks its server for a list of tools and resources; the server replies with natural-language descriptions of capabilities and expected call formats. The LLM uses this to decide whether to call a tool; the host instructs the relevant client to call it, and results are injected into the LLM conversation.
- **SDKs:** Released with SDKs in Python, TypeScript, C#, and Java, plus example MCP server implementations.
- **Adoption:** Used in AI-assisted software development tools; IDEs, coding platforms such as Replit, and code intelligence tools like Sourcegraph have adopted MCP. MCP Apps is an official extension (built on mcp-ui) that standardizes delivery of interactive UIs from servers to host applications.
- **Governance:** Since December 2025, stewarded by the AAIF (Linux Foundation directed fund co-founded by OpenAI and Block).
- **Security:** The spec requires OAuth 2.1 security best practices; guidance describes "confused deputy" risks in proxy servers and forbids token passthrough. Notable vulnerabilities include CVE-2025-6514 (mcp-remote, CVSS 9.6) and CVE-2025-49596 (MCP Inspector). Tool poisoning attacks (hidden malicious instructions in tool descriptions) are also a risk.
- **Recent revision (2026-07-28):** A major revision made MCP stateless at the protocol layer (session tracking removed; version/client identity/capabilities carried in a `_meta` parameter per request), deprecated sampling and roots (functional for at least 12 months), and moved Tasks into optional extensions. Not all changes are backward compatible.

## 2. Further Reading

Wikipedia lookup note: the Wikipedia search API returned no results for "Model Context Protocol" and "Model Context Protocol MCP Anthropic", but the article itself (`Model Context Protocol`) was retrieved successfully via direct summary/sections/links calls, and its link list is very large. Below are one-line descriptions for the most relevant linked entries for onboarding:

- **JSON-RPC** — JSON-based wire protocol for remote procedure calls; MCP messages are JSON-RPC 2.0.
- **Language Server Protocol** — Open, JSON-RPC-based protocol for source-code editors/integrated development; MCP reuses its message-flow ideas.
- **OAuth 2.0** — Open standard for delegated authorization; MCP security guidance requires OAuth 2.1 best practices.
- **Anthropic** — The company that created and initially open-sourced MCP; context for origins and early ecosystem.
- **OpenAI** — AI company that adopted MCP (March 2025) and added MCP support to ChatGPT apps (Sept 2025); also co-founder of AAIF.
- **Claude (language model)** — Anthropic's LLM family; MCP was built to give such models structured access to tools and data.
- **Linux Foundation** — Nonprofit formed in 2007 to support Linux and open-source development; AAIF is a directed fund under it.
- **Agentic AI Foundation** — The Linux Foundation directed fund (co-founded with OpenAI and Block, since Dec 2025) that now stewards MCP code, specs, SDKs, and the registry.
- **Agent2Agent** — Open protocol for communication between AI agents (complementary to MCP).
- **OpenAPI Specification** — Specification for describing REST APIs; often compared to MCP (MCP is likened to OpenAPI as a similar spec describing interfaces).
- **LangChain** — Framework for integrating LLMs into applications; relevant for building MCP-based tooling.
- **Prompt injection** — Cybersecurity attack vector; relevant to MCP security (e.g., tool poisoning attacks hide malicious instructions in tool descriptions).
- **Software agent / AI agent / Intelligent agent** — Programs acting for a user; MCP hosts are typically AI agents.
- **Application programming interface** — Connection between programs; MCP standardizes APIs for tools and data.
- **Retrieval-augmented generation** — Technique combining LLM generation with retrieval; related to how MCP injects retrieved tool results into the LLM conversation.

## 3. Team Scope Decisions (from Slack)

No such discussion was found. Slack searches for "Model Context Protocol", "briefing onboarding MCP", "scope skip onboarding", and "site:C0BBA2QSZ4L MCP" returned only automated weekly-signal digest posts and a single "FIX THIS" correction message from one user (linyue ma / malinyue199, U0BB6DQHKBL) in #所有-mcp-atlas — none of these record a scoping decision about what the briefing should cover or skip. The thread under that message contains only that one message itself. Per instructions, this is recorded as "none found" rather than inventing decisions.

## 4. Current Release Status

No releases have been published on `mcpmark-eval-liuhezi/mcp-onboarding`. The latest-release query returned 404 and the full releases list is empty — this is the first content landing in the repo. The briefing therefore states no current version number; the canonical spec version should be confirm before the briefing is presented.

## 5. Open Questions

- What is the canonical current MCP spec version to cite?
- How deep should the security section go for onboarding (tool poisoning, confused deputy, OAuth 2.1, registry trust)?
- Which SDK should new engineers practice with (Python, TypeScript, C#, or Java)?
- Is access to an internal MCP Test channel available for hands-on work?
- Who is the internal point of contact for MCR-related questions?

---

*Briefing landed as a pull request into `main` of `mcpmark-eval-liuhezi/mcp-onboarding`. Wikipedia research returned article data (search API returned no results, but direct article retrieval succeeded); Slack returned no scoping discussion; no pending draft PR review was found on authored PRs; notification clearance could not be performed (403 from the personal access token).*
