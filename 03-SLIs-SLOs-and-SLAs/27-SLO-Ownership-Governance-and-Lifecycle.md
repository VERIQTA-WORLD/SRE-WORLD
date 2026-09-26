# SLO Ownership, Governance, and Lifecycle

> Keep objectives owned, accepted, versioned, reviewed, and connected to decisions throughout the service lifecycle.

## Section Purpose

Keep objectives owned, accepted, versioned, reviewed, and connected to decisions throughout the service lifecycle.

This section governs SLO artifacts. It does not repeat service ownership governance or create full error-budget enforcement policy.

The practical output is a **SLO governance and lifecycle policy**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain accountable owner and its role in a defensible service-level system.
2. Explain approval authority and its role in a defensible service-level system.
3. Explain provisional objectives and its role in a defensible service-level system.
4. Explain version control and its role in a defensible service-level system.
5. Explain review cadence and its role in a defensible service-level system.
6. Explain disputes and its role in a defensible service-level system.
7. Explain exceptions and its role in a defensible service-level system.
8. Explain lifecycle and its role in a defensible service-level system.
9. Apply the section to an ambiguous production scenario.
10. Produce and defend the required artifact.

---

## Accountable owner

The service owner remains accountable for the protected outcome. Supporting roles may own the SLI query, data source, product requirement, or risk decision.

---

## Approval authority

Define who approves a new target, material definition change, exception, and retirement. Technical teams must not silently create commercial commitments.

---

## Provisional objectives

New services can use provisional SLOs with explicit evidence gaps, limited duration, and a scheduled calibration review.

---

## Version control

Version changes to the SLI, target, window, population, or exclusions. Preserve effective dates and historical interpretation.

---

## Review cadence

Review on a schedule appropriate to criticality and when architecture, users, traffic, dependencies, data, or commitments change.

---

## Disputes

Resolve disputes through definitions, raw evidence, independent calculation, and named decision authority rather than competing dashboards.

---

## Exceptions

Record requirement, scope, reason, risk, compensating controls, approver, owner, expiry, and destination state.

---

## Lifecycle

Production candidates need approved measurement. Active services need operation and review. Deprecated services keep objectives while users remain. Retired objectives retain archived evidence.

---

## SLOs as code

Machine-readable definitions improve validation and change review. They do not replace user analysis, acceptance, governance, or evidence quality.

---

## Avoid governance theater

A complete template is not proof that a service level is useful. Test whether the owner can explain the objective and whether decisions actually use it.

---

## Governance Objects

Govern the objective, indicator, implementation, and evidence separately:

- SLO owner controls purpose, decision use, and lifecycle.
- SLI owner controls semantic definition.
- data owner controls source quality and lineage.
- implementation owner controls query or code fidelity.
- approval authority accepts the target and changes.

## Change Classes

| Change | Typical treatment |
| --- | --- |
| Editorial clarification | patch version and review |
| Query correction with no semantic change | implementation version, validation, annotated backfill |
| Population or success-rule change | new SLI version and SLO review |
| Target or window change | new SLO version and approval |
| Source replacement | parallel comparison and controlled cutover |
| Service or criticality change | full reassessment |

## Review Cadence and Triggers

Use scheduled review plus event triggers. Triggers include architecture changes, new consumer segments, major incidents, persistent overachievement or failure, contract changes, data-quality defects, and ownership transfer.

## Disputes

An SLO dispute should identify the contested field, competing evidence, temporary decision rule, authorized resolver, deadline, and historical impact. Do not resolve disagreement by silently editing the dashboard.

## Exceptions

Every exception records unmet requirement, reason, user and decision risk, temporary controls, approver, expiry, and closure evidence. Expired exceptions cannot renew automatically.

## SLOs as Code

Version-controlled definitions improve review and reproducibility. Code does not decide the correct CUJ, target, or authority. Require human approval for semantic changes and validate generated configuration against the approved record.

## Deprecation

An SLO can be retired only when the service, journey, or obligation no longer requires it or a successor fully replaces it. Preserve historical definitions, reports, effective dates, and links to the replacement.

## Production Scenario

A service changes its SLI query during a poor month without review, making historical performance look better. The query is technically valid and governance is broken.

### Analysis Questions

1. What user outcome or commitment is affected?
2. Which definition, target, source, or authority is missing?
3. What can be concluded from the current evidence?
4. What cannot be concluded?
5. Who owns the decision?
6. What correction is required?
7. What evidence will prove that the correction works?

---

## Practical Output: SLO governance and lifecycle policy

Create a record containing:

- Roles:
- Approval rights:
- Versioning:
- Review cadence:
- Triggers:
- Provisional SLOs:
- Exceptions:
- Disputes:
- Lifecycle transitions:
- Audit trail:
- Policy-as-code checks:

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

- Keep objectives owned, accepted, versioned, reviewed, and connected to decisions throughout the service lifecycle.
- A target is defensible only when its measurement, rationale, owner, and decision are explicit.
- Strong governance preserves meaning as services and data change.
- Internal objectives and external commitments must be compared field by field.
- Contractual authority remains outside a technical team acting alone.

---

## Navigation

[Previous: Deriving Error Budgets from SLOs](./26-Deriving-Error-Budgets-from-SLOs.md)

[Next: Service Level Agreement Foundations](./28-Service-Level-Agreement-Foundations.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)
