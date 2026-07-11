# Almirah Testing Data Set

[![made-with-Markdown](https://img.shields.io/badge/Made%20with-Markdown-1f425f.svg)](http://commonmark.org)

This repository contains different set of documents in markdown format that were created to demonstrate Almirah framework capabilities.

## Demo: security risk register with CVSS scoring (this branch)

This branch demonstrates how Almirah renders a risk register whose records are scored with CVSS instead of a computed risk priority number:

- `risks/security/` — **Security Risk Register** in the ISO 27005 shape: five records (SECR-001 … SECR-005, from an SQL injection down to clickjacking), each naming a threat, the vulnerability it exploits, the mitigation, a CVSS v3.1 vector with its precomputed base score, and an "Affected Documents" table that links the proposed security controls up to requirements with the ">" notation, e.g. ">[REQ-010]". The `overview.md` file describes the register's scoring and lifecycle conventions.
- `project.yml` — configures the register: the visible columns and a single-input RPN group named CVSS that surfaces the "CVSS Score" section unchanged (no product is computed), with the acceptable/unacceptable thresholds set to the CVSS severity boundaries 3.9 and 9.0.
- `specifications/req/req.md` — **Requirements Specification**, the input document declared in `project.yml`. Its "Security Requirements" section holds the controls (REQ-010 … REQ-012) that the SQL-injection record links to.
- `specifications/arch/arch.md`, `decisions/adr-001-start-project-decision.md`, `tests/protocols/`, `tests/runs/` — a minimal surrounding example project (architecture, a decision record, test protocols and runs), so the register lives in a realistic document set.

The five scores are chosen to span all three colour bands: 9.8 falls in the unacceptable (red) band, 8.1 / 7.5 / 5.3 in the caution (amber) band, and 3.1 in the acceptable (green) band.

Build the HTML with the almirah gem from the repository root (run "almirah please ." inside this folder) and open `build/index.html`. The rendered output shows the register table with the colour-coded CVSS column, the per-record pages, and the links between risk records and the requirements they affect.
