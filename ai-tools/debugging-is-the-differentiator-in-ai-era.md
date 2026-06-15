# TIL: Reviewing AI-generated code means auditing contracts, not reading syntax

**Category:** ai-tools

---

## What I learned

AI-generated code "looks right" — idiomatic, clean, plausibly correct — so the old skim-the-PR review style misses silent bugs (swallowed exceptions, off-by-one loop bounds, missing null checks). Volume also broke the old workflow: 2,000 lines/day from an agent vs. ~200 lines of careful human review. Five practices that actually hold up: (1) write tests in a separate session/model from the implementation, so tests check the spec, not the code's own assumptions; (2) review contracts — inputs, outputs, error handling, side effects — not line-by-line; (3) ask the agent directly what assumptions and edge cases it skipped; (4) ship behind feature flags, canary to 1%, and watch error/latency metrics rather than trusting the agent's confidence; (5) build structured logging, distributed tracing, error tracking, and an MCP layer for production signals *before* you need them.

## Why it matters

The job shifted from typing to auditing, from syntax knowledge to systems thinking. Debugging — not code generation speed — is now the actual skill differentiator.

## Resources

- [Full post → aneesas.hashnode.dev](https://aneesas.hashnode.dev/in-the-ai-era-debugging-is-the-differentiator)
