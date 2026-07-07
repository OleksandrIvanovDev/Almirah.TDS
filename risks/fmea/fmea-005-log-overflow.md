---
title: "FMEA-005: Log Overflow Fills Disk"
---

# Status

|  | Date | Status |
|:---:|---|---|
|   | 01-07-2026 | Identified |
|   | 02-07-2026 | Analysed |
|   | 04-07-2026 | Mitigating |
| * | 07-07-2026 | Closed |

# Failure Mode

Diagnostic logging grows without bound and eventually fills the disk the application runs on.

# Effect

Unrelated features start failing on write errors long before anyone connects the failures to the log volume.

# Cause

Log rotation was configured by size per file but not capped in total, so long-running installations accumulated files indefinitely.

# Severity

4

# Occurrence

4

# Detection

2

# Mitigation

A total cap with rotation was configured and shipped; the oldest files are dropped first and a warning is logged when the cap is reached.

# Residual Severity

4

# Residual Occurrence

1

# Residual Detection

2

# Monitoring

None; the risk is closed. Reopen if the cap warning appears in support logs.
