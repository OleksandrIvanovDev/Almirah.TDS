---
title: Security Risk Register
---

# Security Risk Register

This registry collects the product's security risks in the ISO 27005 shape: each record names a threat, the vulnerability it exploits, and the mitigation that controls it.

## Scoring

Every record carries the CVSS v3.1 base score of its vulnerability, precomputed from the vector written in its CVSS Vector section. The register surfaces the score unchanged as the CVSS RPN column — a single-input group, no product is computed.

The colour bands follow the CVSS severity boundaries:

| Band | Score | Register colour |
|---|---|---|
| Low | 0.1 – 3.9 | acceptable (green) |
| Medium / High | 4.0 – 8.9 | caution (amber) |
| Critical | 9.0 – 10.0 | unacceptable (red) |

A critical score blocks the release until the mitigation lands; scores in the caution band are worked in severity order.

## Lifecycle

Records move through Identified, Analysed, Mitigating, Accepted, and Closed. Every record whose current status is not Closed counts as open in the registries summary.
