# MCP Onboarding Briefing

Model Context Protocol (MCP) onboarding guide for the three new engineers joining this week.

## 1. Short Overview

The Model Context Protocol (MCP) is an open standard and open-source framework introduced by Anthropic in November 2024 to standardize the way AI systems such as large language models integrate and share data with external tools, systems, and data sources. It provides a standardized interface for reading files, executing functions, and handling contextual prompts.

- **Architecture:** MCP distinguishes between hosts (typically an AI agent that interacts with an LLM), clients (dedicated per-server clients created by the host), and servers (which expose tools, resources, and prompts). Client and host usually run on the same machine; servers may be local or remote.
- **Messaging:** Client and server communicate using JSON-RPC 2.0 messages. The client asks the server for a list of tools/resources; the server replies with natural-language descriptions and expected call formats; the LLM uses these to decide to call a tool; the server performs the action and returns results injected into the LLM conversation.
- **Features:** Server features include Tools (database access, calculators, code/repository access), Resources (e.g., an FAQ document), and Prompts. Client features include Elicitation (server-initiated requests from the user) and Registry (discovery of available servers). The Tasks feature for long-running operations was moved to optional extensions in the 2026-07-28 revision.
- **Governance:** In December 2025, Anthropic donated MCP to the Agentic AI Foundation (AAIF), a directed fund under the Linux Foundation co-founded by Anthropic, Block and OpenAI. Agent Skills, a companion open standard, was published the same month.
- **2026-07-28 revision:** A major revision finalized on July 28, 2026, described as the most substantial change since authorization was added. It makes the protocol stateless at the layer level (version, client identity and capabilities carried in a `_meta` parameter per request), deprecates sampling and roots (functional for a minimum of twelve months), and moves Tasks to optional extensions. Not all changes are backward compatible.
- **Security:** MCP has faced tool Poisoning attacks (malicious instructions hidden in tool descriptions), and vulnerabilities in mcp-remote (CVE-2025-6514, CVSS 9.6) and the MCP Inspector (CVE-2025-49596). The specification now requires OAuth 2.1 security best practices and describes "confused deputy" risks; token passthrough is forbidden.
- **Adoption:** OpenAI adopted MCP in March 2025 (including the ChatGPT desktop app and ChatGPT apps in September 2025); integration with Microsoft Semantic Kernel, Azure OpenAI and Cloudflare is documented; by mid-2026 over 10,000 MCP servers were reported in production with SDKs downloaded over 97 million times per month.

## 2. Further Reading

Selected entries from the Wikipedia article "Model Context Protocol" link list, with one-line descriptions:

- **JSON-RPC** — JSON-based wire protocol for remote procedure calls; transport-independent (HTTP, TCP, FD I/O); MCP uses JSON-RPC 2.0.
- **Language Server Protocol (LSP)** — Open, JSON-RPC-based protocol between editors/IDEs and language servers providing code completion, syntax highlighting, refactoring; MCP reuses LSP's message-flow ideas.
- **OAuth 2.0** — Open standard for access delegation; MCP specification now requires OAuth 2.1 security best practices.
- **Anthropic** — American AI PBC headquartered in San Francisco; developer of the Claude models and the MCP protocol.
- **OpenAI** — American AI PBC; adopted MCP in March 2025 and ships MCP clients in its Agents SDK.
- **Claude (language model)** — Anthropic's LLM series (Haiku/Sonnet/Opus/Fable/Mythos tiers); used in AI-assisted coding via Claude Code and Claude Cowork.
- **Linux Foundation** — Nonprofit formed in 2007 supporting Linux and open-source software; hosts the AAIF under which MCP is now governed.
- **Agentic AI Foundation** — Linux Foundation directed fund (co-founded by Anthropic, Block and OpenAI) that received the MCP donation in December 2025.
- **Agent2Agent (A2A)** — Open protocol defining how AI agents communicate across different systems, discovering one another and exchanging messages.
- **OpenAPI Specification** — Machine-readable interface definition language for describing, producing, consuming and visualizing web services; MCP has been likened to OpenAPI.
- **LangChain** — Software framework facilitating integration of LLMs into applications (document analysis, summarization, chatbots, code analysis).
- **Prompt injection** — Cybersecurity exploit where inputs designed to cause unintended model behavior; tool poisoning in MCP is a form of prompt injection.
- **Retrieval-augmented generation (RAG)** — Technique enabling LLMs to retrieve and incorporate new information from external data sources; reduces hallucinations and adds source transparency.
- **API / Application programming interface** — Connection between computers or programs; MCP provides a standardized API for tools/resources/prompts.

## 3. Team Scope Decisions (from Slack)

No formal scope-decision discussion was found in the Slack workspace. Searches for "briefing", "onboarding", "scope skip" and "MCP" returned only:
- A weekly signal digest post (counts of deploy/incident/bug/release/launch matches) in #所有-mcp-atlas.
- A "FIX THIS" correction message about a leaked-URL briefing post, with a corrected MCP project-status briefing text (what it is, governance/versions, real-world use, security/extensions, team integration possibilities).
- A team coordination brief stating the last real discussion was Dec 10–11, 2025, with "no work decisions, no open work items, no threads".

Extracted decided scope: none found. The corrected briefing text suggests team integration possibilities (block calendar for the team, create an MCP Test channel, consolidated writeup with current version number, validation tools, and a weaknesses chart) but these are suggestions, not agreed decisions. Recorded as: no agreed scope/skip list found; default to covering overview, further reading, security considerations, and hands-on SDK examples.

## 4. Current Release Status

No releases have been published on `mcpmark-eval-liuhezi/mcp-onboarding`:
- `GET /repos/mcpmark-eval-liuhezi/mcp-onboarding/reices/latest` -> 404 Not Found.
- `GET /repos/mcpmark-eval-liuhezi/mcp-onboarding/releases` -> empty list.

The repository was created on 2026-10-20 and `main` has a single README.md commit (SHA 767e338...). This PR lands the first content (docs/mcp-onboarding.md) into the repo. Canonical spec version referenced: 2026-07-28 (latest revision as of the Wikipedia article).

## 5. Open Questions

- What is the canonical spec version to target for hands-on practice (2026-07-28 vs. a newer draft)?
- How deep should the security section go (tool poisoning, confused deputy, OAuth 2.1, CVE-2025-6514/49596)?
- Which SDK to use for hands-on (Python, TypeScript, C# or Java per the article)?
- Internal MCP Test channel access for the team?
- Internal point of contact for MCP-related questions (the workspace digest suggests linyue ma / malinyue199 maintains official channels)?
- Whether to include a weaknesses chart and validation tools per the suggested integration possibilities.

## 6. Sources

- Wikipedia: "Model Context Protocol" article (summary, sections Background/Features/Adoption/Security risks and vulnerabilities/Reception/See also, and link list).
- MCP specification and registry (modelcontextprotocol.io); AAIF/Linux Foundation governance.
