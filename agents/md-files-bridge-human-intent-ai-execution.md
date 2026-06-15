# TIL: .md files are the token-efficient bridge between human intent and AI execution

**Category:** agents

---

## What I learned

Markdown isn't new, but every major AI coding tool (Claude Code, Cursor, Copilot, Windsurf) reads `.md` natively and far more cheaply than PDFs or Word docs — a cleaned `.md` runs 2,000–2,500 tokens vs. 6,000–8,000 for a raw PDF, and a delta file (changes only) can be 200–500 tokens. Practical patterns: persistent AI context via auto-read config files (`CLAUDE.md`, `.cursorrules`, `.github/copilot-instructions.md`); a "spec-first" workflow where `SPEC.md`/`PLAN.md` defines problem, approach, acceptance criteria, and out-of-scope before any code is written; ADRs in `/adr/*.md` that travel with the code in Git; and Mermaid diagrams inside `.md` that diff cleanly and render natively, replacing unversionable screenshot diagrams.

## Why it matters

The big blind spot: blindly converting a PRD to `.md` silently drops images — wireframes, flow diagrams, ERDs, architecture diagrams. The fix is to redraw them as Mermaid (flowchart, erDiagram, sequenceDiagram) or keep a Figma link, not just convert and hope. `.md` files aren't replacing PRDs — it's a split: the original PRD/DOCX stays for multi-audience human communication, while a derivative `.md` (with `CLAUDE.md` as a pointer file, not a content dump) serves AI + devs. Anything you'd normally put in Notion/Confluence/Jira comments should go in a versioned `.md` in the repo instead — write once, every AI tool reads it, and token costs stay flat as the project grows.

## Resources

- [Full post → aneesas.hashnode.dev](https://aneesas.hashnode.dev/md-files-became-the-bridge-between-human-intent-and-ai-execution)
