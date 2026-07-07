---
title: "SECR-001: SQL Injection in Search"
---

# Status

|  | Date | Status |
|:---:|---|---|
|   | 01-07-2026 | Identified |
|   | 03-07-2026 | Analysed |
| * | 05-07-2026 | Mitigating |

# Threat

An unauthenticated attacker reads or alters the entire database through crafted search input.

# Vulnerability

The search endpoint concatenates the user-supplied term into the SQL statement instead of binding it as a parameter.

# CVSS Vector

CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H

# CVSS Score

9.8

# Mitigation

Replace the string concatenation with parameterised queries across the data layer and add a negative test suite of injection payloads to the build.

# Affected Documents

| # | Proposed Text | Req-ID |
|---|---|---|
| 1 | The software shall pass every user-supplied value to the database exclusively as a bound parameter of a prepared statement. | >[REQ-010] |
| 2 | The software shall not compose any SQL statement text by concatenating or interpolating user-supplied input. | >[REQ-011] |
| 3 | When user input contains SQL metacharacters or injection payloads, the software shall treat the input as literal data and shall return only the results matching that literal value, without raising a database error. | >[REQ-012] |

# Monitoring

The injection payload suite runs in every build; the database audit log is reviewed weekly until the risk closes.
