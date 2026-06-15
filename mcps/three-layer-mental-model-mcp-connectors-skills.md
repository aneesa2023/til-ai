# TIL: A three-layer mental model for agents, MCP/connectors, and skills

**Category:** mcps

---

## What I learned

Think of an AI agent as a new hire: capable on day one, but useless without access or knowledge of "how we do things." That maps to three distinct layers. Layer 1 (reasoning — who does the work): an **agent** is a model running in a loop — goal, action, observe, repeat; a **sub-agent** is a specialist the main agent spawns for a bounded task in its own context window, returning only a summary (keeps the main thread clean, enables parallelism). Layer 2 (connection — what it can reach): a **tool** is one function/permission (`get_issue(id)`); **MCP** is the standardized "USB-C for tools" — package tools/data/prompts behind a server once, any MCP client can use them; a **connector** is just a hosted MCP server with auth pre-handled and a one-click toggle — same layer, more managed. Layer 3 (instruction — your way of doing things): a **skill** is a `SKILL.md` folder of procedural instructions (optionally with scripts/files) that's only loaded into context when a task matches — progressive disclosure, like pulling the relevant handbook page.

## Why it matters

"Should we build an MCP or a skill?" is usually the wrong question — the real question is whether the agent is missing a *capability* (MCP/connector problem) or *instructions* for something it can already do (skill problem). These layers stack rather than compete: the agent thinks, MCP/connectors let it reach, skills tell it your conventions. Misdiagnosing which layer a gap belongs to — e.g., wrapping a skill's worth of instructions inside a custom MCP server, or spawning sub-agents that should've been a single prompt — is one of the most common mistakes in agent design.

## Resources

- [Full post → aneesas.hashnode.dev](https://aneesas.hashnode.dev/stop-confusing-mcp-connectors-and-skills-a-three-layer-mental-model)
