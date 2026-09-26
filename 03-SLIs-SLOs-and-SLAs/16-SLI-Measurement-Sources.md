# SLI Measurement Sources

> Select authoritative measurement evidence that represents user outcomes while making cost, delay, privacy, and control tradeoffs explicit.

## Section Purpose

Select authoritative measurement evidence that represents user outcomes while making cost, delay, privacy, and control tradeoffs explicit.

This section selects evidence sources. It does not teach complete telemetry-platform installation or observability architecture.

The practical output is a **SLI measurement-source decision record**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain client-side evidence and its effect on service-level accuracy.
2. Explain edge and gateway evidence and its effect on service-level accuracy.
3. Explain application metrics and its effect on service-level accuracy.
4. Explain logs and events and its effect on service-level accuracy.
5. Explain distributed traces and its effect on service-level accuracy.
6. Explain synthetic probes and its effect on service-level accuracy.
7. Explain business records and its effect on service-level accuracy.
8. Explain independent evidence and its effect on service-level accuracy.
9. Apply the section to a realistic production service.
10. Produce and verify the required practical artifact.

---

## Client-side evidence

Real-user instrumentation observes client, network, edge, rendering, and final behavior. It can be sampled, blocked, delayed, or privacy-sensitive.

---

## Edge and gateway evidence

Edges see externally received traffic and returned responses. They provide broad coverage but often lack semantic outcome context.

---

## Application metrics

Application counters can classify domain outcomes efficiently. They depend on correct instrumentation and may omit traffic that never reached the service.

---

## Logs and events

Logs and audit events provide detail and can be reprocessed. Parsing changes, loss, duplication, and retention affect trust.

---

## Distributed traces

Traces connect stages and dependencies, but sampling can distort rare failures and tail behavior unless designed carefully.

---

## Synthetic probes

Probes test known paths when real traffic is absent. They may miss user diversity, authorization, data, and client-specific failure.

---

## Business records

Orders, settlements, publications, and downstream acknowledgements can be closest to semantic success, although they arrive later.

---

## Independent evidence

SLAs and high-consequence outcomes may need a source independent of the team being measured. Define dispute and reconciliation rules.

---

## Source decision

Choose the source closest to the outcome that is sufficiently complete, timely, governable, retained, and affordable. Use corroboration when one source cannot satisfy all needs.

---

## Source Selection Is a Boundary Decision

The source determines which failures are visible. Choose it from the claim, not from convenience.

| Source | Strength | Blind spot |
| --- | --- | --- |
| Client telemetry | close to user experience | blocking, sampling, privacy, abandoned clients |
| Edge or load balancer | broad request coverage | semantic failure after response |
| Application logs | rich domain context | pre-arrival and post-response failure |
| Metrics | efficient aggregation | limited event detail and cardinality |
| Traces | path and latency evidence | sampling and incomplete propagation |
| Business records | semantic completion | delayed availability and join complexity |
| Synthetic probes | independent controlled journeys | limited diversity and traffic realism |
| Third-party reports | provider-side evidence | different boundary, delay, and incentives |

## Authoritative and Corroborating Sources

Name one source, or one reconciled dataset, as authoritative for each calculation. Other sources can detect gaps and explain cause. If two sources are co-authoritative, define how disagreements are resolved.

For checkout, edge logs may establish attempts, application events may establish validation, payment records may establish authorization, and order records may establish durable completion. The authoritative dataset is a governed reconciliation of these sources.

## Selection Criteria

Evaluate:

- alignment with the user boundary;
- completeness and sampling;
- semantic accuracy;
- independence from service failure;
- timestamp quality;
- delay and retention;
- deduplication and join keys;
- access, privacy, and cost;
- change control;
- ability to reproduce historical results.

## Source Disagreement

Suppose edge logs show 1,000,000 requests while application logs show 997,000. Possible causes include edge rejection, log loss, sampling, duplicate records, clock boundaries, or application failure before logging. Do not choose the more favorable count. Reconcile the pipeline and classify unresolved difference as coverage uncertainty.

## Source Change

When replacing a source:

1. version the SLI specification;
2. run old and new sources in parallel;
3. explain systematic differences;
4. test known good, bad, excluded, and unknown events;
5. select an effective cutover time;
6. preserve the old implementation for historical reproduction;
7. annotate trend breaks.

## Production Scenario

Application metrics show success, edge logs show timeouts, and business records show missing transactions. The team must identify which source answers which service-level question.

### Analysis Questions

1. Which user or consumer outcome matters?
2. Which population and measurement boundary apply?
3. Which evidence should be trusted?
4. What could make the reported value misleading?
5. Which owner has authority to correct the design?
6. What should be changed now?
7. How will the change be verified?

---

## Practical Output: SLI measurement-source decision record

Create a record containing:

- Candidate source:
- Outcome represented:
- Coverage:
- Delay:
- Sampling:
- Owner:
- Retention:
- Privacy:
- Failure modes:
- Selected use:
- Corroboration:

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

- Select authoritative measurement evidence that represents user outcomes while making cost, delay, privacy, and control tradeoffs explicit.
- Convenient telemetry is not automatically reliable evidence.
- Aggregate success must not hide a materially harmed population.
- Measurement failure is itself an operational risk.
- Every material definition or query change requires controlled review.

---

## Navigation

[Previous: Asynchronous and Event-Driven SLIs](./15-Asynchronous-and-Event-Driven-SLIs.md)

[Next: Ratio, Time-Based, and Window-Based SLIs](./17-Ratio-Time-Based-and-Window-Based-SLIs.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)
