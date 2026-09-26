# SLI, SLO, and SLA Terminology

> Create a precise vocabulary so measurements, targets, agreements, recovery objectives, and business metrics are not confused.

## Section Purpose

Create a precise vocabulary so measurements, targets, agreements, recovery objectives, and business metrics are not confused.

This section defines distinctions. Later sections design the measurements, objectives, and agreements.

The practical output is a **Service-level terminology reference**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain the role of service level in a service-level system.
2. Explain the role of service level indicator in a service-level system.
3. Explain the role of service level objective in a service-level system.
4. Explain the role of service level agreement in a service-level system.
5. Explain the role of events and windows in a service-level system.
6. Explain the role of error budget in a service-level system.
7. Explain the role of kpi, kri, and service level in a service-level system.
8. Explain the role of rto and rpo in a service-level system.

---

## Service level

A service level is the measured quality of service delivered over a defined scope and period. It is incomplete without the behavior, population, calculation, and window.

---

## Service Level Indicator

An SLI is a carefully specified quantitative measure of service behavior. CPU utilization can inform diagnosis, but it is not automatically an SLI because it may not represent user success.

---

## Service Level Objective

An SLO is a target or acceptable range for an SLI over a compliance period. It is an internal reliability objective used to guide decisions.

---

## Service Level Agreement

An SLA is an agreement containing one or more service commitments, measurement rules, responsibilities, and consequences. An SLA may contain SLO-like terms, but not every SLO is contractual.

---

## Events and windows

A valid event belongs in the evaluated population. A good event meets the defined criteria. A bad event does not. A measurement window determines which events or periods enter a calculation. A compliance period determines when an objective or commitment is assessed.

---

## Error budget

An error budget is the permitted unreliability implied by an SLO. For a 99.9 percent objective, the theoretical bad-event allowance is 0.1 percent of valid events. Policy about how to use that allowance is separate.

---

## KPI, KRI, and service level

A KPI measures progress toward a business or operational goal. A KRI signals risk exposure. Either may use service-level data, but neither is automatically an SLI. The concepts overlap only when their definitions and decision purposes align.

---

## RTO and RPO

A Recovery Time Objective limits acceptable restoration time after disruption. A Recovery Point Objective limits acceptable data loss measured in time or another unit. They are recovery objectives, not substitutes for continuous SLOs.

---

## OLA and support commitment

An Operational Level Agreement coordinates internal responsibilities that support a service commitment. A response-time promise describes support behavior. Neither proves the user-facing service level unless explicitly connected to it.

---

## Common category errors

An SLO is not an alert threshold, an SLA is not a dashboard, an SLI is not every metric, and a target is not evidence. Precise language prevents different teams from agreeing to different things using the same acronym.


---

## Production Scenario

A contract says “99.9 percent uptime,” the operations dashboard shows CPU, and the team calls a five-minute paging threshold its SLO. The terms must be separated before the commitment can be measured.

### Analysis Questions

1. Which user outcome is at risk?
2. What is the correct measurement population and boundary?
3. Which evidence is authoritative?
4. Which assumption could make the result misleading?
5. Who owns the indicator and decision?
6. What immediate correction is required?
7. How will the corrected design be verified?

---

## Practical Output: Service-level terminology reference

Create a record containing:

- Term:
- Working definition:
- Example:
- Common confusion:
- Owner or authority:
- Related section:

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

- Create a precise vocabulary so measurements, targets, agreements, recovery objectives, and business metrics are not confused.
- A percentage without a precise population, calculation, window, and owner is not a trustworthy service level.
- User-visible outcomes take priority over convenient infrastructure signals.
- Unknown and excluded events require explicit treatment.
- Every service-level artifact needs validation and lifecycle control.

---

## Navigation

[Previous: Service Level Engineering](./01-Service-Level-Engineering.md)

[Next: From Critical User Journeys to Service Levels](./03-From-Critical-User-Journeys-to-Service-Levels.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

