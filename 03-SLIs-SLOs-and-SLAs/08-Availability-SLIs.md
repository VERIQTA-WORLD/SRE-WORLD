# Availability SLIs

> Measure whether users can access and successfully use the required service behavior when they need it.

## Section Purpose

Measure whether users can access and successfully use the required service behavior when they need it.

This section designs availability indicators. It does not define incident severity, alerting, or architectural high availability.

The practical output is a **Availability SLI specification**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain the role of usability, not process state in a service-level system.
2. Explain the role of request-based availability in a service-level system.
3. Explain the role of time-based availability in a service-level system.
4. Explain the role of partial availability in a service-level system.
5. Explain the role of graceful degradation in a service-level system.
6. Explain the role of low traffic in a service-level system.
7. Explain the role of status-code limits in a service-level system.
8. Explain the role of maintenance treatment in a service-level system.

---

## Usability, not process state

A running process, healthy pod, or open port does not prove availability. The measurement must represent whether an eligible user can complete the required behavior.

---

## Request-based availability

A common form is successful valid requests divided by total valid requests. Success must include the usable outcome, not merely transport completion.

---

## Time-based availability

For continuously required services, calculate good service time divided by total evaluated time. Define sampling interval, state transition, partial intervals, and missing observations.

---

## Partial availability

A service may fail for one region, tenant, feature, or request type. Global aggregation must not hide materially affected populations.

---

## Graceful degradation

A degraded response may count as good only when it preserves the defined minimum outcome. Record which features may be absent and how users are informed.

---

## Low traffic

A service can be unavailable during a window with no requests. Synthetic evidence, time-based state, or business-schedule evaluation may be needed.

---

## Status-code limits

HTTP codes are proxies. A 200 response can be empty, stale, unauthorized, or semantically wrong. A 4xx response may be correct rejection or a service defect.

---

## Maintenance treatment

Internal SLOs often count planned unavailability because users experience it. An SLA may exclude defined maintenance. Preserve both views when their purposes differ.

---

## Calculation example

If 2,000 valid requests contain 1,990 usable outcomes, availability is 99.5 percent. Ten additional unknown results should not be silently removed; they change confidence and possibly the denominator.


---

## Availability Models

Availability is the proportion of valid demand for which the required function is usable. The correct model depends on how consumers use the service.

### Request-Based Availability

Use when demand arrives as identifiable interactions:

$$
Availability = \frac{Successful\ Valid\ Requests}{All\ Valid\ Requests}
$$

This model weights periods by demand. A one-minute failure during peak traffic counts more heavily than one minute with little traffic.

### Time-Based Availability

Use when service usability is naturally continuous:

$$
Availability = \frac{Total\ Evaluated\ Time - Unavailable\ Time}{Total\ Evaluated\ Time}
$$

Time-based availability gives equal weight to every unit of time unless the specification says otherwise. It can overstate or understate user harm when demand varies sharply.

### Window-Based Availability

Divide time into windows and classify each window as good or bad:

$$
Availability = \frac{Good\ Windows}{Eligible\ Windows}
$$

The result depends heavily on window size and the good-window rule. A single failed request can make an entire minute bad, while a one-hour window can dilute a short but severe interruption.

## Define “Usable” at the Service Boundary

A service is unavailable when a valid consumer cannot obtain the required function. That can include:

- connection failure;
- timeout beyond the usefulness threshold;
- rejected valid request;
- response that cannot be used;
- failure affecting only a required segment;
- ambiguous outcome requiring unsafe retry;
- dependency failure that prevents completion.

Process state is not sufficient. A process can be running while deadlocked, returning stale data, rejecting every request, or producing incorrect results.

## Partial Availability

A service may be available for reads and unavailable for writes, or available in one region and unavailable in another. Do not average unlike operations without showing their populations.

Choose one of these approaches:

- separate SLIs for operations with different user meaning;
- segment one SLI by operation, region, or consumer;
- define one end-to-end good event only when all required functions form one outcome.

An administrative endpoint should not inflate customer availability. Health checks and background traffic usually need separate populations.

## Low-Traffic Periods

Request-based availability produces little evidence when no demand occurs. Zero requests do not prove 100 percent availability. Report “no eligible events” or use an independent synthetic signal for detection. Do not insert synthetic events into the customer SLI unless the specification explicitly defines and justifies their weighting.

## Availability Worked Example

In a 28-day window:

- 12,500,000 eligible requests are observed;
- 12,486,250 succeed;
- 8,750 time out;
- 3,000 return internal errors;
- 2,000 return semantically unusable responses;
- 50,000 malformed requests are excluded;
- 5,000 outcomes are unknown because one edge feed is missing.

Bad events equal:

$$
8{,}750 + 3{,}000 + 2{,}000 = 13{,}750
$$

Recorded availability is:

$$
\frac{12{,}486{,}250}{12{,}500{,}000} = 99.89\%
$$

The malformed requests do not enter the calculation. The unknown outcomes remain visible. If they could be eligible, the team must determine whether uncertainty can change compliance.

## Downtime and “Nines”

For a purely time-based model, approximate unavailable time is:

$$
Allowed\ Unavailable\ Time = Period \times (1 - Target)
$$

For a 30-day period:

| Target | Approximate unavailable time |
| ---: | ---: |
| 99% | 7 h 12 min |
| 99.9% | 43 min 12 sec |
| 99.95% | 21 min 36 sec |
| 99.99% | 4 min 19 sec |

Do not apply this table to a request-based SLO as though every minute has equal traffic. Request error budgets depend on eligible volume.

## Dependency Treatment

If a valid request fails because a required dependency is unavailable, the event is normally bad for the service-level outcome. A separate dependency record can assign cause and support escalation. Cause attribution should not rewrite user experience.

## Availability Test Matrix

Verify the SLI against:

- total service outage;
- one-region outage;
- one-operation outage;
- slow responses beyond timeout;
- syntactically successful but unusable responses;
- dependency failure;
- rejected valid clients;
- missing telemetry;
- no-traffic intervals;
- retry storms.

The SLI should fail exactly where the written availability claim fails.

## Production Scenario

All servers answer health checks, but authentication rejects every valid user in one region. Component availability is green while service availability for that population is zero.

### Analysis Questions

1. Which user outcome is at risk?
2. What is the correct measurement population and boundary?
3. Which evidence is authoritative?
4. Which assumption could make the result misleading?
5. Who owns the indicator and decision?
6. What immediate correction is required?
7. How will the corrected design be verified?

---

## Practical Output: Availability SLI specification

Create a record containing:

- Available behavior:
- Population:
- Measurement point:
- Success rule:
- Failure rule:
- Partial availability:
- Maintenance treatment:
- Low-traffic method:
- Segmentation:
- Calculation and tests:

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

- Measure whether users can access and successfully use the required service behavior when they need it.
- A percentage without a precise population, calculation, window, and owner is not a trustworthy service level.
- User-visible outcomes take priority over convenient infrastructure signals.
- Unknown and excluded events require explicit treatment.
- Every service-level artifact needs validation and lifecycle control.

---

## Navigation

[Previous: Good, Bad, and Total Events](./07-Good-Bad-and-Total-Events.md)

[Next: Latency SLIs](./09-Latency-SLIs.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)
