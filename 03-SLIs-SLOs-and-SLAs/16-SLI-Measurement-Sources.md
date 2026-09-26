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

