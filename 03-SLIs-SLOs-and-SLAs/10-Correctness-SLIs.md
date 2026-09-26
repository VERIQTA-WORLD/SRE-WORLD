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

## Correctness Requires Authoritative Truth

A correctness SLI compares the delivered result with a rule or source that can determine what the result should have been. Transport success cannot provide this truth.

Examples of authoritative validation include:

- financial ledger reconciliation;
- source-to-destination record comparison;
- checksum or content hash;
- domain invariant;
- independently computed expected result;
- human-reviewed sample with controlled criteria;
- downstream confirmation of the intended effect.

The validation source has its own failure modes. If the service and validator depend on the same flawed transformation, they can agree and both be wrong.

## Correctness Dimensions

Correctness may include:

- **accuracy:** value matches authoritative truth;
- **completeness:** no required data or effect is missing;
- **uniqueness:** an effect occurs the required number of times;
- **ordering:** events appear in required sequence;
- **association:** result belongs to the correct user or object;
- **state transition:** operation moves the system to a permitted state;
- **authorization correctness:** permitted actions succeed and forbidden actions do not.

These conditions can form one good-event rule when all are necessary for the outcome. Report severe classes separately when averaging would hide intolerable harm.

## Basic Formula

$$
Correctness = \frac{Correct\ Valid\ Results}{Validated\ Valid\ Results}
$$

The denominator may be smaller than total events when validation is sampled or delayed. In that case, report validation coverage:

$$
Validation\ Coverage = \frac{Validated\ Valid\ Results}{All\ Valid\ Results}
$$

A 100 percent correctness result based on 1 percent unrepresentative sampling does not prove service-wide correctness.

## Sampling Design

When full validation is expensive:

- sample randomly from the valid population;
- stratify by high-risk operation or segment;
- oversample rare but severe cases;
- preserve selection probabilities for weighted estimates;
- keep validators independent where possible;
- report sample size and uncertainty;
- run complete reconciliation periodically.

Convenience sampling, such as validating only successful or easily joined records, creates bias.

## Delayed Truth

Some defects appear after the compliance period. Chargebacks, duplicate payments, corrupted archives, and incorrect invoices may be discovered days or months later.

The specification must define:

- provisional correctness;
- validation delay;
- finalization or restatement period;
- how historical reports are corrected;
- whether contract claims can be reopened;
- the audit trail connecting the original and revised result.

Do not freeze a false value merely because the reporting period ended.

## Worked Example: Invoice Correctness

During a calendar month:

- 1,200,000 invoices are issued;
- 1,195,000 are automatically reconciled;
- 4,500 require delayed validation;
- 500 cannot be validated because the reference tax dataset is missing;
- among validated invoices, 1,193,207 are correct and 1,793 are incorrect.

Current validated correctness is:

$$
\frac{1{,}193{,}207}{1{,}195{,}000} = 99.85\%
$$

Current validation coverage is:

$$
\frac{1{,}195{,}000}{1{,}200{,}000} = 99.583\%
$$

The 5,000 unresolved invoices cannot be counted as correct. The report should be provisional and show best and worst possible bounds.

## Exactly-Once Business Effects

Distributed systems rarely guarantee exactly-once delivery at every technical layer. The user may still require an exactly-once business effect.

Measure the business outcome:

- one idempotency key maps to one committed order;
- repeated delivery does not create repeated charge;
- reconciliation detects omissions and duplicates;
- retry returns the existing result when appropriate.

Discarding duplicate telemetry is not the same as proving a duplicate effect did not occur.

## Safety-Critical or Intolerable Errors

A ratio can normalize unacceptable events. If one incorrect authorization can cause severe legal, safety, or security harm, report the event count and severity separately. The target may be zero observed events with additional preventive and detective controls. Avoid claiming that a 100 percent SLO guarantees impossibility.

## Correctness Validation Tests

Include wrong values, missing fields, duplicated effects, swapped identities, out-of-order events, stale reference data, validator outage, conflicting truth sources, late discovery, and corrupted joins. Verify that the correctness pipeline can detect its own inability to validate.

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
