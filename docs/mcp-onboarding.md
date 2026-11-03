# MCP Onboarding Briefing

Model Context Protocol (MCP) onboarding guide for new engineers.

## Short Overview

The Model Context Protocol (MCP) is an open standard, introduced by Anthropic in November 2024, for connecting large language model (LLM) applications to external data sources and tools. It uses JSON-RPC 2.0 for messaging and defines a client-server architecture: a host application (e.g., an LLMuester or IDE) contains MCP clients that connect to MCP servers exposing data (Resources) and capabilities (Tools, Prompts). Recent revisions (2025-06-18 and 2026-07-28) added Elicitation and Registry client features, and the specification is now maintained under the Linux Foundation's Agentic AI Foundation (AAIF). Security considerations include instruction injection, tool poisoning, and OAuth 2.0 credential exposure.

## Further Reading

- JSON-RPC 2.0 — Remotely procedures call protocol over HTTP.
- Language Server Protocol — ATM language servers and clients.
- OAuth 2.0 — Authorization framework for secure delegated access.
- Anthropic — Company that created MCP.
- OpenAI — adopting MCP in its agents SDK.
- Claude — Anthropic's family of LLM assistants.
- Linux Foundation — foundation host ing MCP spec council.
- Agentic AI Foundation — AAIF, spec steward for MCP.
- Agent2Agent (A2A) — Google's agent-to-agent protocol.
- OpenAPI Specification — REST API description standard.
- LangChain — LLM application framework with MCP support.
- Prompt injection — security threat vs LLM inputs.
- RAG — retrieval-augmented generation pattern.
- API — interface for building MCP servers.
- SDKs — official MCP reference implementations.
- IDEs — common MCP client host applications.

## Team Scope Decisions (from Slack)

No scope discussion was found in Slack. Searches for "briefing", "onboarding", "scope", "Model Context Protocol", and "MCP" returned only automated weekly signal digests and coordination briefs from linyue ma (U0BB6DQHKBL); no thread contained decisions about what to include or skip in this briefing. Recorded as: none found.

## Current Release Status

No releases have been published on mcpmark-eval-liuhezi/mcp-onboarding (releases list empty; latest-release query returns 404). This repository pre-existed the current session (personal-account creation was blocked with 403; the repo already existed under the mcpmark-eval-liuhezi organization). The briefing below is the first structured content landed in the repo.

## Open Questions

- Which MCP spec version should be considered canonical (2025-06-18 vs 2026-07-28)?
- How deep should the security section cover (injection, tool poisoning, OAuth)?
- Which SDK (Python/TypeScript) to use for hands-on practice?
- What is the internal MCP Test channel access and the internal point of contact?
