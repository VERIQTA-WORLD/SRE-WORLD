# Quality and Degradation SLIs

> Measure whether an available service remains useful when it returns partial, reduced, fallback, or otherwise degraded outcomes.

## Section Purpose

Measure whether an available service remains useful when it returns partial, reduced, fallback, or otherwise degraded outcomes.

This section measures user-visible quality. It does not define product experimentation, recommendation-model evaluation, or complete graceful-degradation architecture.

The practical output is a **Quality and degradation SLI specification**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain availability is not usefulness and its effect on service-level accuracy.
2. Explain define minimum acceptable service and its effect on service-level accuracy.
3. Explain partial results and its effect on service-level accuracy.
4. Explain degraded modes and its effect on service-level accuracy.
5. Explain quality scoring and its effect on service-level accuracy.
6. Explain subjective quality and its effect on service-level accuracy.
7. Explain proxy risk and its effect on service-level accuracy.
8. Explain recovery and explanation and its effect on service-level accuracy.
9. Apply the section to a realistic production service.
10. Produce and verify the required practical artifact.

---

## Availability is not usefulness

A service can answer every request and still fail its purpose through empty, low-quality, incomplete, or unrecoverable responses.

---

## Define minimum acceptable service

State the smallest outcome that still provides legitimate user value. A fallback counts as good only when it satisfies this minimum.

---

## Partial results

Missing items, fields, attachments, or dependent features may have different consequences. Classify required and optional content explicitly.

---

## Degraded modes

Record which features may be disabled, how the mode is communicated, who authorizes it, and whether users can safely continue.

---

## Quality scoring

Some outcomes need a score rather than a binary class. Define the scale, reference, threshold, aggregation, and sensitivity to user segments.

---

## Subjective quality

Human judgment may be necessary for relevance, media quality, or generated results. Use calibrated reviewers and report disagreement.

---

## Proxy risk

Click rate, abandonment, or support contacts can suggest quality problems but include non-reliability causes. Label proxies and corroborate them.

---

## Recovery and explanation

A useful degraded outcome should communicate limitations and permit retry, correction, or recovery without creating unsafe ambiguity.

---

## Threshold design

Avoid a threshold chosen only because current data passes it. Tie the minimum quality to user need and material harm.

---

## Production Scenario

A search service responds successfully in 100 ms but returns no results for a major product category. Availability and latency are healthy, while quality is unacceptable.

### Analysis Questions

1. Which user or consumer outcome matters?
2. Which population and measurement boundary apply?
3. Which evidence should be trusted?
4. What could make the reported value misleading?
5. Which owner has authority to correct the design?
6. What should be changed now?
7. How will the change be verified?

---

## Practical Output: Quality and degradation SLI specification

Create a record containing:

- Protected outcome:
- Minimum acceptable quality:
- Full, degraded, and failed classes:
- Scoring method:
- Fallback treatment:
- User communication:
- Source and sampling:
- Segments:
- Limitations:
- Validation:

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

- Measure whether an available service remains useful when it returns partial, reduced, fallback, or otherwise degraded outcomes.
- Convenient telemetry is not automatically reliable evidence.
- Aggregate success must not hide a materially harmed population.
- Measurement failure is itself an operational risk.
- Every material definition or query change requires controlled review.

---

## Navigation

[Previous: Correctness SLIs](./10-Correctness-SLIs.md)

[Next: Freshness SLIs](./12-Freshness-SLIs.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

