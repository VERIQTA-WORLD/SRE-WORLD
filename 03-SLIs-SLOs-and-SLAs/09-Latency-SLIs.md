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

## Latency Is an Event Distribution

Latency is not one number. Every valid event produces an elapsed time, creating a distribution. Users experience individual events, not the average of the distribution.

For event $i$:

$$
Latency_i = EndTime_i - StartTime_i
$$

The start and end must represent the service claim. Server handler time excludes network and client work. End-to-end completion may include queues, retries, rendering, or downstream effects.

## Threshold-Based Latency SLIs

A threshold SLI asks what proportion of valid events complete within a useful time:

$$
Latency\ SLI_t = \frac{Count(Latency_i \le t)}{Valid\ Events}
$$

Example with two thresholds:

- 99 percent of valid reads complete within 300 ms;
- 99.9 percent complete within 1 s.

The first protects the common experience. The second limits the slow tail. Both use the same valid population unless explicitly stated otherwise.

## Include Failures and Timeouts

Calculating latency only for successful responses creates survivorship bias. A request that times out after 30 seconds disappears from the latency distribution even though it caused the worst experience.

Options include:

- count timeouts as failing every relevant latency threshold;
- publish latency and availability as separate SLIs using the same population;
- define a compound good event that requires both success and timeliness.

Never report successful-request latency as though it describes every valid attempt.

## Start and End Points

| Claim | Start | End |
| --- | --- | --- |
| Server processing latency | request accepted by handler | response leaves handler |
| Edge response latency | request reaches edge | final response leaves edge |
| Client-perceived latency | client initiates action | usable result appears |
| Queue completion latency | event accepted | promised effect committed |
| Batch timeliness | scheduled or source-ready time | validated output available |

Clock synchronization matters when start and end occur on different systems. Prefer monotonic clocks within one process. For distributed events, record clock uncertainty or use a common event-time model.

## Histograms and Bucket Design

Histograms support aggregatable latency measurement. Bucket boundaries should surround meaningful thresholds and preserve useful tail detail.

If the SLO threshold is 500 ms but buckets are `100 ms`, `1 s`, and `10 s`, the exact SLI cannot be reconstructed. Add a 500 ms boundary or calculate from higher-fidelity events.

Buckets should also include the timeout boundary. Changing buckets can break historical comparability and requires version control.

## Worked Example

During one hour, 1,000,000 valid search attempts produce:

- 940,000 at or below 200 ms;
- 45,000 from 201 to 500 ms;
- 10,000 from 501 ms to 1 s;
- 3,000 over 1 s;
- 2,000 timeouts.

For the 500 ms threshold:

$$
\frac{940{,}000 + 45{,}000}{1{,}000{,}000} = 98.5\%
$$

For the 1-second threshold:

$$
\frac{940{,}000 + 45{,}000 + 10{,}000}{1{,}000{,}000} = 99.5\%
$$

Timeouts remain in the denominator and fail both thresholds. Reporting a 220 ms mean would conceal 15,000 attempts that exceed one second or never complete.

## Segment Before Concluding

Latency commonly differs by:

- region and network path;
- operation type;
- request or payload size;
- cache hit or miss;
- customer tier;
- client version;
- load band;
- dependency path.

Segment only when the difference supports a decision. Preserve the global reconciliation so segments do not become separate, inconsistent populations.

## Coordinated Omission

Load generators can under-sample slow periods when each virtual user waits for the prior response before sending the next request. Real demand may continue arriving while the service is stalled. This coordinated omission makes latency appear better.

Use an arrival model that represents intended demand, or correct the analysis. Document whether tests measure closed-loop concurrency or open-loop arrival rate.

## Latency Validation

Test exact threshold values, timeouts, cancellation, retries, clock skew, queue delay, missing end events, large payloads, regional delay, and histogram overflow. Confirm that a known slow user event appears in the correct bucket and denominator.

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
