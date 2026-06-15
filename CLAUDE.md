# TIL-AI Project

Personal TIL (Today I Learned) repo by Aneesa Shaik. Each entry distills a blog post into a structured insight note.

## Blog: https://aneesas.hashnode.dev

## Project Structure

```
til-ai/
├── README.md                          # Index table of all TIL entries
├── TEMPLATE.md                        # TIL output format
├── reference_md/                      # All reference inputs live here
│   ├── current_reference_md.md        # THE active file to process (paste new blogs here)
│   └── reference_md_*.md              # Archive of previously processed batches
├── agents/                            # Category: AI agents
├── ai-tools/                          # Category: AI dev tools
├── app-builders/                      # Category: app builder platforms
├── flutter-mobile/                    # Category: Flutter/mobile dev
├── mcps/                              # Category: MCP servers/protocols
└── platform-updates/                  # Category: platform news
```

## Workflow

1. Paste new blog content into `reference_md/current_reference_md.md`
2. Run `/project:process-references`
3. TIL files generated, README updated, done

## Valid Categories

`mcps` · `agents` · `app-builders` · `ai-tools` · `flutter-mobile` · `platform-updates`

## Reference File Format

Each reference file contains multiple blogs delimited by:
```
Blog N) Title- <title>
Subtitle- <optional>
Link- <hashnode URL>
<full blog content>
```

## TIL Generation Rules

When processing reference content into TIL entries:

1. **Read** `reference_md/current_reference_md.md` — this is the only file to process
2. **Parse** each blog from the file (split on `Blog N)` pattern)
3. **Skip** blogs that already have a TIL file (check by matching blog URL in existing category files)
4. **For each new blog**, generate a TIL file following TEMPLATE.md structure:
   - `# TIL: <distilled insight title>` (not just the blog title — rewrite as what you learned)
   - `**Category:**` chosen from valid categories
   - `## What I learned` — 2-4 sentences, the core insight
   - `## Why it matters` — 1-2 sentences, practical implication
   - `## Notes / Code` — only if the blog has actionable snippets/commands (optional)
   - `## Resources` — link back to the hashnode post
5. **Save** to `<category>/<slug>.md` (kebab-case filename derived from title)
6. **Update README.md** index table — add new row with correct number, title, category, and blog post link

## Tone

Dense, practitioner-focused. No fluff. Write like explaining to a senior dev what you learned today.
