# Setting Defensible SLO Targets

> Choose reliability targets from user need, evidence, risk, architecture, and cost rather than copying arbitrary industry percentages.

## Section Purpose

Choose reliability targets from user need, evidence, risk, architecture, and cost rather than copying arbitrary industry percentages.

This section selects targets. It does not implement architecture or negotiate legal contract language.

The practical output is a **SLO target decision record**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain user expectation and its role in a defensible service-level system.
2. Explain business consequence and its role in a defensible service-level system.
3. Explain historical performance and its role in a defensible service-level system.
4. Explain architectural capability and its role in a defensible service-level system.
5. Explain dependency limits and its role in a defensible service-level system.
6. Explain cost and tradeoffs and its role in a defensible service-level system.
7. Explain provisional targets and its role in a defensible service-level system.
8. Explain avoid 100 percent and its role in a defensible service-level system.
9. Apply the section to an ambiguous production scenario.
10. Produce and defend the required artifact.

---

## User expectation

Determine the level at which users can complete the journey safely and usefully. Perceived reliability may differ by frequency and consequence.

---

## Business consequence

Connect misses to revenue, trust, safety, operations, compliance, and irreversible harm without pretending every consequence can be monetized.

---

## Historical performance

Use history to understand the current system, variation, incidents, and measurement quality. History is evidence, not automatic justification for the future target.

---

## Architectural capability

A target must be supportable by dependencies, failure domains, change safety, recovery, and staffing. An impossible target is not ambitious governance.

---

## Dependency limits

A consumer objective stronger than an unavoidable dependency requires redundancy, isolation, fallback, or a clear assumption. Arithmetic alone cannot create headroom.

---

## Cost and tradeoffs

Higher reliability can require duplicated systems, reduced change, more staffing, stronger controls, and greater complexity. Make the tradeoff explicit.

---

## Provisional targets

When evidence is weak, begin with a time-limited target, measurement-improvement plan, and review date rather than false precision.

---

## Avoid 100 percent

A 100 percent objective leaves no tolerance for change, measurement error, or known failure. Use it only when the defined population and consequence genuinely demand it and authorized owners accept the implications.

---

## Avoid arbitrary nines

99.9 percent is not a universal default. The same percentage has different meaning by volume, window, clustering, and journey consequence.

---

## Negotiation and authority

Service, product, SRE, business, risk, and commercial owners may contribute. Record who approves the target and who accepts residual risk.

---

## Target Selection Is a Risk Decision

An SLO target expresses how much measured failure the organization is prepared to tolerate for a defined outcome and period. It should not be copied from common “nines,” current performance, a competitor, or an SLA.

## Evidence Set

Use:

- user research and support evidence;
- severity and timing of harm;
- service criticality;
- historical SLI distribution and incidents;
- architecture and dependency limits;
- cost of improvement and cost of failure;
- contractual or regulatory constraints;
- measurement uncertainty;
- available fallback or alternative service;
- expected growth and change rate.

## Candidate Comparison

For 10 million valid monthly events:

| Target | Allowed bad events | Interpretation |
| ---: | ---: | --- |
| 99.5% | 50,000 | May tolerate visible recurring failure |
| 99.9% | 10,000 | Five times stricter |
| 99.95% | 5,000 | Requires additional headroom |
| 99.99% | 1,000 | Ten times stricter than 99.9% |

Each extra nine can require materially different architecture and operating cost. Compare marginal user-risk reduction with marginal cost.

## Do Not Set the Target From the Baseline Alone

If current performance is 99.97 percent, choosing 99.97 simply institutionalizes current behavior. The target may be unsustainable or unnecessarily strict. Use the baseline to test feasibility, not define user need.

## Headroom

An internal SLO should normally be stronger than a customer SLA so the organization can act before contractual exposure. Headroom must consider source and window differences, not only the percentage.

## Low Volume

For 100 monthly events, a 99.9 percent target permits 0.1 bad events and therefore behaves like a zero-failure objective in most periods. Use exact counts, longer evaluation, event review, or an alternative risk model. Do not pretend fractional events solve the problem.

## Target Review Triggers

Review when user harm changes, architecture or traffic changes materially, the SLI definition changes, performance persistently overachieves or misses, a new commitment appears, or measurement uncertainty changes.

## Production Scenario

Leadership requests 99.999 percent because a competitor advertises it. The service has one region, a 99.9 percent dependency, and no tested recovery.

### Analysis Questions

1. What user outcome or commitment is affected?
2. Which definition, target, source, or authority is missing?
3. What can be concluded from the current evidence?
4. What cannot be concluded?
5. Who owns the decision?
6. What correction is required?
7. What evidence will prove that the correction works?

---

## Practical Output: SLO target decision record

Create a record containing:

- Candidate target:
- User need:
- Business consequence:
- Historical evidence:
- Architecture:
- Dependencies:
- Cost:
- Alternatives:
- Uncertainty:
- Approved target:
- Authority:
- Review date:

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

- Choose reliability targets from user need, evidence, risk, architecture, and cost rather than copying arbitrary industry percentages.
- A target is defensible only when its measurement, rationale, owner, and decision are explicit.
- Strong governance preserves meaning as services and data change.
- Internal objectives and external commitments must be compared field by field.
- Contractual authority remains outside a technical team acting alone.

---

## Navigation

[Previous: Anatomy of an SLO Document](./21-Anatomy-of-an-SLO-Document.md)

[Next: SLO Time Windows and Compliance Periods](./23-SLO-Time-Windows-and-Compliance-Periods.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)
