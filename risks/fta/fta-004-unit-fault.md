---
title: "FTA-004: Unit Conversion Fault in Reports"
---

# Status

|  | Date | Status |
|:---:|---|---|
|   | 06-07-2026 | Identified |
|   | 07-07-2026 | Analysed |
| * | 08-07-2026 | Mitigating |

# Top Event

Misleading report delivered to the user (TOP-2)

# Minimal Cut Set

{E7} — unit conversion fault; a first-order cut set, one basic event suffices

# Description

A value stored in one measurement unit is rendered in a report column labelled with another. As a first-order cut set under an OR gate, this single fault delivers the top event on its own, which is what drives the likelihood score.

# Severity

7

# Likelihood

5

# Mitigation

Carry the measurement unit with the value from the data model into every report column, so a unit can never be reattached by the presentation layer.

# Residual Severity

7

# Residual Likelihood

2

# Affected Documents

| # | Proposed Text | Req-ID |
|---|---|---|
| 1 | The software shall carry the measurement unit with the value from the data model into every report column. | >[REQ-023] |

# Monitoring

Report rendering tests compare the unit of every column against the data model on each release.
