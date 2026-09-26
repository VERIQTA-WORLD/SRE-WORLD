# Service Level Agreement Foundations

> Explain the engineering content of a Service Level Agreement and the organizational authority required before a service commitment is made.

## Section Purpose

Explain the engineering content of a Service Level Agreement and the organizational authority required before a service commitment is made.

This is engineering and operational guidance, not legal advice. Qualified legal, commercial, regulatory, and business owners control contract language.

The practical output is a **SLA requirements record**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain agreement, not metric and its role in a defensible service-level system.
2. Explain covered service and its role in a defensible service-level system.
3. Explain provider and customer and its role in a defensible service-level system.
4. Explain commitment and its role in a defensible service-level system.
5. Explain measurement authority and its role in a defensible service-level system.
6. Explain consequences and its role in a defensible service-level system.
7. Explain internal and external agreements and its role in a defensible service-level system.
8. Explain slo distinction and its role in a defensible service-level system.
9. Apply the section to an ambiguous production scenario.
10. Produce and defend the required artifact.

---

## Agreement, not metric

An SLA is an agreement between defined parties. It includes scope, commitments, measurement, responsibilities, reporting, and consequences.

---

## Covered service

Identify the exact service, features, interfaces, regions, users, plans, and dependencies covered. Product names alone are insufficient.

---

## Provider and customer

Name the parties and their responsibilities, including required configuration, notification, access, evidence, and claim behavior.

---

## Commitment

A commitment may address availability, response, completion, support, recovery, or another measurable behavior. Each term needs a precise calculation.

---

## Measurement authority

Define data source, calculation owner, period, timezone, delay, correction, and dispute process. Provider-only measurement may be challenged.

---

## Consequences

An SLA normally defines what happens when a commitment is missed, such as service credit, refund, remediation, escalation, or termination right.

---

## Internal and external agreements

Internal agreements coordinate business units or teams. External agreements create customer or partner obligations. Authority and consequences differ.

---

## SLO distinction

An internal SLO should normally provide operating headroom before an SLA threshold is breached. The definitions may differ and must be mapped.

---

## Support promise distinction

Response time from support is not the same as service availability or user-journey completion unless the agreement explicitly says so.

---

## Creation authority

SRE supplies measurement and feasibility evidence. Product, business, commercial, legal, risk, and regulatory owners decide the commitment.

---

## Production Scenario

A sales proposal promises 99.99 percent uptime before engineering has defined the service boundary, source, exclusions, or architecture required to support it.

### Analysis Questions

1. What user outcome or commitment is affected?
2. Which definition, target, source, or authority is missing?
3. What can be concluded from the current evidence?
4. What cannot be concluded?
5. Who owns the decision?
6. What correction is required?
7. What evidence will prove that the correction works?

---

## Practical Output: SLA requirements record

Create a record containing:

- Parties:
- Covered service:
- Commitments:
- Measurement:
- Period and timezone:
- Responsibilities:
- Reporting:
- Consequences:
- Dependencies:
- Internal SLO mapping:
- Approvers:
- Legal review:

Every target, exception, or commitment must identify its authority. Unknown evidence must remain visible with an owner and resolution date.

---

## Review Checklist

- [ ] The protected outcome or commitment is explicit.
- [ ] The SLI definition is versioned and reproducible.
- [ ] Target and time window are justified.
- [ ] Scope, segments, exclusions, and unknowns are visible.
- [ ] Measurement quality is sufficient for the decision.
- [ ] Dependencies and mismatched commitments are recorded.
- [ ] The accountable owner and approving authority are named.
- [ ] Review triggers, effective dates, and history are preserved.
- [ ] The artifact supports a real decision rather than reporting alone.

---

## Key Takeaways

- Explain the engineering content of a Service Level Agreement and the organizational authority required before a service commitment is made.
- A target is defensible only when its measurement, rationale, owner, and decision are explicit.
- Strong governance preserves meaning as services and data change.
- Internal objectives and external commitments must be compared field by field.
- Contractual authority remains outside a technical team acting alone.

---

## Navigation

[Previous: SLO Ownership, Governance, and Lifecycle](./27-SLO-Ownership-Governance-and-Lifecycle.md)

[Next: SLA Terms, Exclusions, Consequences, and Claims](./29-SLA-Terms-Exclusions-Consequences-and-Claims.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

