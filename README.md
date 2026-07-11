# Almirah Testing Data Set

[![made-with-Markdown](https://img.shields.io/badge/Made%20with-Markdown-1f425f.svg)](http://commonmark.org)

This repository contains different set of documents in markdown format that were created to demostrate Almirah framework capabilities.

## Demo: FMEA risk register with computed RPN (this branch)

This branch demonstrates how Almirah computes risk priority numbers over a Failure Mode and Effects Analysis (IEC 60812 style) register:

- `risks/fmea/` — **FMEA Worksheet** with five failure-mode records (FMEA-001 … FMEA-005, from silent data corruption to a log overflow filling the disk). Each record describes the failure mode, its effect and cause, scores Severity, Occurrence, and Detection on a ten-point scale in dedicated sections, states the mitigation, and links proposed requirements up with the ">" notation in an "Affected Documents" table. The `overview.md` file documents the scoring scales and the record lifecycle.
- `project.yml` — configures the register with two RPN groups: **Initial** multiplies Severity × Occurrence × Detection as first analysed, and **Residual** multiplies the Residual Severity/Occurrence/Detection sections scored after mitigation. Both groups use the thresholds acceptable ≤ 50 and unacceptable ≥ 200, so the register colours each computed value green, amber, or red.
- `specifications/req/req.md` — **Requirements Specification**, the input document declared in `project.yml`, holding the requirements the risk records link to.
- `specifications/arch/arch.md`, `decisions/adr-001-start-project-decision.md`, `tests/protocols/`, `tests/runs/` — a minimal surrounding example project (architecture, a decision record, test protocols and runs), so the register lives in a realistic document set.

Only three of the five records (FMEA-001, FMEA-003, FMEA-005) carry residual scores; FMEA-002 and FMEA-004 are not mitigated yet, so their Residual RPN cells deliberately stay blank — it shows how the register looks mid-mitigation.

Build the HTML with the almirah gem from the repository root (run "almirah please ." inside this folder) and open `build/index.html`. The rendered output shows the register table with the two colour-coded RPN columns computed from the record sections, the per-record pages, and the links between failure modes and the requirements they affect.
