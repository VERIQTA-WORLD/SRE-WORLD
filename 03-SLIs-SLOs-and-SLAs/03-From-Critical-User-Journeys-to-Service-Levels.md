# From Critical User Journeys to Service Levels

> Translate important user outcomes into a small set of reliability dimensions that can be measured and governed.

## Section Purpose

Translate important user outcomes into a small set of reliability dimensions that can be measured and governed.

The definition and discovery of Critical User Journeys belong to SRE Foundations. This section begins with an approved journey and derives service-level requirements.

The practical output is a **Critical User Journey to service-level map**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain the role of begin with the outcome in a service-level system.
2. Explain the role of identify the user in a service-level system.
3. Explain the role of define success and failure in a service-level system.
4. Explain the role of derive dimensions in a service-level system.
5. Explain the role of prioritize critical journeys in a service-level system.
6. Explain the role of separate reliability from product analytics in a service-level system.
7. Explain the role of map harm to evidence in a service-level system.
8. Explain the role of avoid endpoint-first design in a service-level system.

---

## Begin with the outcome

A journey should state what a defined user must accomplish. “POST /orders returns 200” is an interface event. “A customer submits an eligible order and receives durable confirmation exactly once” is an outcome.

---

## Identify the user

Users may be customers, employees, operators, API clients, scheduled workloads, or downstream services. Different users may have different expectations, harm, traffic, and measurement points.

---

## Define success and failure

Success includes the required result, not merely technical completion. Failure can include rejection, delay, duplication, stale data, corruption, incomplete output, or an unrecoverable intermediate state.

---

## Derive dimensions

Ask whether the journey must be available, timely, correct, fresh, durable, complete, or usable under degradation. Select only dimensions that materially affect the outcome.

---

## Prioritize critical journeys

Popularity is not the only criterion. A low-volume emergency recovery path, payroll run, or regulatory submission can deserve stronger protection than a high-volume cosmetic action.

---

## Separate reliability from product analytics

Conversion, engagement, and revenue can explain importance, but they do not directly prove service reliability. A user may abandon a journey for reasons unrelated to system failure.

---

## Map harm to evidence

For each failure, state who is harmed, how quickly harm appears, whether it is reversible, and which observation could detect it. This creates candidate SLIs without prematurely choosing telemetry.

---

## Avoid endpoint-first design

Endpoint metrics often miss client failure, multi-step journeys, semantic correctness, and dependency behavior. Start with the journey, then identify which technical events can represent it.

---

## Record assumptions

Journey definitions often contain uncertainty about user segments, retries, completion, and delayed outcomes. Record these assumptions and assign validation rather than hiding them in a denominator.


---

## Production Scenario

All checkout endpoints meet local success targets, but successful payment events are rejected before order creation. A journey-based service level must measure durable order confirmation, not isolated HTTP success.

### Analysis Questions

1. Which user outcome is at risk?
2. What is the correct measurement population and boundary?
3. Which evidence is authoritative?
4. Which assumption could make the result misleading?
5. Who owns the indicator and decision?
6. What immediate correction is required?
7. How will the corrected design be verified?

---

## Practical Output: Critical User Journey to service-level map

Create a record containing:

- Journey:
- User:
- Start and end:
- Success criteria:
- Failure modes:
- Reliability dimensions:
- User harm:
- Candidate observations:
- Owner:
- Unknowns:

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

- Translate important user outcomes into a small set of reliability dimensions that can be measured and governed.
- A percentage without a precise population, calculation, window, and owner is not a trustworthy service level.
- User-visible outcomes take priority over convenient infrastructure signals.
- Unknown and excluded events require explicit treatment.
- Every service-level artifact needs validation and lifecycle control.

---

## Navigation

[Previous: SLI, SLO, and SLA Terminology](./02-SLI-SLO-and-SLA-Terminology.md)

[Next: Service Boundaries and Measurement Boundaries](./04-Service-Boundaries-and-Measurement-Boundaries.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

