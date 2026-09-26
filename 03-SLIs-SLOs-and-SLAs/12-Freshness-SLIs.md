# Freshness SLIs

> Measure whether data, content, and derived state are current enough for the decision or journey they support.

## Section Purpose

Measure whether data, content, and derived state are current enough for the decision or journey they support.

Freshness is distinct from correctness. Current data may be wrong, and correct historical data may be too old for the intended use.

The practical output is a **Freshness SLI specification**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain define useful age and its effect on service-level accuracy.
2. Explain event time and processing time and its effect on service-level accuracy.
3. Explain data age and its effect on service-level accuracy.
4. Explain last successful update and its effect on service-level accuracy.
5. Explain replication and cache staleness and its effect on service-level accuracy.
6. Explain late source data and its effect on service-level accuracy.
7. Explain backfills and its effect on service-level accuracy.
8. Explain clock and timezone and its effect on service-level accuracy.
9. Apply the section to a realistic production service.
10. Produce and verify the required practical artifact.

---

## Define useful age

Freshness is relative to a user need. A one-hour delay may be harmless for a monthly report and dangerous for fraud detection.

---

## Event time and processing time

Event time records when the source event occurred. Processing time records when the system handled it. Their difference exposes pipeline delay.

---

## Data age

A common SLI classifies a read as good when the newest required data is no older than a defined threshold.

---

## Last successful update

For scheduled publication, measure whether the latest expected update completed by its deadline, not merely whether a process ran.

---

## Replication and cache staleness

A replica or cache can be available but behind its source. Measure the user-visible version or timestamp where possible.

---

## Late source data

A pipeline cannot make unavailable source data current. Separate provider delay, pipeline delay, and publication delay while preserving end-to-end impact.

---

## Backfills

Backfills improve completeness but can alter historical freshness calculations. Define whether and how closed periods are restated.

---

## Clock and timezone

Timezone conversion, daylight-saving changes, skew, and missing timestamps can create impossible ages. Validate time metadata.

---

## Fresh but incorrect

Do not treat recent timestamps as proof of correct content. Pair freshness with correctness or integrity where required.

---

## Production Scenario

A dashboard updates every minute, but its source feed stopped six hours ago. The page is technically refreshed while the business data is stale.

### Analysis Questions

1. Which user or consumer outcome matters?
2. Which population and measurement boundary apply?
3. Which evidence should be trusted?
4. What could make the reported value misleading?
5. Which owner has authority to correct the design?
6. What should be changed now?
7. How will the change be verified?

---

## Practical Output: Freshness SLI specification

Create a record containing:

- Data product and user:
- Source event time:
- Publication time:
- Freshness threshold:
- Expected schedule:
- Late-data rule:
- Backfill rule:
- Clock validation:
- Segments:
- Related correctness evidence:

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

- Measure whether data, content, and derived state are current enough for the decision or journey they support.
- Convenient telemetry is not automatically reliable evidence.
- Aggregate success must not hide a materially harmed population.
- Measurement failure is itself an operational risk.
- Every material definition or query change requires controlled review.

---

## Navigation

[Previous: Quality and Degradation SLIs](./11-Quality-and-Degradation-SLIs.md)

[Next: Durability and Data Integrity SLIs](./13-Durability-and-Data-Integrity-SLIs.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

