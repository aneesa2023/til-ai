# TIL: Claude builds, FlutterFlow designs — use both, not one or the other

**Category:** flutter-mobile

---

## What I learned

FlutterFlow owns things Claude can't replicate in real time: instant responsive design updates across all screens, Git-free version history rollback, simultaneous designer+dev collaboration, zero-code Firebase wiring, and a surface non-technical teammates can contribute to. Claude (or any coding agent) is better at wiring logic — auth, state, APIs, custom features. Three integration patterns, in order of recommendation: (1) **CLI + MCP** — `flutterflow ai init --project X --token Y` then run Claude; changes sync to FlutterFlow instantly (~10 min setup, fast, best for teams); (2) **Export + work locally** — `flutterflow export-code` then prompt Claude against the local Dart code, test with `flutter run` (~5 min setup, best for solo devs wanting full control); (3) **Manual export/paste** — design in FlutterFlow, export, paste into Claude in VS Code (~2 min setup, slow, best for one-off edits).

## Why it matters

Use FlutterFlow to fast-design structure (navigation, screens, responsive layout, theme), then Claude to implement the logic layer. Picking the right integration mode (CLI+MCP for rapid team iteration vs. export for solo full control) avoids friction between the visual builder and the agent workflow.

## Resources

- [Full post → aneesas.hashnode.dev](https://aneesas.hashnode.dev/how-to-combine-claude-and-flutterflow-for-rapid-app-iteration)
