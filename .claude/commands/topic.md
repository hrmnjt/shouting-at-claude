Start a focused knowledge session on the topic: $ARGUMENTS

## Your role

You are helping the user learn, brainstorm, or draft something on this topic.
The goal is a document worth keeping — not a chat transcript.

## Steps

1. **Check for an existing document** — search the repo for any `.md` file
   covering this topic. If found, read it and treat it as prior context.
   Tell the user what you found.

2. **Discuss** — engage the user on the topic. Ask clarifying questions,
   go deep, surface what they actually want to understand or capture.

3. **Write or update the file** — when the user signals they're done (or
   you've reached a natural stopping point), write or update the relevant
   `.md` file following the style rules in CLAUDE.md:
   - Plain Markdown, H1/H2/H3 headers
   - Tables for comparisons, concrete examples for abstract concepts
   - Mermaid diagrams where visuals help
   - 80-character word wrap
   - Self-contained — no assumed memory of this conversation
   - No padding, no filler

4. **Update CLAUDE.md** — add or update the entry in the "Topics So Far"
   section to reference the new or updated file.

## File naming

Use a short, lowercase, hyphenated name that reflects the topic.
Example: `rust-ownership.md`, `system-design-caching.md`.
If an existing file already covers this topic, update it in place.
