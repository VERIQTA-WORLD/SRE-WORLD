# Service Boundaries and Measurement Boundaries

> Choose where service behavior should be observed so the indicator represents the intended user experience.

## Section Purpose

Choose where service behavior should be observed so the indicator represents the intended user experience.

Service boundaries were defined in Service Ownership. This section uses those boundaries while deciding where evidence is collected.

The practical output is a **Service-level measurement boundary record**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain the role of two different boundaries in a service-level system.
2. Explain the role of client-side measurement in a service-level system.
3. Explain the role of edge measurement in a service-level system.
4. Explain the role of server-side measurement in a service-level system.
5. Explain the role of end-to-end measurement in a service-level system.
6. Explain the role of provider and consumer views in a service-level system.
7. Explain the role of control and data planes in a service-level system.
8. Explain the role of third-party and shared boundaries in a service-level system.

---

## Two different boundaries

The service boundary defines accountability and included behavior. The measurement boundary defines where an observation is made. They may align, but they solve different problems.

---

## Client-side measurement

Client measurements include network, edge, rendering, local retries, and final user-visible outcome. They are close to experience but may be sampled, delayed, privacy-sensitive, or unavailable for some clients.

---

## Edge measurement

Load balancers, gateways, and CDN edges see externally received traffic and response behavior. They may miss client-side failures before arrival and semantic failure after a response.

---

## Server-side measurement

Application instrumentation offers rich classification and ownership context. It can overstate success when traffic never arrives or the application records success before downstream completion.

---

## End-to-end measurement

Journey-level evidence follows work from trigger to durable outcome. It best represents multi-service behavior but requires correlation, ownership, and careful treatment of delayed completion.

---

## Provider and consumer views

A provider can measure its interface correctly while a consumer remains unable to complete the journey. Both views may be necessary, with separate ownership and decisions.

---

## Control and data planes

A control-plane action can be rarely used but critical. Its measurement population, latency, and failure consequences differ from the data plane it manages.

---

## Third-party and shared boundaries

When data comes from a vendor or platform, record which layer is measured, who controls the query, how disputes are resolved, and which failures remain invisible.

---

## Choosing the boundary

Prefer the point closest to user-visible success that remains accurate, available, affordable, and governable. When no single source is sufficient, define corroborating indicators and limitations.


---

## Production Scenario

The API server reports 99.99 percent success, but a mobile client version cannot parse the response. Server-side measurement is accurate for the API boundary and wrong for the complete user journey.

### Analysis Questions

1. Which user outcome is at risk?
2. What is the correct measurement population and boundary?
3. Which evidence is authoritative?
4. Which assumption could make the result misleading?
5. Who owns the indicator and decision?
6. What immediate correction is required?
7. How will the corrected design be verified?

---

## Practical Output: Service-level measurement boundary record

Create a record containing:

- Service and journey:
- Service boundary reference:
- Candidate points:
- Selected point:
- User experience represented:
- Blind spots:
- Source owner:
- Privacy and cost:
- Corroborating evidence:
- Review trigger:

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

- Choose where service behavior should be observed so the indicator represents the intended user experience.
- A percentage without a precise population, calculation, window, and owner is not a trustworthy service level.
- User-visible outcomes take priority over convenient infrastructure signals.
- Unknown and excluded events require explicit treatment.
- Every service-level artifact needs validation and lifecycle control.

---

## Navigation

[Previous: From Critical User Journeys to Service Levels](./03-From-Critical-User-Journeys-to-Service-Levels.md)

[Next: Anatomy of an SLI Specification](./05-Anatomy-of-an-SLI-Specification.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

