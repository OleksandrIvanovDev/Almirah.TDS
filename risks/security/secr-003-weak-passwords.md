---
title: "SECR-003: Brute-Forceable Passwords"
---

# Status

|  | Date | Status |
|:---:|---|---|
| * | 03-07-2026 | Identified |

# Threat

An attacker gains a user account by trying common passwords against the login endpoint.

# Vulnerability

No password policy is enforced and the login endpoint neither rate-limits nor locks out repeated failures.

# CVSS Vector

CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:N/A:N

# CVSS Score

7.5

# Mitigation

Not yet defined; candidate controls are a minimum-length policy checked against a breached-password list, and exponential back-off on failed logins.

# Monitoring

Failed-login counts per account are graphed on the operations dashboard.
