# SLI Data Quality and Measurement Failure

> Treat the SLI data path as a production dependency whose failure can invalidate reliability decisions.

## Section Purpose

Treat the SLI data path as a production dependency whose failure can invalidate reliability decisions.

This section governs measurement integrity. It does not build a complete data platform or observability pipeline.

The practical output is a **SLI data-quality control plan**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain measurement lineage and its effect on service-level accuracy.
2. Explain missing telemetry and its effect on service-level accuracy.
3. Explain duplicates and its effect on service-level accuracy.
4. Explain delay and lateness and its effect on service-level accuracy.
5. Explain schema and semantic drift and its effect on service-level accuracy.
6. Explain sampling bias and its effect on service-level accuracy.
7. Explain clock and ordering and its effect on service-level accuracy.
8. Explain query failure and its effect on service-level accuracy.
9. Apply the section to a realistic production service.
10. Produce and verify the required practical artifact.

---

## Measurement lineage

Document the path from raw event through collection, transport, storage, transformation, query, dashboard, and report.

---

## Missing telemetry

Loss may be correlated with severe service failure. Never assume absent events are successful. Track expected and observed volume.

---

## Duplicates

Retries, replay, and ingestion behavior can inflate numerator and denominator. Use identifiers or controlled deduplication.

---

## Delay and lateness

Late data can change a closed period. Define allowed lateness, provisional reporting, restatement, and notification.

---

## Schema and semantic drift

A field can retain its name while changing meaning. Version producers, consumers, queries, and historical comparability.

---

## Sampling bias

Uniform sampling can miss rare tenants or failure types. Tail-based sampling can overrepresent failure. State the inference boundary.

---

## Clock and ordering

Skew, precision, timezone, and reordering affect latency, freshness, and window assignment. Validate timestamps.

---

## Query failure

Syntax can be valid while joins, filters, label changes, or denominator logic are wrong. Test with fixtures and independent calculations.

---

## Confidence and invalidation

Define thresholds for unknown, missing, or delayed data beyond which the SLI is provisional or invalid. An invalid SLI must not authorize high-risk decisions.

---

## Data-quality incident

Assign owners, impact assessment, correction, restatement, stakeholder communication, and prevention when measurement fails.

---

## Measurement Is a Production Dependency

An SLI pipeline can fail independently of the service. If measurement failure makes the service appear healthy, the control system is unsafe.

Assess five dimensions:

- **completeness:** are expected events present?
- **uniqueness:** are logical events counted once?
- **validity:** do fields satisfy schema and domain rules?
- **freshness:** is evidence available in time for the decision?
- **lineage:** can a result be traced to sources, transformations, and versions?

## Coverage Controls

Compare independent totals. Examples include edge requests versus classified events, accepted jobs versus terminal outcomes, committed objects versus inventory records, and billing transactions versus order records.

$$
Coverage = \frac{Classified\ Expected\ Events}{Independent\ Expected\ Events}
$$

Set a minimum coverage threshold and define what happens below it. The correct result may be “compliance unknown,” not “SLO met.”

## Failure Modes

- dropped logs;
- metric resets;
- sampling changes;
- schema drift;
- broken joins;
- duplicate ingestion;
- late partitions;
- timezone changes;
- silent query edits;
- retention loss;
- permissions blocking one source;
- telemetry sharing the same failure domain as the service.

## Plausibility and Reconciliation

Automate invariants:

- good plus bad equals valid;
- classified plus excluded plus unknown reconciles to observed population;
- segment totals match global totals;
- event time is plausible;
- latency is not negative;
- SLI remains between 0 and 1;
- source and query versions match the approved specification.

## Unknown Compliance

Suppose $G=99{,}000$, $B=500$, and $U=500$, with a 99.4 percent target.

Best case:

$$
\frac{99{,}500}{100{,}000}=99.5\%
$$

Worst case:

$$
\frac{99{,}000}{100{,}000}=99.0\%
$$

Because the target lies inside the uncertainty interval, compliance cannot be established.

## Independent Monitoring

Monitor the measurement system using sources that do not fail in exactly the same way. A logging outage cannot reliably report its own completeness from the missing logs. Use pipeline health, source reconciliation, synthetic events, and storage audits.

## Production Scenario

During a severe regional outage, the telemetry pipeline in that region also stops. The global SLI improves because the failed traffic disappears from the dataset.

### Analysis Questions

1. Which user or consumer outcome matters?
2. Which population and measurement boundary apply?
3. Which evidence should be trusted?
4. What could make the reported value misleading?
5. Which owner has authority to correct the design?
6. What should be changed now?
7. How will the change be verified?

---

## Practical Output: SLI data-quality control plan

Create a record containing:

- Data lineage:
- Expected volume:
- Missing-data rule:
- Duplicate control:
- Allowed lateness:
- Schema control:
- Sampling:
- Clock checks:
- Query tests:
- Invalidation threshold:
- Restatement process:
- Owner:

Record unknowns, limitations, owners, dates, and validation evidence. Never improve a result by silently removing difficult observations.

---

## Review Checklist

- [ ] User outcome and population are explicit.
- [ ] Measurement and service boundaries are distinguished.
- [ ] Calculation rules are reproducible.
- [ ] Missing, duplicate, delayed, excluded, and unknown evidence is handled.
- [ ] Relevant segments remain visible.
- [ ] Limitations and uncertainty are stated.
- [ ] The accountable owner accepted the design.
- [ ] Test cases include failure and edge conditions.
- [ ] Review triggers and version history are recorded.

---

## Key Takeaways

- Treat the SLI data path as a production dependency whose failure can invalidate reliability decisions.
- Convenient telemetry is not automatically reliable evidence.
- Aggregate success must not hide a materially harmed population.
- Measurement failure is itself an operational risk.
- Every material definition or query change requires controlled review.

---

## Navigation

[Previous: Aggregation, Segmentation, and Weighting](./19-Aggregation-Segmentation-and-Weighting.md)

[Next: Anatomy of an SLO Document](./21-Anatomy-of-an-SLO-Document.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)
