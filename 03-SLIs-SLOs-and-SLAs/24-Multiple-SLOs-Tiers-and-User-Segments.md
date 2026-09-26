# Multiple SLOs, Tiers, and User Segments

> Protect several important service behaviors and populations without creating an unmanageable collection of objectives.

## Section Purpose

Protect several important service behaviors and populations without creating an unmanageable collection of objectives.

This section structures objectives. It does not define commercial packaging or customer segmentation strategy.

The practical output is a **Multi-SLO service model**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain several dimensions and its role in a defensible service-level system.
2. Explain several journeys and its role in a defensible service-level system.
3. Explain read and write paths and its role in a defensible service-level system.
4. Explain critical and noncritical operations and its role in a defensible service-level system.
5. Explain service tiers and its role in a defensible service-level system.
6. Explain regional objectives and its role in a defensible service-level system.
7. Explain objective precedence and its role in a defensible service-level system.
8. Explain slo explosion and its role in a defensible service-level system.
9. Apply the section to an ambiguous production scenario.
10. Produce and defend the required artifact.

---

## Several dimensions

A service may need availability, latency, correctness, and freshness objectives because no single number protects the complete outcome.

---

## Several journeys

Login, purchase, refund, administration, and recovery may require separate objectives. Include only journeys important enough to drive decisions.

---

## Read and write paths

Reads and writes often have different failure modes, dependencies, and consequences. Combined results can hide unsafe write failure.

---

## Critical and noncritical operations

Do not let high-volume cosmetic actions dominate low-volume critical behavior. Use separate populations or override rules.

---

## Service tiers

Premium, standard, internal, and best-effort offerings may have different commitments. The architecture and operating model must support the distinction.

---

## Regional objectives

Regional objectives expose localized harm. A global objective still supports enterprise decisions, but it cannot replace regional visibility.

---

## Objective precedence

Correctness or safety may override availability. State which target takes priority when improving one dimension harms another.

---

## SLO explosion

Do not create an objective for every endpoint and metric. Consolidate around stable user outcomes and keep diagnostic measures outside the SLO set.

---

## Portfolio reporting

Report a small number of decision-relevant objectives with drill-down. Avoid one composite score that hides which promise failed.

---

## Retirement and consolidation

Remove objectives when journeys disappear, definitions merge, or no decision depends on them. Preserve history and approval.

---

## When Multiple SLOs Are Justified

Use more than one SLO when a service protects distinct outcomes, dimensions, or populations that require different decisions. Do not create a separate SLO for every metric or endpoint.

A useful test asks whether missing one objective while meeting the others would change the decision. If not, it may be diagnostic telemetry rather than a separate SLO.

## Tiered Services

Different tiers can have different objectives only when the product, architecture, measurement, and operating model can actually distinguish them. A premium promise is not credible when all tiers share the same capacity, dependencies, failure domains, and recovery path without prioritization.

## Multi-Threshold Latency

Two latency objectives can describe shape:

- 99 percent within 300 ms;
- 99.9 percent within 1 s.

The first protects common performance, the second constrains the tail. Both require named decisions. Avoid dozens of percentile objectives with no distinct use.

## Segment Reconciliation

For every mandatory segment, retain good and valid counts. Global totals should equal the sum of mutually exclusive segment totals. If users can belong to multiple segments, state the overlap and do not claim simple reconciliation.

## Objective Precedence

Define what happens when:

- global SLO passes but a protected region fails;
- availability passes but correctness fails;
- premium tier passes while standard tier fails;
- one objective lacks trustworthy data;
- two objectives recommend conflicting actions.

Safety, security, correctness, and contractual obligations may require explicit precedence rather than numerical averaging.

## Production Scenario

A service owns twenty-seven SLOs, each copied from a dashboard panel. Teams cannot explain which one should stop a release or protect a user.

### Analysis Questions

1. What user outcome or commitment is affected?
2. Which definition, target, source, or authority is missing?
3. What can be concluded from the current evidence?
4. What cannot be concluded?
5. Who owns the decision?
6. What correction is required?
7. What evidence will prove that the correction works?

---

## Practical Output: Multi-SLO service model

Create a record containing:

- Journeys:
- Dimensions:
- Populations:
- Targets:
- Precedence:
- Global and segment views:
- Decision per SLO:
- Owner:
- Consolidation opportunities:
- Retirement criteria:

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

- Protect several important service behaviors and populations without creating an unmanageable collection of objectives.
- A target is defensible only when its measurement, rationale, owner, and decision are explicit.
- Strong governance preserves meaning as services and data change.
- Internal objectives and external commitments must be compared field by field.
- Contractual authority remains outside a technical team acting alone.

---

## Navigation

[Previous: SLO Time Windows and Compliance Periods](./23-SLO-Time-Windows-and-Compliance-Periods.md)

[Next: Dependency, Composite, and End-to-End SLOs](./25-Dependency-Composite-and-End-to-End-SLOs.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)
