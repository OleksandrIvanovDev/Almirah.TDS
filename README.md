# Almirah Testing Data Set

[![made-with-Markdown](https://img.shields.io/badge/Made%20with-Markdown-1f425f.svg)](http://commonmark.org)

This repository contains different set of documents in markdown format that were created to accelerate testing of the Almirah gem.
There is a "**Test Case** - **Testing Data Set Branch**" relationship between *Almirah.Doc* and *Almirah.TDS* repositories.

## Demo: specification traceability chain (this branch)

This branch demonstrates how Almirah handles traceability across a three-level specification chain for an imagined medical device — a bedside patient monitor that measures heart rate and SpO2, alarms on limit violations, and forwards data to a central nurse station:

- `specifications/srs/srs.md` — **Software Requirements Specification**, ten software requirements (SRS-001 … SRS-010). The top-level document declared as the input in `project.yml`.
- `specifications/sad/sad.md` — **Software Architecture Document**: architecture principles, a system overview and a software architecture diagram (SVG files in the document's `img` folder), and six modules described on the high level. Every architecture item links up to the requirements it realizes with the ">" notation, e.g. ">[SRS-001]".
- `specifications/sdd/sdd.md` — **Software Detailed Design**: the software units of each module, each linking up to its architecture item, e.g. ">[SAD-010]".

Build the HTML with the almirah gem from the repository root (run "almirah please ." inside this folder) and open `build/index.html`. The rendered output shows the uplinks as clickable references, the downlinks generated automatically in the opposite direction, and the traceability and coverage matrices for the srs-sad and sad-sdd document pairs. Note that the architecture principle SAD-002 deliberately has no uplink and no covering design unit — it shows how partially covered items look in the coverage view.
