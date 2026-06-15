# TIL: OpenCode vs. Claude Code is a control-vs-convenience trade, not a feature shootout

**Category:** ai-tools

---

## What I learned

OpenCode (SST, MIT-licensed) is an open-source, terminal-first coding agent with a Plan mode, MCP support, an `AGENTS.md` for project context, and a scriptable non-interactive mode for CI. The two features it's usually praised for — automatic context compaction and routing cheap tasks to cheap models — aren't actually differentiators: Claude Code does both, arguably more sophisticatedly (a "microcompact" step that clears stale tool output without a model call, plus sub-agents that isolate verbose work and return clean summaries, and model tiering via `/model opusplan` for Opus-planning + Sonnet-execution). The real split is philosophical: **OpenCode optimizes for control and neutrality** — swap between Claude/GPT/Gemini/local models mid-session, inspect/fork the open-source agent itself, bring your own API key for per-token cost visibility. **Claude Code optimizes for integration and convenience** — Claude-only, but with a flat-fee Pro/Max subscription instead of metered tokens, first-party feature access, and near-zero setup.

## Why it matters

OpenCode's pay-per-token model turns "keep context lean" from good hygiene into a literal invoice line item — every re-read and loop is metered, which makes token-maxing a core skill rather than a nice-to-have (keep `AGENTS.md` lean since it's sent every turn, use Plan mode before expensive work, scope prompts to specific files, start fresh sessions, route by difficulty). The upside is more cost levers and model flexibility. For large enterprises, OpenCode has a real story — centralized config integrating with SSO/internal AI gateways, no data retention, per-seat pricing with no token charges via your own gateway — but its compliance/governance tooling (SOC 2, SCIM, RBAC, audit logs) is thinner than incumbents', so verify rather than assume parity. The actual decision: model flexibility and openness vs. a flat-fee ceiling and first-party polish.

## Resources

- [Full post → aneesas.hashnode.dev](https://aneesas.hashnode.dev/)
