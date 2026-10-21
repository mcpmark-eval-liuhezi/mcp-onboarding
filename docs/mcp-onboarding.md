# Model Context Protocol (MCP) — Onboarding Briefing

Prepared for the three engineers joining the week of Monday's return-to-office. This briefing is the short version of what MCP is, what to read next, what the team has decided about scope, and what is still open.

---

## 1. What MCP is (short overview)

The **Model Context Protocol (MCP)** is an open standard and open-source framework introduced by **Anthropic in November 2024** that standardizes how AI systems such as large language models (LLMs) integrate and share data with external tools, systems, and data sources. It provides a standardized interface for reading files, executing functions, and handling contextual prompts.

Key points for onboarding:

- **Why it exists.** Before MCP, developers typically built custom connectors for every data source or tool — the "N×M" integration problem. MCP replaces that with one standard interface. Earlier approaches (OpenAI's 2023 function-calling API, the ChatGPT plug-in framework) solved similar problems but required vendor-specific connectors.
- **Architecture.** MCP distinguishes **hosts** (typically an AI agent/LLM application), **clients** (one per server, created by the host), and **servers** (local or remote), each exposing **tools** and **resources**. Client and server communicate over **JSON-RPC 2.0**. MCP reuses message-flow ideas from the Language Server Protocol (LSP).
- **Tooling.** Shipped with SDKs in Python, TypeScript, C#, and Java. Adopted by IDEs and coding platforms (Replit, Sourcegraph and others) to give AI coding assistants real-time access to project context. **MCP Apps** is an official extension (built on mcp-ui) standardizing interactive UI delivery from servers to hosts like Claude and ChatGPT.
- **Adoption and governance.** Adopted by major AI providers including OpenAI (March 2025) and Google DeepMind. In **December 2025, Anthropic donated MCP to the Agentic AI Foundation (AAIF)**, a directed fund under the Linux Foundation co-founded by Anthropic, Block and OpenAI. By mid-2026 more than 10,000 MCP servers were reportedly in production, with SDK downloads over 97 million per month.
- **Recent spec change.** A major revision was finalized on **2026-07-28**: MCP is now stateless at the protocol layer (protocol version, client identity and capabilities move into a `_meta` parameter on each request), several little-used features were deprecated (sampling, roots — functional for at least twelve more months), and long-running Tasks moved to optional extensions. Not fully backward compatible.
- **Security.** Known issues include "tool poisoning" prompt-injection attacks hidden in tool descriptions (Invariant Labs, April 2025) and CVEs in MCP tooling (CVE-2025-6514 in mcp-remote, CVSS 9.6; CVE-2025-49596 in MCP Inspector). The specification now requires implementations to follow OAuth 2.1 best practices.

*Source: Wikipedia, "Model Context Protocol."*

---

## 2. Further reading

The MCP article links out to a large number of related entries (several hundred, spanning AI companies, protocols, security, and machine-learning concepts). The handful most relevant for onboarding, with one-line descriptions:

| Entry | What it is |
|---|---|
| **Anthropic** | The AI public benefit corporation that created MCP; its flagship product is the Claude model series. |
| **Language Server Protocol (LSP)** | The open, JSON-RPC-based editor/server protocol whose message-flow ideas MCP reuses; LSP decouples language tooling from any specific IDE. |
| **JSON-RPC** | The JSON-based remote-procedure-call wire protocol MCP uses for client/server communication; transport-independent, supports notifications and asynchronous calls. |
| **Large language model** | The class of model (trained on vast text corpora, typically transformer-based) that acts as MCP's host intelligence. |
| **Open standard** | What MCP is as a category: a standard openly accessible and usable by anyone, with open participation in its development. |
| **Agentic AI Foundation (AAIF)** | The Linux Foundation directed fund (co-founded by Anthropic, Block and OpenAI) that MCP was donated to in December 2025. |
| **Agent2Agent (A2A)** | A complementary open protocol for agent-to-agent communication, discovery, and task coordination across vendors and frameworks. |
| **Agent Skills** | Anthropic's companion open standard for packaging task-specific instructions/resources that agents load on demand. *(Note: no standalone Wikipedia article exists for this entry yet.)* |
| **Claude (language model)** | Anthropic's LLM series, available as a chatbot, an API, and agent harnesses such as Claude Code. |
| **OpenAI** / **Google DeepMind** | The other major AI providers that adopted MCP after its announcement. |
| **Prompt injection** | The exploit class behind MCP's "tool poisoning" risk — inputs crafted to make a model treat adversarial text as instructions. |
| **OAuth 2.0** | The access-delegation standard the MCP specification now requires implementations to follow (2.1 best practices). |
| **OpenAPI Specification** | The machine-readable interface-definition standard for web services; useful background when wrapping existing APIs as MCP servers. |
| **AI-assisted software development** | The practice of using LLMs and agents to write, debug, test, and document code — the working context where most engineers first meet MCP. |

The article's full link list also covers many more entries (AI industry history, ML fundamentals, other AI tools and companies); the table above is the curated subset for this briefing.

---

## 3. Team scope decisions (from Slack)

**No team discussion of MCP briefing scope was found in Slack.** Searches for "MCP onboarding briefing", "onboarding", "briefing", "MCP", "Model Context Protocol", "scope", and "new hires" returned no matches, and a manual review of every visible channel (#社交, #所有-mcp-atlas, #新频道, #new-channel, #gaming-suggestions, #tv-show-suggestions, #all-dumle-servers, #social, #movie-suggestions) and all DMs turned up only join/announcement messages and off-topic chatter (games, anime, films). Search itself works — a control query for unrelated terms correctly returned matches — so this is an absence of the discussion, not a search failure.

**Consequence:** there are no recorded team decisions on what this briefing should cover or skip. The scope above is the author's best judgement, and the open questions below include confirming scope with the team once a discussion exists.

---

## 4. Current release status

This repository (**mcpmark-eval-liuhezi/mcp-onboarding**) has **no releases yet** — both a latest-release lookup (404) and a full release listing returned empty. There is therefore no version to cite; the briefing is unversioned draft material until the first release is cut.

*(Separate note: an earlier attempt to create a fresh repository named `mcp-onboarding` failed with "name already exists on this account" — this repository already existed with study material. The briefing was landed here as the natural home instead.)*

---

## 5. Open questions

1. **Scope confirmation.** No Slack thread exists recording what the team agreed this briefing should cover and skip — should we hold that discussion and record the decisions here?
2. **First release.** Should this repository cut an initial tagged release (e.g. `v0.1.0`) once the briefing is reviewed and merged, so future edits have a version to point to?
3. **Spec-revision depth.** Should the 2026-07-28 stateless revision and its deprecations get their own deep-dive section, or stay a bullet in the overview?
4. **Hands-on material.** Should this briefing link into the existing MCP study material already in this repository (open PR #1 adds a resource list with video and paper references) rather than duplicating it?
5. **Security module.** Do the new engineers need a dedicated walkthrough of tool-poisoning / prompt-injection risks before they write their first MCP server, or is the overview enough?

---

*Maintained as a living document — this is a pull request precisely so it can be reviewed and updated instead of rotting in a download folder.*
