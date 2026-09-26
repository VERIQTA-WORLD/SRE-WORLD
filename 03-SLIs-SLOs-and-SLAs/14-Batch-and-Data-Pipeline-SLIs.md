# Batch and Data Pipeline SLIs

> Design service-level indicators for scheduled, low-frequency, long-running, and multi-stage processing.

## Section Purpose

Design service-level indicators for scheduled, low-frequency, long-running, and multi-stage processing.

This section addresses measurement. Pipeline architecture, orchestration tooling, and detailed recovery procedures remain outside scope.

The practical output is a **Batch or data-pipeline SLI set**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain deadline completion and its effect on service-level accuracy.
2. Explain expected run population and its effect on service-level accuracy.
3. Explain record completeness and its effect on service-level accuracy.
4. Explain correctness and reconciliation and its effect on service-level accuracy.
5. Explain partial success and its effect on service-level accuracy.
6. Explain reruns and backfills and its effect on service-level accuracy.
7. Explain poison records and its effect on service-level accuracy.
8. Explain low frequency and its effect on service-level accuracy.
9. Apply the section to a realistic production service.
10. Produce and verify the required practical artifact.

---

## Deadline completion

For many jobs, the important outcome is successful completion by a business deadline rather than average runtime.

---

## Expected run population

Define which runs should occur. A scheduler that fails to create a run must not remove the failure from the denominator.

---

## Record completeness

A completed job can omit records. Compare expected and processed populations, accounting for legitimate late or rejected input.

---

## Correctness and reconciliation

Validate totals, invariants, balances, or downstream acceptance instead of relying only on exit codes.

---

## Partial success

Define whether a batch with failed partitions is useful, retryable, unsafe, or failed. Preserve affected records and user impact.

---

## Reruns and backfills

A successful rerun may repair the outcome after the deadline. Report both final correctness and deadline performance.

---

## Poison records

One invalid record may block an entire pipeline or be quarantined. Define acceptable isolation and ownership of unresolved records.

---

## Low frequency

A monthly job has too few events for a smooth percentage. Use consecutive-run history, deadline success, and scenario evidence.

---

## Multi-stage behavior

Local stage success can coexist with end-to-end failure. Correlate the business input through final published output.

---

## Production Scenario

A monthly payroll pipeline completes after an automatic rerun, but salaries arrive one day late. Final success does not erase the deadline failure.

### Analysis Questions

1. Which user or consumer outcome matters?
2. Which population and measurement boundary apply?
3. Which evidence should be trusted?
4. What could make the reported value misleading?
5. Which owner has authority to correct the design?
6. What should be changed now?
7. How will the change be verified?

---

## Practical Output: Batch or data-pipeline SLI set

Create a record containing:

- Expected runs:
- Deadline:
- Completion rule:
- Completeness rule:
- Correctness rule:
- Partial-success rule:
- Rerun treatment:
- Late-source treatment:
- End-to-end correlation:
- Business validation:

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

- Design service-level indicators for scheduled, low-frequency, long-running, and multi-stage processing.
- Convenient telemetry is not automatically reliable evidence.
- Aggregate success must not hide a materially harmed population.
- Measurement failure is itself an operational risk.
- Every material definition or query change requires controlled review.

---

## Navigation

[Previous: Durability and Data Integrity SLIs](./13-Durability-and-Data-Integrity-SLIs.md)

[Next: Asynchronous and Event-Driven SLIs](./15-Asynchronous-and-Event-Driven-SLIs.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

