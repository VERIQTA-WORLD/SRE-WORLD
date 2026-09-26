# Deriving Error Budgets from SLOs

> Calculate and interpret the permitted unreliability implied by an SLO without confusing arithmetic with organizational policy.

## Section Purpose

Calculate and interpret the permitted unreliability implied by an SLO without confusing arithmetic with organizational policy.

This section derives budgets. Full error-budget policy, release enforcement, and multi-window burn-rate alerting belong in later collections.

The practical output is a **Error-budget derivation worksheet**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain core derivation and its role in a defensible service-level system.
2. Explain request budget and its role in a defensible service-level system.
3. Explain time budget and its role in a defensible service-level system.
4. Explain budget consumed and its role in a defensible service-level system.
5. Explain budget remaining and its role in a defensible service-level system.
6. Explain clustering and its role in a defensible service-level system.
7. Explain segmentation and its role in a defensible service-level system.
8. Explain low volume and its role in a defensible service-level system.
9. Apply the section to an ambiguous production scenario.
10. Produce and defend the required artifact.

---

## Core derivation

For a good-event target T expressed as a fraction, the permitted bad fraction is 1 minus T. A 99.9 percent target implies 0.1 percent permitted bad events.

---

## Request budget

Multiply the valid-event population by the permitted bad fraction. With 2,000,000 valid events and a 99.95 percent target, the allowance is 1,000 bad events.

---

## Time budget

Multiply evaluated time by the permitted bad fraction. For a 30-day period at 99.9 percent, the theoretical allowance is 43.2 minutes.

---

## Budget consumed

Consumed fraction equals observed bad events divided by allowed bad events, when definitions align. Values above 100 percent indicate the objective has been missed.

---

## Budget remaining

Remaining allowance equals permitted bad amount minus observed bad amount. It can be negative and must not be clamped silently to zero.

---

## Clustering

The same total failure can produce different user harm when concentrated in one long outage or distributed across small failures. Pair budget totals with continuity constraints where necessary.

---

## Segmentation

A healthy global budget can hide an exhausted regional or critical-journey budget. Preserve segments that have independent consequences.

---

## Low volume

One failure can consume a large fraction of a small event budget. Use counts, consecutive failures, longer justified periods, and qualitative evidence.

---

## Measurement uncertainty

Unknown and delayed events make remaining budget uncertain. Publish provisional ranges or invalidate the calculation when confidence is insufficient.

---

## SLA distinction

An SLA threshold and remedy calculation may use a different population, source, exclusion, and period. The internal error budget should support engineering decisions, not merely avoid credits.

---

## Core Derivation

For SLO target $T$:

$$
Budget\ Fraction = 1-T
$$

For event volume $N$:

$$
Allowed\ Bad\ Events = N(1-T)
$$

For observed bad events $B$:

$$
Budget\ Consumed = \frac{B}{N(1-T)}
$$

$$
Budget\ Remaining = N(1-T)-B
$$

## Request Example

A service has a 99.95 percent SLO and 8,000,000 valid requests:

$$
8{,}000{,}000(1-0.9995)=4{,}000
$$

If 2,600 requests are bad, 65 percent of the budget is consumed and 1,400 bad events remain before the SLO boundary.

## Time Example

For a 99.9 percent time-based SLO over a 30-day period:

$$
30 \times 24 \times 60 \times 0.001 = 43.2\ minutes
$$

This conversion is valid only for a time-based SLI. Request-based budgets use request volume.

## Negative Budget

If observed bad events exceed the allowance, remaining budget is negative. Do not clamp it to zero because the magnitude communicates how far performance exceeded tolerance.

## Fast and Slow Consumption

The same total budget can be consumed through one severe outage or chronic small failure. This section derives the amount. Alerting on burn rate and enforcing policy belong to their dedicated collections.

## Segments and Multiple Objectives

Calculate budgets on the exact population of each SLO. Do not subtract a regional failure from a global allowance and assume the protected region is acceptable. Multiple SLOs create multiple budgets unless an approved policy defines interaction.

## Uncertainty

If unknown events can change attainment, budget remaining is a range. Report best and worst cases rather than a precise number.

## SLA Boundary

An SLO error budget is an internal risk mechanism. An SLA may use a different source, window, target, exclusion rule, and remedy. Do not use the contractual credit threshold as the operating budget.

## Production Scenario

A service reports 60 percent budget remaining, but ten percent of traffic is missing because the failed region stopped exporting telemetry. The arithmetic is correct only for incomplete evidence.

### Analysis Questions

1. What user outcome or commitment is affected?
2. Which definition, target, source, or authority is missing?
3. What can be concluded from the current evidence?
4. What cannot be concluded?
5. Who owns the decision?
6. What correction is required?
7. What evidence will prove that the correction works?

---

## Practical Output: Error-budget derivation worksheet

Create a record containing:

- SLI and target:
- Compliance period:
- Valid population or time:
- Permitted bad fraction:
- Allowed bad amount:
- Observed bad amount:
- Unknown amount:
- Consumed percent:
- Remaining amount:
- Segments:
- Interpretation:

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

- Calculate and interpret the permitted unreliability implied by an SLO without confusing arithmetic with organizational policy.
- A target is defensible only when its measurement, rationale, owner, and decision are explicit.
- Strong governance preserves meaning as services and data change.
- Internal objectives and external commitments must be compared field by field.
- Contractual authority remains outside a technical team acting alone.

---

## Navigation

[Previous: Dependency, Composite, and End-to-End SLOs](./25-Dependency-Composite-and-End-to-End-SLOs.md)

[Next: SLO Ownership, Governance, and Lifecycle](./27-SLO-Ownership-Governance-and-Lifecycle.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)
