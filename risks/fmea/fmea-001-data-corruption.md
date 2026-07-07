---
title: "FMEA-001: Silent Data Corruption"
---

# Status

|  | Date | Status |
|:---:|---|---|
|   | 01-07-2026 | Identified |
|   | 03-07-2026 | Analysed |
| * | 05-07-2026 | Mitigating |

# Failure Mode

A record saved while the storage is under pressure is written incompletely, without any error being raised.

# Effect

The user's data is silently lost or altered; the corruption surfaces much later, when the record is next opened, and cannot be traced back to its cause.

# Cause

The save path acknowledges the write before the storage layer confirms it, and no checksum protects the record on disk.

# Severity

9

# Occurrence

4

# Detection

6

# Mitigation

Write through to the storage layer and acknowledge only on its confirmation; add a per-record checksum verified on every read, so a corrupted record is refused instead of shown.

# Residual Severity

9

# Residual Occurrence

2

# Residual Detection

2

# Affected Documents

| # | Proposed Text | Req-ID |
|---|---|---|
| 1 | The software shall acknowledge a save only after the storage layer confirms the write. | >[REQ-005] |

# Monitoring

Checksum verification failures are counted per release; any non-zero count reopens the analysis.
