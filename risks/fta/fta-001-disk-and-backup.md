---
title: "FTA-001: Disk Failure With Silently Failing Backup"
---

# Status

|  | Date | Status |
|:---:|---|---|
|   | 06-07-2026 | Identified |
|   | 07-07-2026 | Analysed |
| * | 08-07-2026 | Mitigating |

# Top Event

Permanent loss of user data (TOP-1)

# Minimal Cut Set

{E1, E4} — disk hardware failure while the backup job has been failing silently

# Description

The primary disk fails, and only then does it surface that the scheduled backup job has been failing for weeks without anyone noticing. Both legs of the AND gate are true and the data is gone for good.

# Severity

10

# Likelihood

4

# Mitigation

Alert the user when a scheduled backup has not completed successfully within its configured period, so a failing backup leg is repaired long before a disk failure can coincide with it.

# Residual Severity

10

# Residual Likelihood

2

# Affected Documents

| # | Proposed Text | Req-ID |
|---|---|---|
| 1 | The software shall alert the user when a scheduled backup has not completed successfully within its configured period. | >[REQ-021] |

# Monitoring

Backup completion alerts are reviewed weekly; a silent gap longer than one period reopens the analysis.
