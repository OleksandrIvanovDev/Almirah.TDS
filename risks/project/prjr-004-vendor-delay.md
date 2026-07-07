---
title: "PRJR-004: External Vendor Delay"
---

# Status

|  | Date | Status |
|:---:|---|---|
|   | 02-07-2026 | Identified |
|   | 04-07-2026 | Analysed |
| * | 06-07-2026 | Accepted |

# Description

The reporting module depends on a data export API promised by an external vendor for the middle of the release cycle. The vendor has slipped similar commitments before, and there is no contractual penalty for late delivery.

# Probability

2

# Impact

4

# Response

Accept, with a fallback: the integration is scheduled last in the release, and a file-based import path covering the demo scenarios is kept working so a vendor slip degrades the feature instead of blocking the release.

# Affected Documents

| # | Proposed Text | Req-ID |
|---|---|---|
| 1 | The import interface shall remain operable from local files independently of the vendor API. | >[REQ-004] |

# Monitoring

Check the vendor's staging endpoint at every iteration review; a second missed checkpoint reopens the risk as Mitigating.
