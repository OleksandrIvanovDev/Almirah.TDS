---
title: "FTA-005: Report Served From Stale Cache"
---

# Status

|  | Date | Status |
|:---:|---|---|
|   | 06-07-2026 | Identified |
| * | 07-07-2026 | Analysed |

# Top Event

Misleading report delivered to the user (TOP-2)

# Minimal Cut Set

{E8} — report served from stale cache; a first-order cut set, one basic event suffices

# Description

The report engine serves cached figures that no longer match the underlying records, so the user acts on numbers that were true yesterday. Analysis is complete; the mitigation has not been designed yet, so the residual scores are still blank.

# Severity

5

# Likelihood

4

# Mitigation

Proposed: invalidate cached report data when the underlying records change and stamp every report with the time of its data snapshot.

# Affected Documents

| # | Proposed Text | Req-ID |
|---|---|---|
| 1 | The software shall invalidate cached report data when the underlying records change and shall stamp every report with the time of its data snapshot. | >[REQ-024] |

# Monitoring

To be defined together with the mitigation.
