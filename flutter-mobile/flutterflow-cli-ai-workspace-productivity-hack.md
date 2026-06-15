# TIL: FlutterFlow CLI + AI workspace turns FlutterFlow into an agent-driven local dev loop

**Category:** flutter-mobile

---

## What I learned

`flutterflow ai init` scaffolds a local AI workspace and registers an MCP server with whatever agent is on your PATH (Claude Code, Gemini CLI, Codex). From there you `cd` in and prompt directly — the agent talks to FlutterFlow's cloud via MCP, while the actual project still lives on FlutterFlow's servers. The local workspace is just the entry point.

## Why it matters

This bridges FlutterFlow's visual/designer workflow with a CLI/agent-driven workflow without giving up either — you keep FlutterFlow's drag-drop builder and Firebase integration, but iterate via natural-language prompts in your terminal. Noticeably sped up coding velocity in the first week of use.

## Notes / Code

```bash
flutterflow ai init
```

## Resources

- [Full post → aneesas.hashnode.dev](https://aneesas.hashnode.dev/flutterflow-cli-ai-workspace-my-designer-to-cli-productivity-hack)
