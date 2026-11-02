# MCP Onboarding Briefing

Model Context Protocol (MCP) onboarding document for new engineers starting this week.

## 1. Short Overview

The Model Context Protocol (MCP) is an open standard and open-source framework introduced by Anthropic in November 2024 to standardize the way AI systems like large language models (LLMs) integrate and share data with external tools, systems, and data sources. It provides a standardized interface for reading files, executing functions, and handling contextual prompts. Following its announcement, the protocol was adopted by major AI providers, including OpenAI and Google DeepMind. In December 2025, Anthropic donated MCP to the Agentic AI Foundation (AAIF), a fund under the Linux Foundation.

Key points:
- **Messaging:** Client and server communicate using JSON-RPC 2.0 messages.
- **Architecture:** Distinguishes MCP hosts (typically an AI agent interacting with an LLM), MCP clients (one per server, created by the host), and MCP servers (local or remote) that provide tools and resources.
- **Server features:** Tools (e.g., database access, calculators, code/repository access), Resources (e.g., a document such as an FAQ), and Prompts; client features include Elicitation (server-initiated requests) and a Registry to discover servers.
- **SDKs:** Officially available in Python, TypeScript, C#, and Java, plus example MCP server implementations.
- **2026-07-28 revision:** A major revision finalized on July 28, 2026, described as the most substantial change since authorization was added. It makes MCP stateless at the protocol layer (version, client identity, and capabilities carried in a `_meta` parameter with each request), deprecates sampling and roots (functional for a minimum of twelve months), and moves Tasks for long-running operations into optional extensions. Not all changes are backward compatible.
- **Security:** Subject to security vulnerabilities including tool poisoning attacks (malicious instructions hidden in MCP tool descriptions), CVE-2025-6514 (critical flaw in mcp-remote, CVSS 9.6), and CVE-2025-49596 (MCP Inspector). The specification now requires implementations to follow OAuth 2.1 security best practices.
- **Adoption:** Used in AI-assisted software development tools; IDEs, coding platforms such as Replit, and code intelligence tools like Sourcegraph have adopted MCP. By mid-2026, more than 10,000 MCP servers had reportedly been deployed in production, with SDKs downloaded over 97 million times per month.

## 2. Further Reading

One-line descriptions for adjacent topics linked from the Wikipedia article on the Model Context Protocol:

- **JSON-RPC** — JSON-based wire protocol for remote procedure calls; transport-independent (HTTP, TCP, file descriptor I/O) and defines notifications and asynchronous answers; MCP uses JSON-RPC 2.0.
- **Language Server Protocol (LSP)** — Open, JSON-RPC-based protocol between editors/IDEs and language servers providing code completion, syntax highlighting, warnings/errors, and refactoring; MCP reuses LSP's message-flow ideas.
- **OAuth 2.0** — Open standard for access delegation, used to issue access tokens to third-party clients with the resource owner's approval; MCP security requirements now require OAuth 2.1 best practices.
- **Anthropic** — American AI public benefit corporation headquartered in San Francisco; creator of the Claude LLM family and MCP.
- **OpenAI** — American AI PBC known for the GPT series; adopted MCP in March 2025 and ships MCP clients in its Agents SDK.
- **Claude (language model)** — Series of LLMs developed by Anthropic (Haiku/Sonnet/Opus/Mythos/Fable tiers), used in AI-assisted software development via Claude Code and Claude Cowork.
- **Linux Foundation** — Nonprofit formed in 2007 to support Linux and open-source software; now an umbrella for AI projects including the AAIF under which MCP governance sits.
- **Agentic AI Foundation (AAIF)** — Linux Foundation directed fund co-founded by Anthropic, Block and OpenAI (from December 2025); MCP code, specs, SDKs, and registry live under this umbrella.
- **Agent2Agent (A2A)** — Open protocol defining how AI agents communicate across different systems, allowing discovery, message exchange, and task coordination.
- **OpenAPI Specification** — Machine-readable interface definition language for describing, producing, consuming, and visualizing web services; overseen by the Linux Foundation's OpenAPI Initiative.
- **LangChain** — Software framework helping integrate LLMs into applications, with use cases including document analysis, summarization, chatbots, and code analysis.
- **Prompt injection** — Cybersecurity exploit where innocuous-looking inputs are designed to cause unintended behavior in LLMs; tool poisoning (malicious instructions in tool descriptions) is a form of prompt injection relevant to MCP.
- **Retrieval-augmented generation (RAG)** — Technique enabling LLMs to retrieve and incorporate new information from external data sources before generating responses; reduces hallucinations and supports domain-specific/updated answers.
- **API** — Application programming interface; MCP provides a standardized API for tools, resources, and prompts.
- **Software development kits** — Official MCP SDKs in Python, TypeScript, C#, and Java, with example server implementations.
- **Integrated development environment** — IDEs and coding platforms (e.g., Replit, Sourcegraph) have adopted MCP to give AI coding assistants real-time access to project context.

## 3. Team Scope Decisions (from Slack)

Searches of the Slack workspace (channel #所有-mcp-atlas, C0BBA2QSZ4L) for "Model Context Protocol", "briefing", "scope", "onboarding", and "skip" found no team-wide discussion agreeing what the briefing should cover and what to skip. The visible history contains automated weekly signal digests and a single "FIX THIS" correction message (linyue ma, U0BB6DQHKBL, workspace admin/owner) that re-posts a cleaned MCP project-status briefing. No explicit scope decisions (e.g., "cover X, skip Y") were found in Slack; this briefing therefore follows a standard onboarding structure (overview, further reading, release status, open questions) and the scope decisions section records that none were found.

## 4. Current Release Status

No releases have been published on the repository `mcpmark-eval-liuhezi/mcp-onboarding` (GET /releases/latest returned 404 Not Found and the releases list is empty). This is the first content landing in the repo; the briefing lands as `docs/mcp-onboarding.md` on branch `add-mcp-onboarding-briefing-final3` targeting the default branch `main`. Canonical spec version per Wikipedia: 2026-07-28.

## 5. Open Questions

- Which canonical spec version should new engineers target for hands-on practice (2026-07-28 vs. newer)?
- How deep should the security section go (tool poisoning, OAuth 2.1, mcp-remote CVE-2025-6514, Inspector CVE-2025-49596)?
- Which SDK (Python/TypeScript/C#/Java) to use for hands-on practice?
- Internal MCP Test channel access and internal point of contact (linyue ma maintains the official channels)?
- Whether to include a validation chart (tools to validate the implementation) and a weaknesses summary?
