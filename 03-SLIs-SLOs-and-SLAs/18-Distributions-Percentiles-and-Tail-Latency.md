# Distributions, Percentiles, and Tail Latency

> Interpret latency populations without relying on misleading averages or mathematically invalid percentile aggregation.

## Section Purpose

Interpret latency populations without relying on misleading averages or mathematically invalid percentile aggregation.

This section teaches the statistics needed for service levels, not a complete statistics course or performance-diagnostics methodology.

The practical output is a **Distribution and percentile analysis worksheet**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain distribution first and its effect on service-level accuracy.
2. Explain mean and median and its effect on service-level accuracy.
3. Explain percentiles and its effect on service-level accuracy.
4. Explain tail latency and its effect on service-level accuracy.
5. Explain threshold ratios and its effect on service-level accuracy.
6. Explain percentile aggregation and its effect on service-level accuracy.
7. Explain histogram buckets and its effect on service-level accuracy.
8. Explain sparse traffic and outliers and its effect on service-level accuracy.
9. Apply the section to a realistic production service.
10. Produce and verify the required practical artifact.

---

## Distribution first

Latency is a population, not one value. Inspect shape, modes, spread, tail, and changes across segments.

---

## Mean and median

The mean is sensitive to large values. The median describes the middle event and can hide a severely harmed minority.

---

## Percentiles

p99 is the value at or below which approximately 99 percent of observations fall. It does not describe the average of the slowest one percent.

---

## Tail latency

A small slow population can include millions of requests or high-value users. Tail protection must follow consequence, not only percentage.

---

## Threshold ratios

An SLO stating 99 percent below 500 ms directly counts good events. A p99 chart answers a related but different question.

---

## Percentile aggregation

Do not average regional or hourly percentiles. Merge compatible distributions or histograms, or calculate from the complete event population.

---

## Histogram buckets

Buckets must preserve relevant thresholds and ranges. Poor buckets make quantiles coarse or impossible to compare.

---

## Sparse traffic and outliers

Percentiles are unstable for small samples. Publish counts, use longer windows where justified, and investigate impossible values.

---

## Multiple thresholds

Two or more thresholds can protect typical and tail experience, such as 95 percent within 300 ms and 99.9 percent within two seconds.

---

## Production Scenario

A dashboard averages the p99 latency reported by ten regions. One small region has catastrophic performance, but the arithmetic average appears acceptable.

### Analysis Questions

1. Which user or consumer outcome matters?
2. Which population and measurement boundary apply?
3. Which evidence should be trusted?
4. What could make the reported value misleading?
5. Which owner has authority to correct the design?
6. What should be changed now?
7. How will the change be verified?

---

## Practical Output: Distribution and percentile analysis worksheet

Create a record containing:

- Population:
- Count:
- Histogram:
- Mean:
- Median:
- Percentiles:
- Threshold ratios:
- Segments:
- Tail impact:
- Aggregation method:
- Conclusion:

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

- Interpret latency populations without relying on misleading averages or mathematically invalid percentile aggregation.
- Convenient telemetry is not automatically reliable evidence.
- Aggregate success must not hide a materially harmed population.
- Measurement failure is itself an operational risk.
- Every material definition or query change requires controlled review.

---

## Navigation

[Previous: Ratio, Time-Based, and Window-Based SLIs](./17-Ratio-Time-Based-and-Window-Based-SLIs.md)

[Next: Aggregation, Segmentation, and Weighting](./19-Aggregation-Segmentation-and-Weighting.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

