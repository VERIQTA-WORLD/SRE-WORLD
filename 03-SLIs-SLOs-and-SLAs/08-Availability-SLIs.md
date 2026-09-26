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

