# TIL: The CLI + MCP workflow is what stops Claude + FlutterFlow from becoming a merge nightmare

**Category:** flutter-mobile

---

## What I learned

The bad pattern is: design in FlutterFlow → export → edit with Claude → re-import → repeat — FlutterFlow's and Claude's code patterns clash and the codebase turns unreadable. The CLI + MCP approach is different: Claude injects changes directly into FlutterFlow's project structure instead of generating competing files, so FlutterFlow's patterns stay intact. Four built-in safeguards: (1) **optimistic concurrency** — the server checks the project's last-modified timestamp against the agent's snapshot before any push, and rejects/retries on conflict, so nothing is silently overwritten; (2) **context refresh** (`flutterflow ai refresh-context`) — Claude re-reads the latest state before planning the next change after visual edits; (3) `.flutterflowignore` protects custom Dart files from being overwritten on re-export; (4) **branches** — each branch has its own project ID, so you can experiment with Claude on a feature branch and merge back safely.

## Why it matters

The right workflow: `flutterflow ai init --project [id]` → run Claude → describe changes → Claude reads state, plans, pushes via MCP → verify visually → refresh context if you made visual edits → repeat. This is "work beside each other," not "stack on top of each other" — most bad experiences mixing low-code tools and AI come from the export/re-import loop, which this avoids entirely.

## Resources

- [Full post → aneesas.hashnode.dev](https://aneesas.hashnode.dev/preventing-merge-nightmares-claude-flutterflow-done-right)
