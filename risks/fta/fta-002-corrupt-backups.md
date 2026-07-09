---
title: "FTA-002: Corruption Replicated Into Untested Backups"
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

{E2, E5} — silent write corruption replicated into backups whose restore was never tested

# Description

A record is corrupted on write without any error and the corruption is faithfully replicated into every backup generation. Because a restore has never been exercised, the backups' unusability is discovered only at the moment they are needed.

# Severity

10

# Likelihood

3

# Mitigation

Verify every completed backup by restoring it to a scratch area and comparing record checksums against the primary copy, so corrupted backups are detected at backup time, not at restore time.

# Residual Severity

10

# Residual Likelihood

1

# Affected Documents

| # | Proposed Text | Req-ID |
|---|---|---|
| 1 | The software shall verify every completed backup by restoring it to a scratch area and comparing record checksums against the primary copy. | >[REQ-020] |

# Monitoring

Restore-verification failures are counted per month; any non-zero count reopens the analysis.
