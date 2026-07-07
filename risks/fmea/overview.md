---
title: FMEA Worksheet
---

# FMEA Worksheet

This registry is a Failure Mode and Effects Analysis (IEC 60812 style) of the product: each record is one failure mode, scored for how bad it is, how often it happens, and how likely it is to escape detection before it reaches the user.

## Scales

Each factor is written into its own section of the record on a ten-point scale:

| Value | Severity | Occurrence | Detection |
|---|---|---|---|
| 1 | No noticeable effect | Practically never | Caught immediately, always |
| 4 | Degraded performance | Occasional | Usually caught by tests |
| 7 | Loss of function | Frequent | Rarely caught before release |
| 10 | Safety or data loss | Persistent | No detection in place |

The Initial RPN is Severity times Occurrence times Detection, computed over the factors as first analysed. The Residual RPN uses the Residual Severity, Residual Occurrence, and Residual Detection sections, scored after the mitigation is in place; a record without residual scores has not been mitigated yet and its Residual cell stays blank.

An RPN of 50 or below is acceptable, 200 or above is unacceptable and blocks the release until mitigated; the band between is tolerable while a mitigation is in progress.

## Lifecycle

Records move through Identified, Analysed, Mitigating, Accepted, and Closed. Every record whose current status is not Closed counts as open in the registries summary.
