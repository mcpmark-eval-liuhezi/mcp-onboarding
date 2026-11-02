# MCP Onboarding Briefing

Model Context Protocol (MCP) onboarding for new engineers.

## 1. Short Overview

The Model Context Protocol (MCP) is an open standard and open-source framework introduced by Anthropic in November 2024 to standardize the way artificial intelligence (AI) systems like large language models (LLMs) integrate and share data with external tools, systems, and data sources. MCP provides a standardized interface for reading files, executing functions, and handling contextual prompts. Following its announcement, the protocol was adopted by major AI providers, including OpenAI and Google DeepMind. In December 2025, Anthropic donated MCP to the Agentic AI Foundation (AAIF), a fund under the Linux Foundation.

Architecture: MCP distinguishes between hosts (typically an AI agent that interacts with an LLM), clients (one dedicated client per server, created by the host), and servers (which expose tools, resources, and prompts). The client and server communicate using JSON-RPC 2.0 messages. SDKs are available in Python, TypeScript, C#, and Java.

Adoption: OpenAI officially adopted MCP in March 2025 (ChatGPT desktop app; MCP apps support added September 2025). Microsoft exposes MCP support in Azure AI Foundry and Copilot Studio. By mid-2026, more than 10,000 MCP servers had been deployed in production, with SDKs downloaded over 97 million times per month.

2026-07-28 revision: On July 28, 2026, maintainers finalized a major revision described as the most substantial change since the addition of authorization. The revision makes MCP stateless at the protocol layer (version, client identity, and capabilities carried in a _meta parameter with each request), deprecates sampling and roots (functional for a minimum of twelve months), and moves Tasks for long-running operations into optional extensions. Not all changes are backward compatible.

Security: MCP has been subject to several vulnerabilities. In April 2025, Invariant Labs described "tool poisoning attacks" where malicious instructions are hidden in MCP tool descriptions. In July 2025, JFrog disclosed CVE-2025-6514 (CVSS 9.6) in mcp-remote (affected 0.0.5-0.1.15, fixed in 0.1.16), and researchers reported CVE-2025-49596 in Anthropic's MCP Inspector. The specification now requires implementations to follow OAuth 2.1 security best practices and describes "confused deputy" risks in MCP proxy servers; token passthrough is forbidden.

## 2. Further Reading

One-line descriptions for particularly relevant entries from the Wikipedia article's link list:

- JSON-RPC — JSON-based wire protocol for remote procedure calls; MCP uses JSON-RPC 2.0 messages.
- Large language model — neural network model trained on vast text for language generation and understanding; the AI systems MCP connects to.
- Anthropic — American AI public benefit corporation headquartered in San Francisco; creator of Claude and MCP.
- Agentic AI Foundation — Linux Foundation directed fund (co-founded by Anthropic, Block and OpenAI) that now hosts MCP governance.
- Agent2Agent (A2A) — open protocol defining how AI agents communicate with each other across different systems/vendors.
- Language Server Protocol (LSP) — open JSON-RPC-based protocol between editors/IDEs and language-inspection servers; MCP reuses its message-flow ideas.
- Prompt injection — cybersecurity exploit through which prompts are designed to cause unintended model behavior; relevant to trusted tool-description input.
- OAuth 2.0 — open standard for access delegation; MCP security requirements now reference OAuth 2.1 best practices.
- OpenAPI Specification — spec for describing REST APIs; often compared with MCP.
- LangChain — framework for building language-model applications.
- Retrieval-augmented generation (RAG) — technique combining information retrieval with language-model generation; related to MCP data-source integration.
- API (Application programming interface) — connection between computers or programs.
- Linux Foundation — nonprofit founded in 2007 hosting open-source projects including the AAIF.
- Claude — Anthropic's proprietary LLM series; MCP hosts such as Claude and ChatGPT use it.
- GitHub — host of the modelcontextprotocol organization (spec, SDKs, registry).

## 3. Team Scope Decisions (from Slack)

Searches for "briefing onboarding", "scope skip", and "onboarding" returned zero matches. Searches for "Model Context Protocol" and "MCP" matched only automated weekly signal digests and a single "FIX THIS" correction message in the general channel #所有-mcp-atlas (all from linyue ma, U0BB6DQHKBL). Those posts note "Not seeing MCP-related discussion on the workspace" and suggest issuing a writeup with the current version number, validation tools, and a chart of weaknesses. No thread replies existed beyond the parent message. Conclusion: no explicit scope decisions (what to cover vs. skip) were found in Slack; this briefing covers the standard onboarding set (overview, architecture, adoption, security, further reading) and leaves specific exclusions to the team.

## 4. Current Release Status

No releases have been published on mcpmark-eval-liuhezi/mcp-onboarding: the releases list is empty and the latest-release endpoint returns 404. The repository (created 2026-10-20) pre-existed this work; this PR lands the first content, docs/mcp-onboarding.md, on branch add-mcp-onboarding-briefing-v4 against the default branch main.

## 5. Open Questions

- Which canonical spec version should we target (2026-07-28 revision is the latest per Wikipedia)?
- How deep should security coverage go (tool poisoning, OAuth 2.1, confused deputy, CVE-2025-6514/49596)?
- Which SDK (Python or TypeScript) for hands-on practice?
- Internal MCP Test channel access and internal point of contact (per Slack digest suggestion)?
- Whether to include MCP Apps / Tasks extension coverage given the 2026-07-28 changes?
