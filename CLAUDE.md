# CLAUDE.md

## What This Repo Is

A personal knowledge repo. The workflow is:

1. Have a conversation with Claude (to learn something, brainstorm, draft
   a spec, etc.)
2. Persist the output — a summary, guide, or artifact — as a Markdown file
   in this repo
3. Return to it later and continue from where things left off

This makes it possible to pick up mid-thought across sessions, on any
device.

## How to Behave Here

- When starting a session, check if there's an existing document on the
  topic — read it first and treat it as the prior context.
- Output should be a document worth keeping: clear, accurate, and
  self-contained enough to be useful without the chat history.
- Prefer depth over breadth. A focused, well-explained document on one
  thing beats a shallow overview of many.
- Don't pad. No filler, no unnecessary caveats, no summaries of what was
  just said.

## Document Style

- Plain Markdown, readable in any viewer
- Use H1, H2, H3 headers so documents are scannable
- Use tables for comparisons, concrete examples to anchor abstract concepts
- Use mermaid diagrams to visually explain concepts
- Don't use `---` line breaks often; headers can naturally split sections
- Strict word wrap at 80 characters
- Each document should be understandable on its own — assume the reader
  has no memory of the original conversation

## Topics So Far

- **Healthcare coding** (`healthcare-coding-guide.md`) — ICD-10, CPT, DRG,
  HCPCS, USCLS, and Abu Dhabi / DoH-specific context (IR-DRG, Shafafiya,
  Mandatory Tariff)
- **AsciiDoc vs Markdown** (`asciidoc-vs-markdown.md`) — why AsciiDoc
  exists, its strengths (admonitions, includes, callouts, CSV tables,
  multi-format output), Asciidoctor tooling, and when to stay with
  Markdown
- **Changelog publishing workflow** (`changelog-publishing-workflow.md`)
  — publishing Markdown changelogs to Outlook email, PDF, and website;
  Pandoc + Juice pipeline, CSS inlining, Quarto as future upgrade path
