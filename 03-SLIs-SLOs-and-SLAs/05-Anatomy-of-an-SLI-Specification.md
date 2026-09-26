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

## The Specification as an Engineering Contract

An SLI specification is the authoritative description of what will be measured. It is an engineering contract between the service owner, measurement implementer, data owner, and decision-maker. A dashboard, query, or vendor configuration may implement the specification, but none should silently redefine it.

## Required Fields and Their Purpose

| Field | Question answered | Failure when missing |
| --- | --- | --- |
| Stable ID and version | Which definition produced this result? | Historical reports cannot be reproduced. |
| Service and CUJ | Which outcome is represented? | Metric becomes detached from users. |
| Reliability dimension | What property is evaluated? | Availability, correctness, and latency are confused. |
| Event or interval unit | What is counted once? | Retries and samples distort totals. |
| Boundary | Where do observation and responsibility begin and end? | Claims exceed measured behavior. |
| Valid population | What enters the denominator? | Convenient exclusions inflate performance. |
| Good rule | What exact conditions constitute success? | Implementers make inconsistent assumptions. |
| Bad rule | Which valid outcomes fail? | Partial or semantic failures disappear. |
| Exclusion rule | What is outside scope, and why? | Real failure is removed without review. |
| Unknown rule | When can outcome not be established? | Missing data becomes success. |
| Formula and units | How is the result calculated? | Equivalent-looking dashboards disagree. |
| Source and query version | Which evidence is authoritative? | Source changes break comparability. |
| Segments | Which populations require separate visibility? | Global totals hide localized harm. |
| Data-quality controls | When is the measurement untrustworthy? | Compliance survives telemetry failure. |
| Owner and review triggers | Who keeps it correct? | Specification becomes stale. |

## Formal Event Model

Let $O$ be all observed candidate events. Classification produces four disjoint sets:

- $G$: good valid events;
- $B$: bad valid events;
- $X$: excluded events;
- $U$: unknown events.

For complete classification:

$$
|O| = |G| + |B| + |X| + |U|
$$

The valid population is:

$$
V = G \cup B
$$

and a basic ratio SLI is:

$$
SLI = \frac{|G|}{|G| + |B|}
$$

This model forces unknown and excluded observations to remain visible. It also creates a reconciliation control: every observed event must enter exactly one class after deduplication.

## Natural Language and Executable Logic

The specification should contain both. Natural language establishes intent. Executable logic implements it.

Natural-language rule:

> A checkout attempt is good when an eligible request produces exactly one correct order and durable confirmation within two seconds.

Illustrative query logic:

```sql
SELECT
  SUM(CASE WHEN eligible
            AND order_count = 1
            AND amount_matches
            AND durable_confirmation
            AND elapsed_ms <= 2000
           THEN 1 ELSE 0 END) AS good_events,
  SUM(CASE WHEN eligible THEN 1 ELSE 0 END) AS valid_events
FROM checkout_outcomes
WHERE event_time >= :window_start
  AND event_time < :window_end;
```

The query alone is insufficient. It does not explain how `eligible`, `amount_matches`, or `durable_confirmation` are produced, how duplicates are handled, or how absent records become unknown.

## Specification Invariants

An invariant is a condition that must always hold if the implementation is faithful.

Useful invariants include:

- `good_events <= valid_events`;
- `good + bad = valid`;
- no logical event appears in more than one class;
- exclusions use an approved reason code;
- unknown volume is reported separately;
- segment totals reconcile to the global population;
- query version matches the specification version;
- timestamps fall inside the declared window and timezone.

Automate these checks where possible. An SLI pipeline should fail visibly when its mathematics becomes impossible.

## Designing Test Cases

Every specification needs positive, negative, boundary, and failure tests.

| Test | Input | Expected class |
| --- | --- | --- |
| Normal success | Correct order in 800 ms | Good |
| Exact threshold | Correct order in exactly 2,000 ms | Good if rule is `<=` |
| Beyond threshold | Correct order in 2,001 ms | Bad |
| Semantic failure | `200` response with wrong amount | Bad |
| Duplicate effect | Two orders for one logical attempt | Bad |
| Invalid input | Request violates public contract | Excluded if approved |
| Source loss | No terminal record because telemetry failed | Unknown |
| Retry | Three transport requests, one logical idempotency key | One classified event |

Boundary-value tests matter. A specification that says “under two seconds” differs from “two seconds or less.”

## Data Lineage

The specification should trace each derived field to its origin:

```text
client attempt
  -> edge request record
  -> application decision
  -> payment authorization
  -> order write
  -> durable confirmation
  -> classified SLI event
```

For every transformation, record schema version, join key, deduplication rule, retention, and owner. A correct final formula cannot compensate for a broken join upstream.

## Versioning Rules

Create a new specification version when changing:

- the valid population;
- the good or bad rule;
- threshold inclusivity;
- measurement boundary;
- authoritative source;
- deduplication or retry treatment;
- segmentation that changes compliance;
- missing-data policy.

Editorial clarification that does not change classification may use a patch version. Material semantic changes need an effective date, parallel comparison where feasible, approval, and annotated reporting.

## Completed Mini-Specification

```yaml
sli_id: checkout-completion
version: 2.1.0
service: checkout
consumer: eligible retail customer
dimension: correctness-and-latency
logical_event: one checkout intention identified by idempotency_key
valid_event: request passes published eligibility rules and enters checkout
good_event: exactly one correct order is durably confirmed within 2000 ms
bad_event: any valid event that does not satisfy every good condition
excluded_event: malformed or unauthorized request rejected before entry
unknown_event: terminal outcome cannot be established from reconciled sources
formula: good_events / valid_events
source: reconciled_checkout_outcomes_v4
timezone: UTC
segments: [region, payment_method]
owner: commerce-reliability
effective_from: 2026-10-01T00:00:00Z
```

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
