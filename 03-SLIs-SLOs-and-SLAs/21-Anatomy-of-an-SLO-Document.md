# Anatomy of an SLO Document

> Define the complete record required to operate, review, and defend a Service Level Objective.

## Section Purpose

Define the complete record required to operate, review, and defend a Service Level Objective.

This section assembles an SLO document. Target selection, windows, multiple objectives, dependencies, budgets, and governance are expanded in Sections 22 through 27.

The practical output is a **Complete SLO document**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain service context and its role in a defensible service-level system.
2. Explain sli reference and its role in a defensible service-level system.
3. Explain objective statement and its role in a defensible service-level system.
4. Explain scope and segments and its role in a defensible service-level system.
5. Explain exclusions and its role in a defensible service-level system.
6. Explain rationale and its role in a defensible service-level system.
7. Explain error-budget derivation and its role in a defensible service-level system.
8. Explain decision use and its role in a defensible service-level system.
9. Apply the section to an ambiguous production scenario.
10. Produce and defend the required artifact.

---

## Service context

Identify the service, stable identifier, accountable team, criticality, lifecycle state, users, and protected Critical User Journey.

---

## SLI reference

Link to an approved, versioned SLI specification. Do not copy an ungoverned query into the SLO and allow the definitions to drift.

---

## Objective statement

State the target, direction, population, and compliance period in one testable sentence, such as at least 99.9 percent of valid checkout attempts complete successfully over a rolling 28-day period.

---

## Scope and segments

Name included regions, interfaces, user classes, and service tiers. Record segments with independent objectives or override rules.

---

## Exclusions

Reference the eligibility and exclusion policy. Explain why each exclusion is legitimate and how its volume is monitored.

---

## Rationale

Document user expectations, business consequences, historical evidence, architectural capability, dependency limits, cost, and risk acceptance.

---

## Error-budget derivation

Show the permitted bad-event or bad-time allowance implied by the target. Keep policy decisions separate from the arithmetic.

---

## Decision use

State which actions the objective informs, who has authority, and what evidence is required. An SLO without a decision becomes reporting theater.

---

## Limitations and dependencies

Record measurement uncertainty, blind spots, third-party reliance, and assumptions that could invalidate the objective.

---

## Approval and lifecycle

Include owner acceptance, approvers, effective date, version, review cadence, triggers, related SLA, and retirement conditions.

---

## Production Scenario

A dashboard contains a target line but no population, window, owner, rationale, or decision rule. It visualizes a preference rather than documenting an SLO.

### Analysis Questions

1. What user outcome or commitment is affected?
2. Which definition, target, source, or authority is missing?
3. What can be concluded from the current evidence?
4. What cannot be concluded?
5. Who owns the decision?
6. What correction is required?
7. What evidence will prove that the correction works?

---

## Practical Output: Complete SLO document

Create a record containing:

- Service context:
- Journey and users:
- SLI reference and version:
- Objective statement:
- Target and window:
- Segments:
- Exclusions:
- Rationale:
- Error budget:
- Decision use:
- Dependencies and limitations:
- Approval and review:

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

- Define the complete record required to operate, review, and defend a Service Level Objective.
- A target is defensible only when its measurement, rationale, owner, and decision are explicit.
- Strong governance preserves meaning as services and data change.
- Internal objectives and external commitments must be compared field by field.
- Contractual authority remains outside a technical team acting alone.

---

## Navigation

[Previous: SLI Data Quality and Measurement Failure](./20-SLI-Data-Quality-and-Measurement-Failure.md)

[Next: Setting Defensible SLO Targets](./22-Setting-Defensible-SLO-Targets.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

