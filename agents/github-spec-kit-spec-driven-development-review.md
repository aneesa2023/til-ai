# TIL: GitHub Spec Kit is a workflow harness, not a capability boost

**Category:** agents

---

## What I learned

Spec Kit is GitHub's open-source toolkit for Spec-Driven Development (SDD): a CLI that wraps your AI coding agent in five phases, each a slash command — `/speckit.constitution` (project principles), `/speckit.specify` (what/why, no tech), `/speckit.plan` (stack/architecture), `/speckit.tasks` (ordered breakdown with dependencies), and `/speckit.implement` (agent executes). Each phase writes a markdown file (`spec.md`, `plan.md`, `tasks.md`) that feeds the next and lives in git — reviewable and versionable, unlike buried chat history. After a week with Claude Code, the key realization: the agent does all the actual thinking. Spec Kit just structures *when* you ask for *what* — every artifact it produces, a well-formed prompt could have produced too. The structure is enforcement, not intelligence.

## Why it matters

For a disciplined solo developer who already plans before prompting, Spec Kit's ceremony costs more than it saves — Plan mode plus a sharp prompt covers the same ground. For teams, the artifacts are genuinely valuable: five engineers prompting freely produce five different shapes, while five engineers using Spec Kit produce comparable, reviewable specs, enabling intent review before code is written. The big unresolved problem is spec drift — nothing keeps `spec.md` in sync as code evolves, so on long-lived projects it quietly becomes another stale doc. Best fit: teams needing consistent specs across developers, compliance/audit trails, or orgs standardizing AI workflows across multiple agents. Skip it for small single-sentence features or fast-changing requirements. The lasting takeaway isn't the tool — it's the habit of writing the spec down before touching the agent.

## Resources

- [Full post → aneesas.hashnode.dev](https://aneesas.hashnode.dev/)
