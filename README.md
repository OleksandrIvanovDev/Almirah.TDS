# Almirah Testing Data Set

[![made-with-Markdown](https://img.shields.io/badge/Made%20with-Markdown-1f425f.svg)](http://commonmark.org)

This repository contains different set of documents in markdown format that were created to demonstrate Almirah framework capabilities.

## Demo: fault tree analysis risk register (this branch)

This branch demonstrates how Almirah renders a risk register derived from a Fault Tree Analysis (IEC 61025 style), including images inside a risk registry:

- `risks/fta/overview.md` — **Fault Tree Analysis Register** overview: two fault trees drawn as SVG diagrams from the register's `img` folder (TOP-1 "permanent loss of user data" behind an AND gate, TOP-2 "misleading report delivered" behind an OR gate), a table mapping each minimal cut set to its register record, the scoring scales, and the record lifecycle.
- `risks/fta/fta-001 … fta-005` — one record per minimal cut set (from a disk failure coinciding with a silently failing backup down to a report served from a stale cache). Each record names its top event and cut set, scores Severity and Likelihood on a ten-point scale, states the mitigation, and links proposed requirements up with the ">" notation in an "Affected Documents" table. One further cut set is screened out as already acceptable and deliberately carries no record.
- `project.yml` — configures the register with two RPN groups: **Criticality** multiplies Severity × Likelihood as first analysed, and **Residual** multiplies the residual sections scored with the mitigation in place. Both groups use the thresholds acceptable ≤ 15 and unacceptable ≥ 35, so the register colours each computed value green, amber, or red.
- `specifications/req/req.md` — **Requirements Specification**, the input document declared in `project.yml`, holding the requirements the risk records link to.

Four of the five records carry residual scores; FTA-005 is not mitigated yet, so its Residual cell deliberately stays blank — it shows how the register looks mid-mitigation.

Build the HTML with the almirah gem from the repository root (run "almirah please ." inside this folder) and open `build/index.html`. The rendered output shows the fault tree diagrams copied into the build, the register table with the two colour-coded criticality columns, the per-record pages, and the links between cut-set records and the requirements they affect.
