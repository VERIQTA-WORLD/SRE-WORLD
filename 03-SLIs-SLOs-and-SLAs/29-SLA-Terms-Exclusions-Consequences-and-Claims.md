# SLA Terms, Exclusions, Consequences, and Claims

> Evaluate whether an SLA can be measured, reported, disputed, and administered fairly under normal and failure conditions.

## Section Purpose

Evaluate whether an SLA can be measured, reported, disputed, and administered fairly under normal and failure conditions.

This section tests operational measurability. It does not draft binding legal language.

The practical output is a **SLA measurability and operations checklist**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain scope precision and its role in a defensible service-level system.
2. Explain calculation terms and its role in a defensible service-level system.
3. Explain planned maintenance and its role in a defensible service-level system.
4. Explain customer-caused events and its role in a defensible service-level system.
5. Explain third-party and force conditions and its role in a defensible service-level system.
6. Explain credits and remedies and its role in a defensible service-level system.
7. Explain claim process and its role in a defensible service-level system.
8. Explain measurement disputes and its role in a defensible service-level system.
9. Apply the section to an ambiguous production scenario.
10. Produce and defend the required artifact.

---

## Scope precision

List included and excluded functions, regions, plans, interfaces, maintenance states, and customer responsibilities.

---

## Calculation terms

Define numerator, denominator, availability interval, rounding, threshold, reporting source, and treatment of partial or unknown data.

---

## Planned maintenance

State notice, frequency, duration, window, approval, and whether emergency maintenance is different. Excessive exclusions destroy the meaning of the commitment.

---

## Customer-caused events

Define evidence required to attribute failure to customer configuration or action. Shared causation should not be decided unilaterally.

---

## Third-party and force conditions

Avoid broad language that excludes every dependency. Identify which dependencies are part of the provider commitment and which exceptional events follow another process.

---

## Credits and remedies

State eligibility, calculation, caps, application, and whether repeated breach triggers stronger action. A credit is not a reliability strategy.

---

## Claim process

Define notification, claim window, evidence, customer action, provider response, correction, and appeal. A claim process should not make legitimate remedies practically inaccessible.

---

## Measurement disputes

Preserve raw evidence, versioned definitions, independent sources, discrepancy thresholds, and final decision authority.

---

## Late data and correction

State whether reports are provisional, when periods close, and how material corrections affect claims or credits.

---

## Chronic breach

Define escalation, remediation plan, executive review, renegotiation, and possible termination when isolated remedies do not address repeated failure.

---

## Production Scenario

The provider excludes maintenance, dependency failure, attacks, customer behavior, emergency work, and missing telemetry. The advertised commitment has almost no measurable failure population.

### Analysis Questions

1. What user outcome or commitment is affected?
2. Which definition, target, source, or authority is missing?
3. What can be concluded from the current evidence?
4. What cannot be concluded?
5. Who owns the decision?
6. What correction is required?
7. What evidence will prove that the correction works?

---

## Practical Output: SLA measurability and operations checklist

Create a record containing:

- Scope:
- Calculation:
- Source:
- Exclusions:
- Maintenance:
- Customer duties:
- Dependencies:
- Reporting:
- Consequences:
- Claims:
- Disputes:
- Corrections:
- Chronic breach:

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

- Evaluate whether an SLA can be measured, reported, disputed, and administered fairly under normal and failure conditions.
- A target is defensible only when its measurement, rationale, owner, and decision are explicit.
- Strong governance preserves meaning as services and data change.
- Internal objectives and external commitments must be compared field by field.
- Contractual authority remains outside a technical team acting alone.

---

## Navigation

[Previous: Service Level Agreement Foundations](./28-Service-Level-Agreement-Foundations.md)

[Next: Aligning SLIs, SLOs, SLAs, and Internal Commitments](./30-Aligning-SLIs-SLOs-SLAs-and-Internal-Commitments.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

