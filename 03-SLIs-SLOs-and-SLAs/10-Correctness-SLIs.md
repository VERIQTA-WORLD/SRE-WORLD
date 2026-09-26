# Correctness SLIs

> Measure whether the service produces the right result, state transition, authorization decision, or side effect.

## Section Purpose

Measure whether the service produces the right result, state transition, authorization decision, or side effect.

This section defines correctness measurement. It does not replace application testing, data governance, or security engineering.

The practical output is a **Correctness SLI specification and validation plan**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain the role of semantic correctness in a service-level system.
2. Explain the role of ground truth in a service-level system.
3. Explain the role of financial correctness in a service-level system.
4. Explain the role of duplicate and missing effects in a service-level system.
5. Explain the role of ordering in a service-level system.
6. Explain the role of authorization correctness in a service-level system.
7. Explain the role of delayed discovery in a service-level system.
8. Explain the role of sampling in a service-level system.

---

## Semantic correctness

A response can be syntactically valid and semantically wrong. Correctness asks whether the result matches the intended business and user outcome.

---

## Ground truth

Measurement needs a trusted reference, invariant, reconciliation process, independent calculation, or validated sample. Without ground truth, state that the SLI is a proxy.

---

## Financial correctness

Payments and ledgers require amount, currency, beneficiary, authorization, and exactly-once recording. Availability alone cannot protect these conditions.

---

## Duplicate and missing effects

A request may succeed technically while producing no durable effect or several effects. Stable transaction identifiers and reconciliation expose these failures.

---

## Ordering

Messaging, inventory, and state machines may require ordered application. Measure violations at the business boundary rather than only broker sequence.

---

## Authorization correctness

Correctness includes allowing authorized actions and rejecting unauthorized ones. A high success ratio can be dangerous when invalid access is accepted.

---

## Delayed discovery

Some errors are known only after settlement, audit, or user report. Define allowed lateness, historical correction, and how closed periods are restated.

---

## Sampling

Full verification may be too expensive. A statistically and operationally justified sample can estimate correctness, but confidence interval, bias, and blind spots must be reported.

---

## Human review

High-consequence or subjective results may need controlled human validation. Record reviewer consistency, sampling, conflict resolution, and privacy.

---

## Calculation example

If an audit sample of 5,000 completed orders finds 15 incorrect totals, sampled correctness is 99.7 percent. This estimate is not equivalent to proving that 99.7 percent of every order was correct.


---

## Production Scenario

A transfer API returns successful responses, but a currency-conversion defect records incorrect amounts. Availability and latency remain healthy while the service violates its purpose.

### Analysis Questions

1. Which user outcome is at risk?
2. What is the correct measurement population and boundary?
3. Which evidence is authoritative?
4. Which assumption could make the result misleading?
5. Who owns the indicator and decision?
6. What immediate correction is required?
7. How will the corrected design be verified?

---

## Practical Output: Correctness SLI specification and validation plan

Create a record containing:

- Correct outcome:
- Ground truth:
- Comparison method:
- Sampling:
- Delayed discovery:
- Duplicates and omissions:
- Authorization checks:
- Confidence:
- Correction rule:
- Owner and evidence:

Unknown information must remain visible with an investigation owner and due date. Do not use “not applicable” to hide missing evidence.

---

## Review Checklist

- [ ] The protected user outcome is explicit.
- [ ] The evaluated population is defined.
- [ ] The measurement boundary is defensible.
- [ ] Good, bad, excluded, and unknown behavior cannot be confused.
- [ ] The calculation can be reproduced from authoritative evidence.
- [ ] Segments with materially different harm remain visible.
- [ ] Limitations and uncertainty are documented.
- [ ] Ownership, approval, version, and review triggers are recorded.
- [ ] The result supports a named production decision.

---

## Key Takeaways

- Measure whether the service produces the right result, state transition, authorization decision, or side effect.
- A percentage without a precise population, calculation, window, and owner is not a trustworthy service level.
- User-visible outcomes take priority over convenient infrastructure signals.
- Unknown and excluded events require explicit treatment.
- Every service-level artifact needs validation and lifecycle control.

---

## Navigation

[Previous: Latency SLIs](./09-Latency-SLIs.md)

[Next: Quality and Degradation SLIs](./11-Quality-and-Degradation-SLIs.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

