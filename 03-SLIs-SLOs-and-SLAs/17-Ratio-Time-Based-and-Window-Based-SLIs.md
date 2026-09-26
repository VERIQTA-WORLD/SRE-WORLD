# Ratio, Time-Based, and Window-Based SLIs

> Choose the calculation form that represents service harm without being distorted by traffic volume, idle periods, or sampling intervals.

## Section Purpose

Choose the calculation form that represents service harm without being distorted by traffic volume, idle periods, or sampling intervals.

This section compares calculation forms. Specific reliability dimensions define what counts as good.

The practical output is a **SLI calculation-method comparison**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain event-based ratio and its effect on service-level accuracy.
2. Explain time-based ratio and its effect on service-level accuracy.
3. Explain window-based ratio and its effect on service-level accuracy.
4. Explain request versus duration and its effect on service-level accuracy.
5. Explain gauge thresholds and its effect on service-level accuracy.
6. Explain empty windows and its effect on service-level accuracy.
7. Explain bursty traffic and its effect on service-level accuracy.
8. Explain consecutive failure and its effect on service-level accuracy.
9. Apply the section to a realistic production service.
10. Produce and verify the required practical artifact.

---

## Event-based ratio

Good valid events divided by total valid events weights every event equally. High-volume periods contribute more observations.

---

## Time-based ratio

Good evaluated time divided by total evaluated time weights duration. Define sampling interval and how partial or unknown intervals are handled.

---

## Window-based ratio

A time window is good when its aggregate behavior meets a rule. This can expose sustained degradation but may hide failures inside a broad window.

---

## Request versus duration

Request-based measurement can hide a long outage during low traffic. Time-based measurement can understate a short high-volume failure.

---

## Gauge thresholds

For continuous state such as backlog age, classify observations or windows relative to a threshold. Avoid averaging away threshold breaches.

---

## Empty windows

No traffic is not automatically good or bad. Define whether the service was expected to receive work and whether independent evidence exists.

---

## Bursty traffic

A burst can consume a large event budget quickly while affecting little clock time. Choose the form that matches user harm.

---

## Consecutive failure

Some services care about the longest continuous failure even when total availability meets target. Add continuity constraints where necessary.

---

## Comparative calculation

Calculate the same incident using request, time, and window methods. The differences reveal what each method values.

---

## Three Calculation Families

### Event Ratio

$$
SLI = \frac{Good\ Events}{Valid\ Events}
$$

Best for identifiable interactions or records. It weights the result by demand.

### Time Ratio

$$
SLI = \frac{Good\ Time}{Eligible\ Time}
$$

Best when the function is continuously required and usability can be sampled meaningfully. Sampling frequency and state detection determine accuracy.

### Good-Window Ratio

$$
SLI = \frac{Good\ Windows}{Eligible\ Windows}
$$

Best when the consumer evaluates the service in periods, but highly sensitive to window size and pass rule.

## Same Incident, Different Results

Assume a 60-minute period with a 5-minute outage during peak load. The service receives 600,000 requests, 150,000 during the outage.

- Request availability: $450{,}000 / 600{,}000 = 75\%$.
- Time availability: $55 / 60 = 91.67\%$.
- Five-minute-window availability: 11 of 12 windows good, or 91.67 percent, if the outage fills one window.
- One-hour-window availability could be 0 percent if a window is good only when every request succeeds.

The calculation family changes meaning. Choose it from how users consume the service and which decision the result supports.

## Sampling Time-Based State

Checking once per minute does not prove the service was available for the whole minute. Short failures can fall between probes. Define observation frequency, failure confirmation, interpolation, partial intervals, and independent probe locations.

## Window Thresholds

A good window might require 99 percent request success within one minute. This creates two thresholds: the per-window threshold and the required proportion of good windows. Document both.

## Low Volume and Empty Windows

Do not automatically label an empty request window good. It contains no evidence about request success. Treat it as not evaluated, or use a separately specified synthetic measure.

## Production Scenario

A service is unavailable for twenty minutes overnight with no requests, then fails 5,000 requests in one peak minute. Request-based and time-based SLIs describe different harm.

### Analysis Questions

1. Which user or consumer outcome matters?
2. Which population and measurement boundary apply?
3. Which evidence should be trusted?
4. What could make the reported value misleading?
5. Which owner has authority to correct the design?
6. What should be changed now?
7. How will the change be verified?

---

## Practical Output: SLI calculation-method comparison

Create a record containing:

- Service pattern:
- Candidate method:
- Formula:
- Traffic weighting:
- Idle treatment:
- Window size:
- Incident examples:
- User harm represented:
- Blind spots:
- Selected method:

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

- Choose the calculation form that represents service harm without being distorted by traffic volume, idle periods, or sampling intervals.
- Convenient telemetry is not automatically reliable evidence.
- Aggregate success must not hide a materially harmed population.
- Measurement failure is itself an operational risk.
- Every material definition or query change requires controlled review.

---

## Navigation

[Previous: SLI Measurement Sources](./16-SLI-Measurement-Sources.md)

[Next: Distributions, Percentiles, and Tail Latency](./18-Distributions-Percentiles-and-Tail-Latency.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)
