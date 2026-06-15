Process `reference_md/current_reference_md.md` and generate TIL entries for any new blogs found.

## Steps

1. **Read** `reference_md/current_reference_md.md` — this is the only input file
2. **Collect existing TILs** by reading all `.md` files in category folders (agents/, ai-tools/, app-builders/, flutter-mobile/, mcps/, platform-updates/) — extract the hashnode URL from each `## Resources` section to build an "already processed" set
3. **Parse** the current reference file — split on the `Blog N) Title-` pattern to extract individual blogs with their title, link, and content
4. **For each unprocessed blog** (URL not in the already-processed set):
   a. Read TEMPLATE.md for the output structure
   b. Determine the correct category from the blog content (one of: mcps, agents, app-builders, ai-tools, flutter-mobile, platform-updates)
   c. Generate a TIL markdown file:
      - Title: rewrite as a distilled "what I learned" insight, not just the blog title
      - What I learned: 2-4 dense sentences capturing the core insight
      - Why it matters: 1-2 sentences on practical implications
      - Notes/Code: only include if the blog has concrete snippets, commands, or configs worth noting
      - Resources: link to the original hashnode post
   d. Save to `<category>/<kebab-case-slug>.md`
5. **Update README.md** — append new entries to the index table, continuing the numbering sequence. Format: `| # | [Title](./category/filename.md) | category | [Post](hashnode-url) |`
6. **Report** what was generated and what was skipped (already existed)

## Important
- Match the tone and depth of existing TIL files in the repo — dense, practitioner-focused, no fluff
- Category must be one of: mcps, agents, app-builders, ai-tools, flutter-mobile, platform-updates
- Do NOT regenerate TILs that already exist (match by hashnode URL)
- Filenames should be kebab-case, descriptive, and concise
