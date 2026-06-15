# TIL: AI tools get you to ~60% of a production app — the rest is architecture

**Category:** app-builders

---

## What I learned

Tools like v0, Bolt, Lovable, FlutterFlow, Cursor, and Devin can take an app from prompt to working prototype in hours. But "remarkable" isn't "production-ready." Real growth (e.g. 50 → 5,000 users) exposes what AI scaffolding skips: missing DB indexes (full table scans on geo queries), in-memory session state that breaks behind a load balancer, WebSocket servers that can't handle hundreds of concurrent connections, and unoptimized asset delivery (no CDN/compression).

## Why it matters

Beyond scaling, AI-generated apps routinely ship without the privacy/security layer required for real users: no MFA or rate limiting, plaintext PII in the DB, missing row-level access control (any user can fetch `/rides/:id` by guessing a UUID), no audit logging, no GDPR deletion pipeline, hardcoded secrets, and no prompt-injection sanitization for LLM-backed features. These become compliance and security incidents, not just bugs.

## Gotchas

The experienced engineer's job shifted from writing boilerplate to making architectural decisions *before* they're expensive to undo: data model, multi-region readiness, auth architecture, and the privacy layer — all best decided on day one, not retrofitted.

## Resources

- [Full post → aneesas.hashnode.dev](https://aneesas.hashnode.dev/vibe-coded-to-production-where-ai-builders-hit-the-wall)
