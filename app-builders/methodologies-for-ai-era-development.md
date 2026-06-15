# TIL: Spec-driven, test-driven, and type-driven methods are the ones that survive AI coding

**Category:** app-builders

---

## What I learned

AI assistants are extraordinarily good at translating well-defined intent into code, but terrible at guessing intent from vague prompts. That makes the choice of development methodology a "contract with your AI collaborator," not just a team preference. Of the family of "X-driven development" approaches (code-first, TDD, BDD, spec-driven, DDD, type-driven, contract-driven, model/data/hypothesis-driven), the ones that win in the AI era are whichever produce the clearest, most testable, most unambiguous spec: **Spec-Driven Development** (write user stories/success criteria/edge cases before any code — tools like GitHub Spec Kit, Kiro, Tessl), **TDD** (failing tests as executable specs that agents iterate against in a red-green-refactor loop), **Type-Driven Development** (strict TypeScript/Rust types catch hallucinations before tests even run), and **Contract-Driven Development** (OpenAPI/Pact/GraphQL contracts stop AI-generated services from drifting apart).

## Why it matters

The pragmatic stack is to combine them: specs for planning, tests for verification, types for safety, contracts for boundaries, DDD for organizing code around the business domain. The cost of writing specs and tests has collapsed — an AI can draft a spec in 20 minutes — so the "too heavyweight" objection to these methodologies mostly disappears. Writing things down is what stops AI from being a footgun.

## Resources

- [Full post → aneesas.hashnode.dev](https://aneesas.hashnode.dev/the-many-ways-to-build-software-and-what-actually-works-in-the-ai-era)
