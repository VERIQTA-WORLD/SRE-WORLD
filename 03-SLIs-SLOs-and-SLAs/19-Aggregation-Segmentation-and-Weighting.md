# Aggregation, Segmentation, and Weighting

> Prevent aggregate service levels from concealing material harm to regions, tenants, journeys, interfaces, or other meaningful populations.

## Section Purpose

Prevent aggregate service levels from concealing material harm to regions, tenants, journeys, interfaces, or other meaningful populations.

This section defines visibility and calculation choices. It does not establish commercial customer tiers or full capacity allocation.

The practical output is a **SLI segmentation and aggregation plan**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain global aggregation and its effect on service-level accuracy.
2. Explain material segments and its effect on service-level accuracy.
3. Explain volume weighting and its effect on service-level accuracy.
4. Explain equal weighting and its effect on service-level accuracy.
5. Explain criticality weighting and its effect on service-level accuracy.
6. Explain simpson’s paradox and its effect on service-level accuracy.
7. Explain cardinality and its effect on service-level accuracy.
8. Explain small populations and its effect on service-level accuracy.
9. Apply the section to a realistic production service.
10. Produce and verify the required practical artifact.

---

## Global aggregation

A global SLI is useful for portfolio decisions but can remain healthy while a smaller population experiences complete failure.

---

## Material segments

Segment by a characteristic that changes user harm or ownership, such as region, tenant, interface, request type, channel, or critical journey.

---

## Volume weighting

Event aggregation naturally gives more weight to high-volume groups. This represents event impact but can erase smaller critical groups.

---

## Equal weighting

Equal group weighting protects representation but can let a tiny group dominate the summary. State the decision purpose.

---

## Criticality weighting

Some journeys or customers may require stronger treatment. Weighting must be governed and must not disguise raw segment results.

---

## Simpson’s paradox

Aggregate trends can reverse the pattern visible within groups because traffic mix changes. Compare segment and composition changes.

---

## Cardinality

Unlimited segmentation can make storage and analysis unusable. Preserve a controlled set of decision-relevant dimensions and drill-down paths.

---

## Small populations

A small group can have volatile percentages. Publish counts, confidence, consecutive failures, and qualitative evidence.

---

## Aggregation policy

Record how groups combine, which segments have independent objectives, and when a segment breach overrides the global result.

---

## Production Scenario

Overall login success improves because traffic shifts toward a healthy region, while success in another region continues to deteriorate.

### Analysis Questions

1. Which user or consumer outcome matters?
2. Which population and measurement boundary apply?
3. Which evidence should be trusted?
4. What could make the reported value misleading?
5. Which owner has authority to correct the design?
6. What should be changed now?
7. How will the change be verified?

---

## Practical Output: SLI segmentation and aggregation plan

Create a record containing:

- Global population:
- Required segments:
- Reason:
- Weighting:
- Minimum count:
- Independent target:
- Override rule:
- Cardinality control:
- Owner:
- Review trigger:

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

- Prevent aggregate service levels from concealing material harm to regions, tenants, journeys, interfaces, or other meaningful populations.
- Convenient telemetry is not automatically reliable evidence.
- Aggregate success must not hide a materially harmed population.
- Measurement failure is itself an operational risk.
- Every material definition or query change requires controlled review.

---

## Navigation

[Previous: Distributions, Percentiles, and Tail Latency](./18-Distributions-Percentiles-and-Tail-Latency.md)

[Next: SLI Data Quality and Measurement Failure](./20-SLI-Data-Quality-and-Measurement-Failure.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

