---
title: "FTA-003: Bulk Deletion Discovered After Retention"
---

# Status

|  | Date | Status |
|:---:|---|---|
|   | 06-07-2026 | Identified |
|   | 07-07-2026 | Analysed |
| * | 09-07-2026 | Accepted |

# Top Event

Permanent loss of user data (TOP-1)

# Minimal Cut Set

{E3, E6} — accidental bulk deletion noticed only after the retention window has expired

# Description

A user deletes a large set of records by mistake and only realises months later. If the retention window is shorter than the typical discovery time, the deleted records have already been purged and cannot be recovered.

# Severity

9

# Likelihood

2

# Mitigation

Retain deleted records for at least 30 days and require an explicit second confirmation for any bulk deletion, so the accidental deletion is both less likely and recoverable within the discovery time observed in support cases.

# Residual Severity

9

# Residual Likelihood

1

# Affected Documents

| # | Proposed Text | Req-ID |
|---|---|---|
| 1 | The software shall retain deleted records for at least 30 days and shall require an explicit second confirmation for any bulk deletion. | >[REQ-022] |

# Monitoring

Support cases involving recovery of deleted records are tagged; a case arriving after the retention window reopens the analysis.
