# Almirah Testing Data Set

[![made-with-Markdown](https://img.shields.io/badge/Made%20with-Markdown-1f425f.svg)](http://commonmark.org)

This repository contains different set of documents in markdown format that were created to demonstrate Almirah framework capabilities.

## Demo: decision record with affected documents (this branch)

This branch demonstrates how Almirah renders a decision record and links its "Affected Documents" table to a requirements specification, using an imagined records-management application that gains a full-text search feature:

- `decisions/adr-001-full-text-search.md` — **Architecture Decision Record** "Introduce Full-Text Search" with the full decision template: a status history table (Proposed → Accepted), context and decision sections illustrated by two SVG diagrams from the document's `img` folder, scope and out-of-scope tables, consequences, alternatives considered, and an "Affected Documents" table that states the proposed requirement texts and links them up with the ">" notation, e.g. ">[REQ-010]".
- `specifications/req/req.md` — **Requirements Specification** for the application, declared as the input in `project.yml`. It contains the existing requirements REQ-001 … REQ-012 as controlled paragraphs.

The first three rows of the "Affected Documents" table reference requirements that already exist in the specification, so their Req-IDs resolve into clickable links. The last two rows propose new requirements (REQ-030, REQ-031) that do not exist yet, so their Req-IDs deliberately stay unresolved — it shows how a decision record looks while the requirements work is still pending.

Build the HTML with the almirah gem from the repository root (run "almirah please ." inside this folder) and open `build/index.html`. The rendered output shows the decision record with its images copied into the build, the resolved and unresolved requirement references, and the downlinks generated on the requirements side back to the decision record.
