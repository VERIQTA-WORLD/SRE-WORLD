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

## Aggregate Counts, Not Percentages

To combine segments, sum their good and valid counts:

$$
Global\ SLI = \frac{\sum_i G_i}{\sum_i V_i}
$$

Do not average segment percentages unless equal weighting is explicitly intended.

Example:

- Region A: 999,000 of 1,000,000 good, or 99.9 percent.
- Region B: 8,000 of 10,000 good, or 80 percent.

Unweighted average is 89.95 percent, which understates global traffic performance. Count-weighted global result is:

$$
\frac{1{,}007{,}000}{1{,}010{,}000} \approx 99.703\%
$$

The global figure then hides severe harm in Region B. Both views matter.

## Choose Segments by Decision

Segment when a population has distinct harm, commitment, architecture, or action. Common dimensions include region, operation, customer tier, client version, dependency path, payload class, and accessibility mode.

Avoid unbounded combinations. High cardinality creates noisy, sparse results and makes ownership unclear. Define a primary global SLI, mandatory segments, exploratory diagnostics, and minimum-volume rules.

## Simpson's Paradox

An aggregate trend can improve while every segment worsens if traffic shifts toward a naturally healthier segment. Always compare mix changes when global results move unexpectedly.

## Weighting by Value or Risk

Traffic weighting represents the average event. Equal segment weighting represents the average segment. Business or risk weighting represents an explicit policy choice. Never hide the weights. Publish the unweighted counts and explain why the weighted measure supports the decision.

## Small Populations

Low volume increases variability but does not erase harm. Use longer observation periods, confidence intervals, exact counts, or event review. Do not merge a protected premium or safety-sensitive segment into global traffic merely to stabilize the percentage.

## Segment Lifecycle

Segments should be governed like other measurement definitions. Add a mandatory segment when evidence shows distinct user harm, commitments, architecture, or operational action. Remove one only when the distinction no longer affects decisions and historical reporting remains interpretable.

For every segment, record:

- business or user reason;
- classification field and authoritative source;
- whether membership is mutually exclusive;
- minimum reporting volume;
- separate target, if any;
- owner and review trigger;
- privacy and cardinality limits.

## Worked Mix-Shift Example

In Week 1, mobile traffic has 98 percent success across 100,000 events and web has 99.9 percent across 900,000. In Week 2, both segments worsen: mobile falls to 97.5 percent and web to 99.8 percent. However, traffic shifts so web now represents 99 percent of demand. The global percentage can improve despite both experiences worsening.

The correct review compares segment attainment and traffic mix. Global improvement does not establish system improvement when population composition changes.

## Weighting Review Questions

Before approving a weighted measure, ask whether the weight represents event volume, equal consumer groups, revenue, harm, or another policy. State who approved that value judgment. Retain raw counts so another reviewer can calculate alternative views. Never allow a favorable weighting choice to erase a failed protected segment.

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
