# Model Context Protocol (MCP) — Onboarding Briefing

Prepared for three new engineers joining the team. This doc is the team's MCP onboarding
briefing and supersedes any half-lived copies floating in个人 downloads.

## 1. Short Overview

The Model Context Protocol (MCP) is an open protocol, announced by Anthropic on
25 November 2024, that standardizes how AI applications (hosts) connect to external
data sources and tools (servers) through a client. Messages between hosts, clients,
and servers use JSON-RPC 2.0. Servers expose capabilities such as Resources, Prompts
and Tools; clients can request Elicitation (server-initiated requests from users,
including multi-round trips and inter-client agreement on end negotiations) and use
the Registry to discover available servers.

Governance note: as of 9 December 2025, the MCP donation went to the AGENTIC AI
foundation (AAIF), a Linux Foundation directed fund co-founded with OpenAI and
Block; the project code, specs, SDKs and registry now live under the AAIF umbrella.

## 2. Further Reading

Wikipedia lookup note: the Wikipedia search for "Model Context Protocol" and
related queries returned no results, and direct article/link-fetch calls timed out
or came back empty. The following further-reading items are therefore **not** taken
from the article's link list; they are well-established adjacent topics with a one
line each, offered as a sensible starting set:

- **JSON-RPC 2.0** — The wire format MCP uses for messages between hosts, clients
  and servers.
- **Anthropic** — The company that created and initially open-sourced MCP.
- **AGENTIC AI foundation (AAIF)** — The Linux Foundation directed fund that now
  hosts the MCP project, specs, SDKs and registry.
- **OpenAI Agents SDK** — Orgs shipping MCP clients into their agent toolkits.
- **Google Gemini / Google Cloud** — Projects embedding or exposing MCP-type
  connectors.
- **Microsoft Azure AI Foundry / Copilot Studio** — Microsoft's MCP support and
  public MCP Test channel.

## 3. Team Scope Decisions (from Slack)

No such discussion was found. A workspace-wide Slack search for "Model Context
Protocol", "onboarding briefing scope" and related terms returned only automated
weekly signal digest posts by a single user (linyue ma / malinyue199) in
#所有-mcp-atlas; these are digest/coordination posts, not a team discussion that
agreed what the briefing should cover and what to skip. There is no record of
team scope decisions to fold in, so this briefing uses a default onboarding
structure (overview, further reading, security/extension awareness, hands-on
next steps). If a real scoping discussion happened elsewhere ( another channel, DMs,
or a deleted thread), it was not recoverable from the available history.

## 4. Current Release Status

The `mcp-onboarding` repository exists in the `mcpmark-eval-liuhezi` organization and
was initialized with a README, but **no releases have been published yet** —
the latest-release query returned 404 Not Found. Version of the briefing itself:
this document is the first content landing in the repo; there is no tagged version
to cite. Once merged, the branch `add-mcp-onboarding-briefing` becomes the source.

## 5. Open Questions

- Which MCP spec version should we treat as canonical for onboarding examples
  (2026-07-28 per current docs, or an earlier stable release)?
- How deep should the security section go (resource limits, compliance monitoring,
  key management, data privacy) versus a pointer to the official threat-model docs?
- Should the three new engineers each run a local MCP server example before the
  Monday briefing, and if so, which SDK (Python/TypeScript)?
- Is there an internal MCP Test channel or registry access we should use for
  hands-on practice?
- Who is the internal point of contact for MCP questions (the workspace notes
  point to linyue ma as the best starting internal contact)?

## 6. Draft Review Note

No pending draft pull-request review was found on any of the authored PRs checked
(`italian-newsletter#1`, `advisory-brief-2026-10#1` both returned empty review lists),
so there was nothing to discard.
