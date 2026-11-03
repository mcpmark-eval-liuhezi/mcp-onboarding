## Video

- Title: MCP In 26 Minutes (Model Context Protocol)
- Video ID: kOhLoixrJXo
- URL: https://www.youtube.com/watch?v=kOhLoixrJXo
- Channel: Tina Huang
- Duration: 26:23 (published 2025-10-15)

## Takeaways from the transcript

- MCP is defined by Anthropic as an open protocol that standardizes how LLM applications connect to and work with your tools and data sources - it is a shared contract between an AI application and the outside world, not a product feature of any one vendor.
- The core mental model is the USB analogy: MCP is a universal plug that lets any device connect to any other device. Before a universal standard you needed special cords, different adapters, and custom software for every pairing - which is exactly the N-apps-times-M-tools integration problem MCP removes.
- The fundamentals are a host-client-server architecture: the AI application is the host (e.g. Claude Desktop), an MCP client embedded in the host connects out to MCP servers, and each server exposes capabilities back to the model.
- An MCP server exposes three primitives - Tools (functions the model can invoke, like search_web or write_sheet), Resources (data the model can read, like file contents or database records), and Prompt Templates (reusable, standardized task instructions such as analyze_sheet_data).
- The communication life cycle between client and server runs over JSON-RPC with two transport options - stdio for local subprocess servers and HTTP/SSE for remote servers - so the same protocol covers local and hosted deployments.
- You can build your own MCP server both with code and with no code: the no-code route assembles a server in a builder, while the code route writes a Python server (e.g. the video's Google Sheets server) that you test with the MCP Inspector (npx @modelcontextprotocol/inspector) and register in Claude Desktop via claude_desktop_config.json under mcpServers with command, args, and env.
- The video is structured as a teach-then-verify course, with quiz checkpoints after each major section (definition, fundamentals, life cycle, and the two build walkthroughs) so you can confirm you actually retained each concept before moving on.

## Papers

- arXiv:2509.25292 - A Measurement Study of Model Context Protocol Ecosystem
- arXiv:2505.02279 - A survey of agent interoperability protocols: Model Context Protocol (MCP), Agent Communication Protocol (ACP), Agent-to-Agent Protocol (A2A), and Agent Network Protocol (ANP)
- arXiv:2606.30317 - MCP Server Architecture Patterns for LLM-Integrated Applications
- arXiv:2504.08999 - MCP Bridge: A Lightweight, LLM-Agnostic RESTful Proxy for Model Context Protocol Servers
- arXiv:2507.16044 - From REST to MCP: An Empirical Study of API Wrapping and Automated Server Generation for LLM Agents
