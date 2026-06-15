# TIL: MCPs (not the model) cut a day's mobile feature work to 90 minutes

**Category:** mcps

---

## What I learned

MCP lets AI assistants connect to real tools — Xcode, simulators, Figma files, Crashlytics — instead of guessing from screenshots/descriptions. Platform vendors have gone all-in: Apple ships a built-in MCP server in Xcode, Flutter's official MCP is stable, Expo and Firebase MCPs are GA. Figma's Dev Mode MCP lets the AI read actual design variables/components/layout, turning design-to-Flutter or design-to-SwiftUI into a 15-minute review instead of a half-day translation. Firebase Crashlytics MCP turns crash triage into a direct question ("what's the top new crash this week and which commit caused it?") with an actionable answer instead of dashboard tab-switching. Cross-platform device control is solved via Mobile MCP (mobile-next, unifies iOS/Android) or XcodeBuildMCP (deeper iOS-only with LLDB debugging).

## Why it matters

Off-the-shelf MCPs cover ~80% of a workflow; the smartest move is building 1-2 custom MCPs for your team's specific internal design system, proprietary backend, or CI — that's the last 20% that actually matches how your team works. Check the growing MCP directory (Deployment/DevOps, Security/Testing, Web Scraping, Collaboration, vendor-official) before building your own.

## Resources

- [Full post → aneesas.hashnode.dev](https://aneesas.hashnode.dev/90-minutes-not-a-day-how-mcps-not-the-model-sped-up-my-mobile-dev-workflow)
