---
name: add-book-note
description: Add a book note to the site. Given an absolute path to a raw book-note markdown file, copy it into posts/, strip its "# Raw quotes" section, and link it from writing.md under "### Book notes" in alphabetical order (keeping "More on medium" last).
---

# Add book note

Input: an absolute path to a raw book-note markdown file (provided as the skill argument).

Do these steps in order. Do not skip verification.

## 1. Read the source file and derive the display title

- Read the file at the provided absolute path.
- Capture the basename of the file (e.g. `hell-yeah-or-no-derek-sivers.md`) — this becomes the destination filename.
- Derive the display title from the basename (NOT from the H1 — the first heading is typically `# TL;DR` or similar and is not useful).
  - Strip the `.md` extension.
  - Replace dashes with spaces.
  - Apply title case, preserving lowercase for common small words (a, an, and, or, the, of, in, on, for, to, vs).
  - The author's name is typically the last 1–2 tokens. Separate it from the book title with ` - ` (space, hyphen, space).
  - Example: `hell-yeah-or-no-derek-sivers.md` → `Hell Yeah or No - Derek Sivers`.
  - If the filename doesn't clearly contain an author name, just use the title-cased filename without the ` - ` separator. If unsure, ask the user.

## 2. Write the trimmed and re-leveled copy to posts/

- Destination path: `posts/<basename>` (relative to the repo root `/home/stephen/Code/personal/sjonany.github.io`).
- Apply these transformations to the source content, in this order:
  1. Remove the `# Raw quotes` heading line AND everything after it to end-of-file. If `# Raw quotes` does not appear, leave the content as-is and tell the user no "Raw quotes" section was found.
  2. Demote every markdown heading by two levels: `#` → `###`, `##` → `####`, `###` → `#####`, etc. Apply to all heading lines in the remaining content. Leave non-heading lines (including any line that just happens to start with `#` inside a code fence) untouched — only transform actual ATX heading lines outside of fenced code blocks.
  3. Prepend a new top-level title line at the very top of the file: `# <display title from step 1> [Book notes]`, followed by a blank line, then the rest of the transformed content.
- Do not reformat, re-wrap, or otherwise edit the prose.
- If the destination already exists, stop and ask the user before overwriting.

Use the Read tool on the source, then Write the transformed content to the destination. Do not use `cp` — we need the trim and re-level steps.

## 3. Add a link in writing.md

Edit `writing.md` (repo root). Under the `### Book notes` section, add a new bullet:

```
- [<display title from step 1>](posts/<basename>)
```

Ordering rules for the `### Book notes` list:

- Alphabetical by the displayed title (case-insensitive), EXCEPT
- The line `- More on [medium](https://medium.com/@sjonany)` always stays last.

Insert the new bullet at the correct alphabetical position among the other book-note bullets. Use the Edit tool with enough surrounding context to disambiguate the insertion point.

## 4. Report

Tell the user:
- The destination path written.
- The exact line inserted into writing.md and where (between which two existing bullets).
- Whether the "Raw quotes" section was present and stripped, or absent.
- How many headings were demoted.

Do not commit or stage changes — leave that to the user.
