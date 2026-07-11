# Almirah Testing Data Set

[![made-with-Markdown](https://img.shields.io/badge/Made%20with-Markdown-1f425f.svg)](http://commonmark.org)

This repository contains sets of documents in markdown format that demonstrate [Almirah](https://almirah.site) framework capabilities and serve as input data for manual testing of the Almirah gem.

Each branch is a self-contained Almirah project: check it out, run "almirah please ." inside the repository root, and open `build/index.html` to see the rendered result. The `main` branch intentionally holds no documents — all content lives on the branches listed below, and each branch's own README describes its content in detail.

## Overview

Demo branches, one Almirah capability each:

- [demo-specifications-one_di](#demo-specifications-one_di)
- [demo-decisions-aff_docs](#demo-decisions-aff_docs)
- [demo-risks-cvss](#demo-risks-cvss)
- [demo-risks-fmea](#demo-risks-fmea)
- [demo-risks-fta](#demo-risks-fta)
- [demo-risks-project](#demo-risks-project)

Manual-testing branches, referenced by test cases in the *Almirah.Doc* repository ("**Test Case** - **Testing Data Set Branch**" relationship):

- [tp-002](#tp-002)

### demo-specifications-one_di

A three-level specification chain (requirements → architecture → detailed design) for an imagined bedside patient monitor. Demonstrates uplinks, generated downlinks, and the traceability and coverage matrices, including how a deliberately uncovered architecture item looks.

### demo-decisions-aff_docs

An architecture decision record introducing full-text search into a records-management application, with SVG diagrams and an "Affected Documents" table linked to a requirements specification. Demonstrates how resolved and still-unresolved requirement references render in a decision record.

### demo-risks-cvss

A security risk register in the ISO 27005 shape whose five records carry CVSS v3.1 base scores spanning all three colour bands. Demonstrates a single-input RPN group that surfaces a precomputed score unchanged.

### demo-risks-fmea

A Failure Mode and Effects Analysis worksheet (IEC 60812 style) with Severity × Occurrence × Detection scoring. Demonstrates two computed RPN groups — Initial and Residual — with some records deliberately left unmitigated so their Residual cells stay blank.

### demo-risks-fta

A Fault Tree Analysis register (IEC 61025 style) with two fault trees drawn as SVG images and one record per minimal cut set. Demonstrates images inside a risk registry and the Criticality/Residual RPN groups computed from Severity × Likelihood.

### demo-risks-project

A register of project-level risks (expertise loss, scope creep, schedule overrun, vendor delay, budget cut) scored as Probability × Impact. Demonstrates the simplest register configuration with a single RPN group and no residual scoring.

### tp-002

Five small interlinked specifications and two test protocols used as the input data for the manual test case TP-002 in *Almirah.Doc*.
