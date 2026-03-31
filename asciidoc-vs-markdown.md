# AsciiDoc vs Markdown

Markdown was designed for blog posts. AsciiDoc was designed for books.
That single distinction explains almost every difference between them —
why AsciiDoc exists, what it does better, and when it isn't worth the
switch.

## Origins

**Markdown** (John Gruber, 2004) — lightweight syntax for writing HTML.
The goal was readable plain text that converts cleanly to web pages. It
was never intended for complex documents.

**AsciiDoc** (Stuart Rackham, 2002) — syntax for technical documentation
targeting DocBook (a heavyweight XML format used for books and manuals).
Designed from the start for long-form, multi-file, multi-format output.

## What AsciiDoc Does That Markdown Can't

### Admonitions

First-class callout blocks, not hacked-together blockquotes:

```asciidoc
NOTE: This only applies to version 2.x and later.

WARNING: Deleting this directory is irreversible.

TIP: You can skip this step if using Docker.
```

Renders as visually distinct labelled blocks. In Markdown you simulate
this with `> **Note**:` and custom CSS.

### Includes (Transclusion)

Pull another file's content inline:

```asciidoc
= My Book

include::chapters/introduction.adoc[]

include::chapters/getting-started.adoc[]

include::chapters/reference.adoc[]
```

A 500-page book is one master file that assembles the pieces. Markdown
has no native equivalent.

### Code Callouts

Annotate specific lines in a code block with numbered markers:

```asciidoc
[source,python]
----
def connect(host, port):       <1>
    sock = socket.create(host) <2>
    sock.timeout = 30          <3>
    return sock
----
<1> Takes host and port as arguments
<2> Opens a raw socket connection
<3> Sets a 30-second timeout
```

The numbers appear inline in the rendered code and link to the
explanations below. Essential for technical writing. Markdown cannot
do this.

### CSV Tables

Tables can be written as raw CSV data instead of pipe syntax:

```asciidoc
[%header,format=csv]
|===
Name,Language,Stars
Asciidoctor,Ruby,4500
Spring Framework,Java,55000
Linux Kernel,C,180000
|===
```

More usefully, you can include an external CSV file:

```asciidoc
[%header,format=csv]
|===
include::data/projects.csv[]
|===
```

Maintain data in a spreadsheet, export as CSV, commit it. The
documentation renders it as a table automatically.

The equivalent Markdown pipe table must be written and maintained by
hand — every row, every time the data changes.

### Document Attributes

Variables for your document:

```asciidoc
:product-name: Acme Platform
:version: 3.2.1
:support-email: support@acme.com

Download {product-name} version {version} and contact
{support-email} for help.
```

Update the attribute once, every reference updates. Markdown has no
equivalent.

### Single Source, Multiple Outputs

Asciidoctor (the processor) produces HTML, PDF, EPUB, DocBook, and
manpages from a single `.adoc` source:

```bash
asciidoctor file.adoc          # → HTML
asciidoctor-pdf file.adoc      # → PDF
asciidoctor -b docbook file.adoc  # → DocBook XML
```

Markdown reliably produces HTML. Anything else requires external
tooling (Pandoc, etc.) that often loses fidelity.

## Syntax Comparison

| Feature | Markdown | AsciiDoc |
|---|---|---|
| H1 heading | `# Title` | `= Title` |
| H2 heading | `## Section` | `== Section` |
| Bold | `**bold**` | `*bold*` |
| Italic | `*italic*` | `_italic_` |
| Inline code | `` `code` `` | `` `code` `` |
| Code block | ` ```lang ` ... ` ``` ` | `[source,lang]` + `----` fence |
| Link | `[text](url)` | `link:url[text]` |
| Image | `![alt](url)` | `image::url[alt]` |
| Admonition | (none native) | `NOTE:`, `WARNING:`, etc. |
| Include file | (none native) | `include::file.adoc[]` |
| Cross-reference | (manual links) | `<<section-id>>` |

AsciiDoc is more verbose. The code block syntax alone is noticeably
heavier for quick writing.

## Tooling

### The Processor: Asciidoctor

AsciiDoc is the format. Asciidoctor is the dominant processor.

| Implementation | Language | Used For |
|---|---|---|
| Asciidoctor | Ruby | CLI, most complete feature set |
| Asciidoctor.js | JavaScript | Browser extensions, VS Code plugin |
| AsciidoctorJ | Java | JVM build systems |

```bash
gem install asciidoctor
asciidoctor document.adoc     # produces document.html
```

### VS Code

The **AsciiDoc extension by asciidoctor** provides syntax highlighting,
live preview, and document outline. It uses Asciidoctor.js internally —
no Ruby required for preview.

This is the right editor for AsciiDoc. The experience is comparable to
VS Code's Markdown preview.

### Browser Extension

**Asciidoctor.js Live Preview** (Chrome/Firefox) renders `.adoc` files
when opened locally in the browser. No install beyond the extension.
Good for casual checking.

### Obsidian

Obsidian is built around Markdown at its core. Community plugins exist
but AsciiDoc is a second-class citizen — no native rendering, no graph
view integration, no backlink support. If you use Obsidian, stay with
Markdown.

## The Fragmentation Problem Markdown Has

Markdown has no single canonical implementation. The original Gruber
spec was loose, CommonMark tried to standardize it but adoption is
incomplete, and GitHub Flavored Markdown, MultiMarkdown, and Pandoc
Markdown all differ in edge cases.

AsciiDoc has one spec and one dominant tool. Behavior is consistent.

## When Not to Use AsciiDoc

AsciiDoc has real costs. Stay with Markdown when:

- **The ecosystem matters** — GitHub, GitLab, npm, PyPI, Slack, Discord,
  Notion, every static site generator (Hugo, Jekyll, Astro) — all speak
  Markdown natively. AsciiDoc support is limited.

- **GitHub is your renderer** — GitHub renders `.adoc` files but
  `include::` doesn't work (security restriction), some attributes
  don't resolve, and multi-format output is off the table. You lose
  what makes AsciiDoc worth it.

- **You use Obsidian or a PKM tool** — All major personal knowledge
  management tools are Markdown-native. AsciiDoc is not a viable choice
  here.

- **Small documents** — For a README, short notes, quick reference:
  the verbosity of AsciiDoc is constant friction with no payoff.

- **Team writing** — Most people know Markdown. AsciiDoc has a learning
  curve and adds onboarding cost for every collaborator.

- **AI tooling** — Claude, Copilot, ChatGPT default to Markdown. Getting
  AsciiDoc output requires explicit prompting every time.

- **Copy-paste portability** — Markdown pastes into GitHub issues, PR
  descriptions, and Slack with reasonable rendering. AsciiDoc syntax
  in a comment just looks like noise.

## When AsciiDoc Is Worth It

- Long technical documentation split across many files (needs `include::`)
- Output must be both HTML and PDF from a single source
- Heavy use of admonitions and code callouts
- Documentation that references external data (CSV tables)
- Writing a technical book

Examples of projects using AsciiDoc: Spring Framework docs, Git
documentation (git-scm.com), various Red Hat and Apache project docs,
O'Reilly books written with Asciidoctor.

## Should You Learn It?

**Light familiarity: yes.** You will encounter AsciiDoc in technical
wikis and open source projects. Being able to read it and make edits
takes an afternoon.

**Deep commitment: only if you have a concrete need.** If you hit
Markdown's ceiling — needing includes, reliable PDF output, or heavy
admonition use — AsciiDoc is the right move and worth learning properly.
For a general personal wiki or notes workflow, Markdown with a good
renderer (Obsidian, MkDocs, Docusaurus) will cover almost everything.

The people who chose AsciiDoc for the wikis you encountered were not
wrong. They likely needed features Markdown couldn't provide. That
doesn't mean you need those features.
