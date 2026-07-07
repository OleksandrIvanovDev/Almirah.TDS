---
title: "SECR-004: Stack Traces in Error Pages"
---

# Status

|  | Date | Status |
|:---:|---|---|
|   | 02-07-2026 | Identified |
|   | 04-07-2026 | Analysed |
| * | 06-07-2026 | Accepted |

# Threat

An attacker maps the product's internals — framework versions, file paths, query shapes — from the diagnostic detail leaked in error responses.

# Vulnerability

Unhandled exceptions return the full stack trace to the client when the deployment flag is left in development mode.

# CVSS Vector

CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:L/I:N/A:N

# CVSS Score

5.3

# Mitigation

Accepted for this release with a compensating control: the deployment checklist verifies the production flag, and error responses are sampled in the smoke test. A framework-level generic error page is scheduled for the next release.

# Monitoring

The smoke test asserts that a forced error returns the generic page in every deployment.
