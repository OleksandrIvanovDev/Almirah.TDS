---
title: "FMEA-002: UI Freeze Under Load"
---

# Status

|  | Date | Status |
|:---:|---|---|
|   | 02-07-2026 | Identified |
| * | 04-07-2026 | Analysed |

# Failure Mode

The user interface stops responding for tens of seconds when a large data set is opened.

# Effect

The user assumes a crash and force-quits the application, losing unsaved work and trust in the product.

# Cause

The data set is parsed on the interface thread; nothing yields control or reports progress while the parse runs.

# Severity

5

# Occurrence

5

# Detection

3

# Mitigation

Move the parse off the interface thread and show a cancellable progress indicator; analysis of the change is still in progress, so no residual scores are claimed yet.

# Monitoring

Interface responsiveness is measured in the nightly performance run against the large reference data set.
