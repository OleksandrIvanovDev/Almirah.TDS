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

# Data Protection Requirements

The requirements in this section mitigate the minimal cut sets identified by the Fault Tree Analysis of the "Permanent loss of user data" top event.

[REQ-020] The software shall verify every completed backup by restoring it to a scratch area and comparing record checksums against the primary copy.

[REQ-021] The software shall alert the user when a scheduled backup has not completed successfully within its configured period.

[REQ-022] The software shall retain deleted records for at least 30 days and shall require an explicit second confirmation for any bulk deletion.

# Reporting Integrity Requirements

The requirements in this section mitigate the minimal cut sets identified by the Fault Tree Analysis of the "Misleading report delivered" top event.

[REQ-023] The software shall carry the measurement unit with the value from the data model into every report column.

[REQ-024] The software shall invalidate cached report data when the underlying records change and shall stamp every report with the time of its data snapshot.

# Document History

| Revision | Description of changes | Date |
|---|---|---|
| A | Initial version | 2026-07-09 |
