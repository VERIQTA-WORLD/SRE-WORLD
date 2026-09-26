# Anatomy of an SLI Specification

> Define every field required for another engineer to reproduce, validate, and govern a Service Level Indicator.

## Section Purpose

Define every field required for another engineer to reproduce, validate, and govern a Service Level Indicator.

This section defines the specification. Sections 6 through 20 explain its most difficult fields in depth.

The practical output is a **Complete SLI specification**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain the role of identity and context in a service-level system.
2. Explain the role of observation and boundary in a service-level system.
3. Explain the role of eligibility in a service-level system.
4. Explain the role of good and bad criteria in a service-level system.
5. Explain the role of calculation in a service-level system.
6. Explain the role of source and custody in a service-level system.
7. Explain the role of limitations and confidence in a service-level system.
8. Explain the role of validation in a service-level system.

---

## Identity and context

Give the SLI a stable identifier, descriptive name, service, journey, owner, user, and reliability dimension. Names such as “availability” are too ambiguous across services.

---

## Observation and boundary

State the event or observation being classified and where it is observed. A request, job, message, record, minute, session, or completed journey requires different mathematics.

---

## Eligibility

Define which observations enter the denominator and why. Eligibility must be implementable, versioned, and protected from exclusions that erase user harm.

---

## Good and bad criteria

Write criteria that are mutually understandable and testable. When possible, define good explicitly and derive bad from valid minus good while preserving unknown outcomes.

---

## Calculation

Record numerator, denominator, units, query, aggregation, segmentation, time window, late-data behavior, and rounding. A chart without the calculation is not a specification.

---

## Source and custody

Identify the authoritative data source, source owner, retention, access, expected delay, sampling, and schema. Record every transformation between raw evidence and published result.

---

## Limitations and confidence

State blind spots, missing populations, proxy assumptions, known bias, expected uncertainty, and conditions that invalidate the indicator.

---

## Validation

Test the SLI with known good, bad, excluded, duplicate, delayed, and missing events. Compare the calculation with independent evidence before approval.

---

## Versioning

A change to eligibility, thresholds, query, source, aggregation, or segmentation can change the meaning of historical values. Version material changes and record comparability.


---

## Production Scenario

Two dashboards both show “checkout availability,” but one counts API responses and the other counts durable orders. A specification exposes that they are different indicators rather than conflicting calculations.

### Analysis Questions

1. Which user outcome is at risk?
2. What is the correct measurement population and boundary?
3. Which evidence is authoritative?
4. Which assumption could make the result misleading?
5. Who owns the indicator and decision?
6. What immediate correction is required?
7. How will the corrected design be verified?

---

## Practical Output: Complete SLI specification

Create a record containing:

- SLI ID and version:
- Service, journey, and user:
- Reliability dimension:
- Measurement point:
- Valid-event rule:
- Good and bad criteria:
- Exclusions and unknowns:
- Numerator and denominator:
- Source and query:
- Aggregation and segmentation:
- Window and delay:
- Limitations:
- Owner and approval:
- Validation and review:

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

- Define every field required for another engineer to reproduce, validate, and govern a Service Level Indicator.
- A percentage without a precise population, calculation, window, and owner is not a trustworthy service level.
- User-visible outcomes take priority over convenient infrastructure signals.
- Unknown and excluded events require explicit treatment.
- Every service-level artifact needs validation and lifecycle control.

---

## Navigation

[Previous: Service Boundaries and Measurement Boundaries](./04-Service-Boundaries-and-Measurement-Boundaries.md)

[Next: Valid Events and Eligibility Rules](./06-Valid-Events-and-Eligibility-Rules.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

