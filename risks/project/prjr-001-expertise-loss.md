---
title: "PRJR-001: Key Expertise Loss"
---

# Status

|  | Date | Status |
|:---:|---|---|
|   | 01-07-2026 | Identified |
|   | 03-07-2026 | Analysed |
| * | 05-07-2026 | Mitigating |

# Description

The architecture and the deployment procedure live in the head of a single senior engineer. If that person leaves or becomes unavailable for an extended period, the team cannot release or change the core design without a long re-discovery phase.

# Probability

4

# Impact

4

# Response

Reduce, by spreading the knowledge: pair the senior engineer with a second developer on every architecture change, and require the deployment procedure to be executed once per release by somebody else, following the written runbook only.

# Affected Documents

| # | Proposed Text | Req-ID |
|---|---|---|
| 1 | The architecture decisions shall be recorded in the requirements set rather than held informally. | >[REQ-003] |

# Monitoring

Review at every release: the risk stays open until two people have independently performed a production deployment within the last quarter.
