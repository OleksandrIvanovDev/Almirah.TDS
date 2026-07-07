---
title: "FMEA-004: Failed Update Without Rollback"
---

# Status

|  | Date | Status |
|:---:|---|---|
| * | 03-07-2026 | Identified |

# Failure Mode

An interrupted software update leaves the installation in a state that neither starts nor accepts a new update.

# Effect

The installation is unusable until manually reinstalled; on remote sites this means a service visit.

# Cause

The updater replaces files in place; a power loss or lost connection mid-update leaves a mixed installation, and no previous version is kept to fall back to.

# Severity

10

# Occurrence

2

# Detection

8

# Mitigation

Not yet defined; the analysis of an A/B installation scheme with automatic fallback is scheduled for the next iteration.

# Monitoring

Support tickets mentioning a failed update are tagged and reviewed weekly.
