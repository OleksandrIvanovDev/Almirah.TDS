# Almirah Testing Data Set

[![made-with-Markdown](https://img.shields.io/badge/Made%20with-Markdown-1f425f.svg)](http://commonmark.org)

This repository contains different set of documents in markdown format that were created to demostrate Almirah framework capabilities.

## Demo: project risk register (this branch)

This branch demonstrates how Almirah renders a register of project-level risks — everything that threatens the plan, the budget, or the team, as opposed to the product itself:

- `risks/project/` — **Project Risk Register** with five records (PRJR-001 … PRJR-005: key expertise loss, scope creep, schedule overrun, vendor delay, and a mid-release budget cut). Each record describes the risk, scores Probability and Impact on five-point scales in dedicated sections, states the response with its strategy spelled out (reduce, avoid, or accept), and links proposed requirements up with the ">" notation in an "Affected Documents" table. The `overview.md` file documents the scoring scales and the record lifecycle.
- `project.yml` — configures the register with a single RPN group, **Initial**, that multiplies Probability × Impact with the thresholds acceptable ≤ 6 and unacceptable ≥ 15, so the register colours each computed value green, amber, or red. Unlike the FMEA and FTA demo branches, there is no residual group — project risks here are tracked to closure through the status lifecycle instead of being re-scored.
- `specifications/req/req.md` — **Requirements Specification**, the input document declared in `project.yml`, holding the requirements the risk records link to.
- `specifications/arch/arch.md`, `decisions/adr-001-start-project-decision.md`, `tests/protocols/`, `tests/runs/` — a minimal surrounding example project (architecture, a decision record, test protocols and runs), so the register lives in a realistic document set.

Build the HTML with the almirah gem from the repository root (run "almirah please ." inside this folder) and open `build/index.html`. The rendered output shows the register table with the colour-coded RPN column computed from the record sections, the per-record pages with their status history, and the links between project risks and the requirements they affect.
