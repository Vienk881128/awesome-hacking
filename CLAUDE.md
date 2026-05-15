# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

A curated "awesome list" of hacking resources, in the style of sindresorhus/awesome. It is **content-only**: no source code, no build system, no tests, no linter, no CI. The deliverable is plain Markdown.

The repository contains only:
- `README.md` — the entire curated list (the substantive content)
- `books.md` — a short companion list of books
- `LICENSE` — MIT

Almost every task here is "add / move / fix one or more entries in `README.md`" via PR. Do not invent build steps, scaffolding, package files, or directories — there is no project to build.

## Content structure (README.md)

`README.md` is organized as a two-level hierarchy:

- **Top-level `#` sections** (categories): `System`, `Reverse Engineering`, `Web`, `Network`, `Forensic`, `Cryptography`, `Wargame`, `CTF`, `OS`, `Post exploitation`, `ETC`.
- **`##` subsections** that recur across categories: typically `Tutorials`, `Tools`, `General`. Some categories use deeper `###` groupings (e.g. Reverse Engineering → Tools → `Disassemblers and debuggers`, `Decompilers`, `Deobfuscators`, `Hex editors`, …).

A hand-maintained Table of Contents lives at the top of `README.md` inside `<!-- MarkdownTOC depth=4 -->` … `<!-- /MarkdownTOC -->`. Anchor links use GitHub's slugging plus numeric suffixes for repeated headings (e.g. `#tutorials`, `#tutorials-1`, `#tools-2`). When you add, rename, remove, or reorder a section, you must update the TOC entries and re-number the suffixes consistently — the suffix order is determined by the order headings appear in the document, not by category.

## Entry format conventions

Follow the existing style exactly when adding entries — consistency is the main thing reviewers check.

Tool/resource bullet:
```
 * [Name](https://example.com) - Short description ending without a trailing period in most cases (match neighbors).
```

Docker image bullet (only under `System` → `Docker Images for Penetration Testing & Security`):
```
 * `docker pull org/image` - [Display name](https://link/to/project)
```

Nested annotations (used sparingly, e.g. for Roppers entries) are indented four spaces under the parent bullet and start with `* `.

Notes:
- Bullets use a single leading space then `*` (` * `), not `-`. Some sub-lists use `*` with no leading space — match the surrounding block.
- Place new entries inside the most specific existing subsection. Only create a new subsection if none fits, and update the TOC when you do.
- Order within a list is **not** strictly alphabetical in this repo; appending to the end of the relevant list matches the historical pattern unless a clearer grouping exists nearby.

## Workflow

- There is nothing to run locally. "Testing" a change means: render the Markdown (e.g. GitHub preview) and confirm the TOC links jump to the right headings, every new external link resolves, and formatting matches surrounding entries.
- Contributions land via pull request to `master`. Commit messages in history are short and descriptive (e.g. `Add PETEP`, `Added CAINE as a Forensic tool`, `Update README.md`) — match that tone.
- This repo's designated development branch for Claude Code work is `claude/add-claude-documentation-FxgXS` (see the harness instructions); push there, not to `master`.

## Things not to do

- Don't add a `package.json`, linter config, GitHub Actions workflow, or any tooling unless explicitly asked — this repo deliberately has none.
- Don't auto-reformat `README.md` wholesale (e.g. running a Markdown formatter). It will churn unrelated lines and break the manually-curated TOC anchors.
- Don't delete or "fix" links that look dead without confirming — many entries point to long-lived resources whose hosts occasionally hiccup.
