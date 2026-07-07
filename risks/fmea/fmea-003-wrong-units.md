---
title: "FMEA-003: Wrong Units in Report"
---

# Status

|  | Date | Status |
|:---:|---|---|
|   | 02-07-2026 | Identified |
|   | 04-07-2026 | Analysed |
| * | 06-07-2026 | Mitigating |

# Failure Mode

A generated report renders a value in different units than its column caption states.

# Effect

The reader takes a decision on a value that is wrong by a constant factor; the report looks perfectly plausible.

# Cause

Unit conversion happens in the presentation layer per column template, and a template can be edited without touching the conversion.

# Severity

8

# Occurrence

3

# Detection

4

# Mitigation

Attach the unit to the value in the data model so the caption and the number can never come from different places; add a report regression test comparing every column against a golden file.

# Residual Severity

8

# Residual Occurrence

1

# Residual Detection

2

# Affected Documents

| # | Proposed Text | Req-ID |
|---|---|---|
| 1 | The software shall carry the measurement unit with the value from the data model into every report column. | >[REQ-006] |

# Monitoring

The golden-file report comparison runs in every build.
