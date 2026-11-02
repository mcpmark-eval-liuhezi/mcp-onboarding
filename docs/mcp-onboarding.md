# Model Context Protocol (MCP) Onboarding Briefing

## 1. Short Overview

The Model Context Protocol (MCP) is an open standard and open-source framework introduced by Anthropic in November 2024 to standardize the way AI systems such as large language models (LLMs) integrate and share data with external tools, systems, and data sources. It provides a standardized interface for reading files, executing functions, and handling contextual prompts. Following its announcement, the protocol was adopted by major AI providers including OpenAI and Google DeepMind. In December 2025, Anthropic donated MCP to the Agentic AI Foundation (AAIF), a directed fund under the Linux Foundation co-founded by Anthropic, Block and OpenAI.

Key characteristics:

- **Architecture:** MCP distinguishes between hosts (typically an AI agent that interacts with an LLM), clients (one per server, usually running on the same machine as the host), and servers (local or remote, each providing one or more tools or resources).
- **Messaging:** Client and server communicate using JSON-RPC 2.0 messages; the client asks the server for its tools/resources, the server replies with natural-language descriptions and expected call formats, and the host injects results into the LLM conversation.
- **SDKs:** Released with SDKs in Python, TypeScript, C# and Java, plus example MCP server implementations.
- **Adoption:** Used in AI-assisted software development tools; IDEs, coding platforms such as Replit, and code intelligence tools like Sourcegraph have adopted MCP. Integrated development environments (IDEs), coding platforms such as Replit, and code intelligence tools like Sourcegraph have adopted MCP to grant AI coding assistants real-time access to project context.
- **MCP Apps:** An official extension (built on mcp-ui) standardizing delivery of interactive user interfaces — dashboards, forms, data visualizations — from MCP servers to host applications such as Claude and ChatGPT.
- **2026-07-28 revision:** A major revision finalized on July 28, 2026, described as the most substantial change since authorization was added. It removes protocol-level session tracking (MCP becomes stateless at the protocol layer; version, client identity and capabilities move into a `_meta` parameter per request), deprecates sampling and roots (functional for a minimum of twelve months), and moves Tasks into optional extensions. Not all changes are backward compatible.
- **Security:** The spec now requires OAuth 2.1 security best practices; guidance describes "confused deputy" risks in proxy servers and forbids token passthrough. Tool poisoning attacks (hidden malicious instructions in tool descriptions) and related CVEs (e.g., CVE-2025-6514 in mcp-remote, CVE-2025-49596 in MCP Inspector) are relevant for secure deployments.

## 2. Further Reading (from Wikipedia link list)

One-line descriptions for the most relevant linked entries:

- **JSON-RPC** — JSON-based wire protocol for remote procedure calls; the message format MCP uses.
- **Language Server Protocol (LSP)** — open, JSON-RPC-based protocol between editors/IDEs and language-intelligence servers; MCP reuses its message-flow ideas.
- **OAuth 2.0** — open standard for access delegation; MCP specification requires OAuth 2.1 security best practices.
- **Anthropic** — American AI public benefit corporation (San Francisco); creator of Claude and MCP.
- **Claude (language model)** — series of LLMs developed by Anthropic; released as a chatbot in March 2023 and used in AI-assisted software development.
- **OpenAI** — American AI PBC developing frontier generative AI models; officially adopted MCP in March 2025.
- **Linux Foundation** — nonprofit formed in 2007 to support Linux and open-source software; hosts the AAIF.
- **Agentic AI Foundation** — Linux Foundation directed fund co-founded by Anthropic, Block and OpenAI; governs MCP since December 2025.
- **Agent2Agent (A2A)** — open protocol defining how AI agents communicate with each other across different systems.
- **OpenAPI Specification** — machine-readable interface definition language for describing, producing, consuming and visualizing REST APIs; often compared to MCP.
- **LangChain** — framework helping integrate LLMs into applications.
- **Prompt injection** — cybersecurity exploit in which prompt-like inputs cause unintended behavior in ML models; relevant to trustworthy tool-description handling.
- **Retrieval-augmented generation (RAG)** — technique enabling LLMs to retrieve and incorporate new information from external data sources.
- **Application programming interface (API)** — connection between computers or programs offering a service to other software.
- **Software agent** — computer program that acts for a user or another program in a relationship of agency.
- **Python / TypeScript / C# / Java** — languages of official MCP SDKs; Python and TypeScript SDKs are the most widely used for quick starts.

## 3. Team Scope Decisions (from Slack)

No scoping discussion was found. Searches for "onboarding" returned zero matches; "briefing" and "MCP" returned automated weekly signal digests and a team coordination brief posted by linyue ma (U0BB6DQHKBL) in #所有-mcp-atlas and #all-dumle-servers. A thread check confirmed no threaded replies exist in any of the 9 visible channels, and the last real discussion dated Dec 10–11, 2025 contained only casual game/anime/movie recommendations with no work decisions. Therefore: **no team scope decisions to fold in; record as none found.**

## 4. Current Release Status

No releases have been published on `mcpmark-eval-liuhezi/mcp-onboarding` (latest-release query returned 404; the repository contains only a README.md on `main`). This briefing is the first content landing in the repository.

## 5. Open Questions

- Which spec version should new engineers target (pre- or post 2026-07-28 revision)?
- How deep should the security section go (OAuth 2.1, confused deputy, token passthrough, tool poisoning)?
- Which SDK should be used for hands-on practice (Python, TypeScript, C# or Java)?
- Is access to an internal MCP Test channel possible, and who is the internal point of contact?
- Should MCP Apps (UI extensions) and the Tasks extension be covered for this audience?
- Are there internal MCP servers/tools the new engineers should learn to connect to?
