# MCP Onboarding Briefing

Model Context Protocol (MCP) onboarding document for new engineers. Landed as a pull request into `main` of the `mcp-onboarding` repository.

## 1. Overview

The Model Context Protocol (MCP) is an open standard and open-source framework introduced by Anthropic in November 2024 to standardize the way AI systems such as large language models integrate and share data with external tools, systems, and data sources. It provides a standardized interface for reading files, executing functions, and handling contextual prompts. Following its announcement, the protocol was adopted by major AI providers including OpenAI and Google DeepMind. In December 2025, Anthropic donated MCP to the Agentic AI Foundation, a fund under the Linux Foundation.

MCP uses JSON-RPC 2.0 messages between hosts, clients, and servers, and exposes server features (Resources, Prompts, Tools) plus client features such as Elicitation. The latest spec version per the project is 2026-07-28 (released July 28, 2026).

## 2. Further Reading

Entries linked from the Wikipedia article "Model Context Protocol", with one-line descriptions:

- **JSON-RPC** — JSON-based wire protocol for remote procedure calls; transport-independent (HTTP/TCP), supports notifications and async calls; no built-in authentication.
- **Language Server Protocol (LSP)** — JSON-RPC-based protocol between editors/IDEs and language servers providing code completion, syntax highlighting, diagnostics, and refactoring; originally developed for VS Code.
- **OAuth 2.0** — Open standard for access delegation; lets applications obtain limited access to user resources without sharing passwords; widely used for securing MCP server access.
- **Prompt injection** — Cybersecurity exploit where innocuous-looking inputs manipulate LLM behavior by bypassing safeguards; relevant to securing MCP tools and prompts.
- **Agent2Agent (A2A)** — Open protocol defining how AI agents communicate across different systems, discover one another, exchange messages, and coordinate tasks.
- **Anthropic** — AI company founded 2021 in San Francisco; creator of the Claude LLM family and MCP; donated MCP to the Agentic AI Foundation in Dec 2025.
- **Linux Foundation** — Nonprofit formed 2007 supporting Linux and open-source software; hosts the Agentic AI Foundation under which MCP now falls.
- **Cloudflare** — Cloud provider that runs MCP compatibility events and has fixed security/reliability bugs in the MCP registry.
- **Microsoft** — Co-maintainer of the AAIF org; publishes MCP docs, test channels, and server testing documentation.
- **OpenAI** — Adopted MCP in March 2025 (Agents SDK); MCP clients shipped in its Agents SDK.
- **Google DeepMind** — Embedded MCP into Gemini; MCP support announced at Google I/O 2025.
- **API** — Generic concept; MCP defines a standardized API for tools, resources, and prompts.

## 3. Team Scope Decisions (from Slack)

Source: Slack workspace team T0BAQV600R5, channel #所有-mcp-atlas (C0BBA2QSZ4L), thread at ts 1793281886.398579 (user U0BB6DQHKBL / linyue ma).

Decided scope for the briefing:
- Cover what MCP is (open protocol, JSON-RPC 2.0, host/client/server model, Resources/Prompts/Tools/Elicitation).
- Cover governance and versions: latest spec 2026-07-28; donated to Agentic AI Foundation (Linux Foundation directed fund, co-founded with OpenAI and Block) as of Dec 9, 2025.
- Cover real-world use: OpenAI Agents SDK (2025), Google DeepMind/Gemini, Microsoft Azure AI Foundry/Copilot Studio, Cloudflare compatibility event.
- Cover security and extensions: resource limits, compliance monitoring, key management, data privacy; extensions incl. tasks, MCP Apps.
- Team integration: block a calendar for the team, create an MCP Test channel, keep/publish one consolidated MCP writeup; consider issuing a writeup with current version number, validation tools, and a chart with weaknesses.
- Noted that no MCP-related discussion was previously visible in the workspace; linyue ma maintains the official channels and is the best internal point to start from.

## 4. Current Release Status

The `mcpmark-eval-liuhezi/mcp-onboarding` repository has **no releases published** (release list is empty; latest-release endpoint returns 404). There is no current version to state; this briefing itself is the first documented release candidate.

## 5. Open Questions

- Which MCP spec version should new engineers target for onboarding (2026-07-28 vs. earlier)? Confirm against modelcontextprotocol.io at briefing time.
- Which official SDKs to recommend (Python, TypeScript, Go, Java, C#)?
- How to validate MCP servers/connections in the team environment (test clients, registry usage)?
- What security review is needed for tools exposing data sources (resource limits, OAuth 2.0 consent flows, prompt-injection safeguards)?
- Whether to stand up an MCP Test channel and how to gate access.
- Confirm the AAIF governance contacts and registry usage for the current date.
