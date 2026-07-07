---
title: "SECR-005: Clickjacking on Settings Page"
---

# Status

|  | Date | Status |
|:---:|---|---|
|   | 01-07-2026 | Identified |
|   | 02-07-2026 | Analysed |
|   | 03-07-2026 | Mitigating |
| * | 07-07-2026 | Closed |

# Threat

An attacker overlays the settings page in a hidden frame and tricks a logged-in user into clicking a destructive control.

# Vulnerability

The application served no frame-ancestors policy, so any site could embed it.

# CVSS Vector

CVSS:3.1/AV:N/AC:H/PR:N/UI:R/S:U/C:N/I:L/A:N

# CVSS Score

3.1

# Mitigation

Shipped: the frame-ancestors content-security policy denies all embedding, and the smoke test asserts the header on every page.

# Monitoring

None; the risk is closed. Reopen if an embedding use case ever requires relaxing the policy.
