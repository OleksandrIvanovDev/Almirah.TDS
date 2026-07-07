---
title: Requirements Specification
author: put your name here
---

# Overview

This is an example of software requirements specification.

# Requirements

This is a regular paragraph in the document.

[REQ-001] This is a first requirement (controlled paragraph with ID equal to "REQ-001").

[REQ-002] This is a second requirement.

# Security Requirements

Controls in this section trace back to the records of the security risk register that motivate them.

[REQ-010] The software shall pass every user-supplied value to the database exclusively as a bound parameter of a prepared statement.

[REQ-011] The software shall not compose any SQL statement text by concatenating or interpolating user-supplied input.

>Note: verified by code review of the data layer rather than black-box testing.

[REQ-012] When user input contains SQL metacharacters or injection payloads, the software shall treat the input as literal data and shall return only the results matching that literal value, without raising a database error.

# Document Histrory

| Revision | Description of changes | Date |
|---|---|---|
| A | Initial version | 2026-07-07 |

