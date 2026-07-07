---
title: "SECR-002: Vulnerable Third-Party Dependencies"
---

# Status

|  | Date | Status |
|:---:|---|---|
|   | 02-07-2026 | Identified |
| * | 04-07-2026 | Analysed |

# Threat

An attacker exploits a publicly known vulnerability in one of the product's outdated third-party libraries.

# Vulnerability

Dependencies are pinned once per release and never rescanned; the current lock file contains libraries with published advisories.

# CVSS Vector

CVSS:3.1/AV:N/AC:H/PR:N/UI:N/S:U/C:H/I:H/A:H

# CVSS Score

8.1

# Mitigation

Add a dependency audit to the build that fails on any advisory at High or above, and schedule a monthly update window for the rest.

# Monitoring

The audit report is attached to every release; advisories arriving between releases are triaged within one working day.
