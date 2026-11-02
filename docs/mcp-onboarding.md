# Model Context Protocol (MCP) — Onboarding Briefing

Prepared for three new engineers starting the week of the walkthrough. This briefing consolidates: a short background overview, further reading, team-scoping decisions, current release status, and open questions.

## 1. Short Overview

The Model Context Protocol (MCP) is an open protocol, announced November 25, 2024, that standardizes how AI applications (hosts) connect to external data sources and tools (servers) and to clients inside that stack. Messages between hosts, clients, and servers use JSON-RPC 2.0. Servers expose capabilities in two groups: server features (Resources, Prompts, Tools) and client features (notably Elicitation — server-initiated requests from users, including multi-round-trip negotiations on the latest spec, plus a Registry to discover available servers). Governance moved to the AGENTIC AI foundation (AAIF), a Linux Foundation directed fund co-founded with OpenAI and Block, as of December 9, 2025; code, specs, SDKs, and the registry all live under that umbrella. In practice: OpenAI shipped MCP clients into its Agents SDK in 2025; Google DeepMind is embedding MCP into Gemini and Google Cloud exposes data via MCP-type connectors; Microsoft puts MCP support in Azure AI Foundry and Copilot Studio with a public MCP Test channel; Cloudflare ran an MCP compatibility event and fixed registry bugs. Key security considerations include resource limits, compliance monitoring, key management, and personal-data privacy controls; the project publishes API best-practice and threat-model docs plus an open public registry.

## 2. Further Reading

Wikipedia lookup note: the Model Context Protocol article search returned no results and article/link fetches timed out, so the further-reading list below is drawn from the workspace briefing material and general knowledge rather than the article's link list.

- **JSON-RPC 2.0** — The wire protocol MCP messages are built on; defines requests, responses, errors, and notifications.
- **Anthropic** — The company that introduced MCP as an open standard in late 2024; the original maintainer and reference implementation.
- **AGENTIC AI foundation (AAIF)** — Linux Foundation directed fund that now governs MCP (donation effective December 9, 2025), co-founded with OpenAI and Block.
- **OpenAI Agents SDK** — Where OpenAI shipped MCP clients in 2025; a concrete place to see MCP in the wild.
- **Google Gemini / Google Cloud** — DeepMind embedding MCP; Cloud exposing data via MCP-type connectors.
- **Microsoft Azure AI Foundry / Copilot Studio** — Microsoft's MCP support surface, including a public MCP Test channel.
- **Cloudflare MCP event** — Industry compatibility event and registry bug-fix effort; useful case study for ecosystem health.

## 3. Team Scope Decisions (Slack)

No scope decisions were found. Slack searches for "Model Context Protocol", "briefing", "onboarding", and "scope" returned only automated weekly-signal digest posts and a single correction message in #所有-mcp-atlas — no thread where the team agreed what to cover or skip in this briefing. Per the instruction, this is recorded as: none found. Until such a discussion turns up, the briefing defaults to the overview, further reading, release status, and open questions below.

## 4. Current Release Status

No releases have been published in the `mcp-onboarding` repository (`mcpmark-eval-liuhezi/mcp-onboarding`). The releases list is empty and the latest-release query returned 404, so this briefing is the first content landing in the repo. Spec version referenced in workspace material: 2026-07-28 (released July 28, 2026).

## 5. Open Questions

- Canonical spec version to target for hands-on practice (2026-07-28 vs. newer).
- Depth of security coverage needed (resource limits, compliance monitoring, key management, personal-data controls).
- Which SDK to use for hands-on practice.
- Internal MCP Test channel access for the team.
- Internal point of contact for MCP questions (linyue ma maintains the official channels per workspace material).

## 6. Sources & Notes

- Wikipedia: Model Context Protocol article search returned no results; article fetches timed out. Further reading descriptions are from workspace briefing material and general knowledge, not the article's link list.
- Slack: #所有-mcp-atlas thread reviewed; no scoping discussion found (see §3).
- GitHub: repo `mcpmark-eval-liuhezi/mcp-onboarding` pre-existed; no releases; no pending PR reviews on authored PRs #5/#6.
