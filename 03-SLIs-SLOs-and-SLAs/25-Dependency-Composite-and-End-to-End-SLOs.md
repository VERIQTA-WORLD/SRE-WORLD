# Dependency, Composite, and End-to-End SLOs

> Connect provider objectives, consumer reliability, and complete Critical User Journeys without confusing local success with end-to-end success.

## Section Purpose

Connect provider objectives, consumer reliability, and complete Critical User Journeys without confusing local success with end-to-end success.

Dependency ownership was established in Service Ownership. This section defines service-level relationships and calculations.

The practical output is a **Dependency and end-to-end SLO map**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain provider and consumer objectives and its role in a defensible service-level system.
2. Explain serial dependencies and its role in a defensible service-level system.
3. Explain parallel dependencies and its role in a defensible service-level system.
4. Explain shared dependencies and its role in a defensible service-level system.
5. Explain third-party services and its role in a defensible service-level system.
6. Explain composite indicators and its role in a defensible service-level system.
7. Explain end-to-end objective and its role in a defensible service-level system.
8. Explain budget allocation and its role in a defensible service-level system.
9. Apply the section to an ambiguous production scenario.
10. Produce and defend the required artifact.

---

## Provider and consumer objectives

A provider measures its offered boundary. The consumer owns correct integration, fallback, and the end-to-end outcome.

---

## Serial dependencies

When every serial dependency must succeed, end-to-end reliability is constrained by the chain. Independence assumptions rarely hold perfectly.

---

## Parallel dependencies

Parallel calls may require all, any, quorum, or a subset to succeed. Define the composition rule from the user outcome.

---

## Shared dependencies

A shared identity, DNS, certificate, or control-plane service can create correlated failure across many journeys.

---

## Third-party services

A vendor SLA does not guarantee consumer SLO attainment. Measurement sources, exclusions, windows, and remedies may differ.

---

## Composite indicators

A composite SLI combines several required conditions. Keep the components visible so the result remains diagnosable.

---

## End-to-end objective

Measure final journey success across services. Component SLOs support ownership and engineering but cannot substitute for the journey SLO.

---

## Budget allocation

Teams may allocate reliability expectations to dependencies, but allocation is a design assumption, not proof that the complete service will meet its target.

---

## Double counting

One underlying failure can appear in several component indicators. End-to-end impact should not be multiplied when calculating affected user journeys.

---

## Outside control

Record escalation, alternatives, risk acceptance, and evidence when the owner cannot directly change a dependency.

---

## Local Objectives Do Not Guarantee the Journey

Every service in a chain can meet its local SLO while the complete journey fails. Boundaries, correlated failures, integration defects, retries, and client behavior create end-to-end outcomes that local measures cannot prove.

## Serial Dependencies

If independent components must all succeed and have success probabilities $a_1...a_n$, the approximate joint success is:

$$
A_{serial} = \prod_{i=1}^{n} a_i
$$

Three independent 99.9 percent components yield approximately:

$$
0.999^3 \approx 99.7003\%
$$

Independence is often false, so use this as a planning model, not proof.

## Parallel and Redundant Paths

For two independent redundant paths that can each satisfy the request, joint unavailability is the product of both failure probabilities. Shared control planes, credentials, networks, and data stores can invalidate the independence assumption.

## Dependency Budget Allocation

An end-to-end objective can inform internal dependency expectations, but budgets cannot always be divided mechanically. A dependency may be called several times per journey, failures may be retried, and one shared dependency may affect many services. Model call patterns and user impact.

## Third Parties

A provider's SLA does not become the consumer's SLO. Differences may include edge versus user measurement, calendar versus rolling windows, exclusions, regions, and claim thresholds. Design fallback, caching, graceful degradation, multi-provider capability, or an honest lower end-to-end target.

## Composite Measures

Avoid averaging local SLO attainment. Define the end-to-end event directly when possible. Use dependency measures for diagnosis, capacity planning, and escalation.

## Correlation Test

Record shared failure domains and test loss of identity, DNS, network, control plane, configuration, region, and observability. Redundancy that shares these dependencies may not improve journey reliability.

## Production Scenario

Every component meets its local SLO, but small independent failure rates across five mandatory steps cause the purchase journey to miss its end-to-end target.

### Analysis Questions

1. What user outcome or commitment is affected?
2. Which definition, target, source, or authority is missing?
3. What can be concluded from the current evidence?
4. What cannot be concluded?
5. Who owns the decision?
6. What correction is required?
7. What evidence will prove that the correction works?

---

## Practical Output: Dependency and end-to-end SLO map

Create a record containing:

- Journey:
- Components:
- Dependency type:
- Provider SLO:
- Consumer assumption:
- Composition rule:
- Correlated risks:
- Fallback:
- End-to-end SLI:
- Owners:
- Escalation:

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

- Connect provider objectives, consumer reliability, and complete Critical User Journeys without confusing local success with end-to-end success.
- A target is defensible only when its measurement, rationale, owner, and decision are explicit.
- Strong governance preserves meaning as services and data change.
- Internal objectives and external commitments must be compared field by field.
- Contractual authority remains outside a technical team acting alone.

---

## Navigation

[Previous: Multiple SLOs, Tiers, and User Segments](./24-Multiple-SLOs-Tiers-and-User-Segments.md)

[Next: Deriving Error Budgets from SLOs](./26-Deriving-Error-Budgets-from-SLOs.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)
