# Latency SLIs

> Measure whether a service delivers a correct or acceptable outcome within the time it remains useful to the user.

## Section Purpose

Measure whether a service delivers a correct or acceptable outcome within the time it remains useful to the user.

This section defines latency indicators. Performance diagnosis and capacity engineering remain separate disciplines.

The practical output is a **Latency SLI specification**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain the role of choose the interval in a service-level system.
2. Explain the role of end-to-end versus server time in a service-level system.
3. Explain the role of threshold-based sli in a service-level system.
4. Explain the role of multiple thresholds in a service-level system.
5. Explain the role of failures and latency in a service-level system.
6. Explain the role of queue and asynchronous delay in a service-level system.
7. Explain the role of tail behavior in a service-level system.
8. Explain the role of clock integrity in a service-level system.

---

## Choose the interval

Latency may begin at user action, client send, edge receipt, server receipt, queue entry, or job trigger. It may end at first byte, full response, durable commit, or visible completion.

---

## End-to-end versus server time

Server duration excludes client, network, edge, queue, and downstream delays. It is useful for diagnosis but may not represent the user experience.

---

## Threshold-based SLI

Classify a valid event as good when a successful outcome completes within a defined threshold. This produces a ratio that fits SLO and error-budget calculations.

---

## Multiple thresholds

A service may require 90 percent within 200 ms and 99 percent within one second. Each threshold protects a different part of the distribution and must have a clear decision purpose.

---

## Failures and latency

A failed fast request is not a good latency event merely because it is quick. Define whether latency applies only to successful events and maintain a separate availability or correctness SLI.

---

## Queue and asynchronous delay

For queued work, measure acceptance-to-completion or event-time-to-availability. Broker delay alone is a component indicator, not necessarily the journey outcome.

---

## Tail behavior

A healthy median can coexist with severe harm at p99. Protect the population whose delay matters rather than relying on one average.

---

## Clock integrity

Distributed timestamps introduce skew, timezone, precision, and ordering problems. Prefer duration recorded from one clock when possible and validate negative or impossible values.

---

## Calculation example

If 9,700 of 10,000 valid successful requests complete within 300 ms, the threshold SLI is 97 percent. This does not state the p97 latency and should not be described as a percentile.


---

## Production Scenario

Average latency remains 120 ms, but five percent of users wait more than eight seconds. The average is mathematically correct and operationally misleading.

### Analysis Questions

1. Which user outcome is at risk?
2. What is the correct measurement population and boundary?
3. Which evidence is authoritative?
4. Which assumption could make the result misleading?
5. Who owns the indicator and decision?
6. What immediate correction is required?
7. How will the corrected design be verified?

---

## Practical Output: Latency SLI specification

Create a record containing:

- Start event:
- End event:
- Population:
- Success dependency:
- Thresholds:
- Clock source:
- Timeout treatment:
- Asynchronous completion:
- Segmentation:
- Validation cases:

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

- Measure whether a service delivers a correct or acceptable outcome within the time it remains useful to the user.
- A percentage without a precise population, calculation, window, and owner is not a trustworthy service level.
- User-visible outcomes take priority over convenient infrastructure signals.
- Unknown and excluded events require explicit treatment.
- Every service-level artifact needs validation and lifecycle control.

---

## Navigation

[Previous: Availability SLIs](./08-Availability-SLIs.md)

[Next: Correctness SLIs](./10-Correctness-SLIs.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

