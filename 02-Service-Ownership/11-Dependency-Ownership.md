# Dependency Ownership

> Define accountability for selecting, integrating, operating against, escalating, replacing, and exiting service dependencies.

## Section Purpose

Define accountability for selecting, integrating, operating against, escalating, replacing, and exiting service dependencies.

Strong service ownership requires explicit outcomes, boundaries, accountable teams, authority, evidence, and review. A name in a catalog is not enough. The ownership arrangement must continue to work during change, failure, leave, reorganization, recovery, and retirement.

The practical output is a **Dependency ownership record**.

This section focuses on dependency relationships. It does not repeat general service discovery, platform ownership, vendor governance, or data ownership.

---

## Learning Objectives

After completing this section, you should be able to:

1. Define the section's ownership problem in production terms.
2. Distinguish accountability, responsibility, contribution, authority, and evidence.
3. Identify the service outcome and relevant ownership boundaries.
4. Assign one accountable team to every defined scope.
5. Connect supporting teams without creating joint-accountability ambiguity.
6. Identify missing authority, evidence, continuity, and escalation.
7. Apply the model to a realistic production failure.
8. Produce and verify a complete Dependency ownership record.

---

## 1. Dependency relationship

A dependency relationship includes a provider capability, a consuming service, an interface, assumptions, failure behavior, and ownership on both sides.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 2. Consumer ownership

The consumer owns dependency selection, correct use, timeouts, retries, fallback behavior, observability, and user-impact assessment.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 3. Provider ownership

The provider owns the published capability, supported interface, change communication, support route, and defined recovery obligations.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 4. Critical dependencies

Criticality depends on user consequence, concentration, alternatives, failure propagation, and recovery order.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 5. Dependency contracts

Contracts may define interfaces, limits, supported versions, maintenance communication, escalation, and deprecation.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 6. Failure handling

Consumers should define behavior for timeout, partial failure, incorrect response, rate limiting, stale data, and complete unavailability.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 7. Dependency observability

Evidence should distinguish provider health, consumer integration failure, and end-to-end service impact.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 8. Change and deprecation

Providers announce breaking change and retirement. Consumers track adoption and removal before deadlines.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 9. Transitive risk

Material transitive dependencies should be visible when they affect shared failure, recovery, security, or capacity.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 10. Exit planning

High-consequence dependencies need a credible plan for replacement, isolation, degraded operation, or accepted exposure.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 11. Core Principles

- Both provider and consumer have obligations
- The consumer retains service-outcome accountability
- Interfaces are explicit
- Failure assumptions are tested
- Critical dependencies receive stronger controls
- Transitive concentration is visible
- Deprecation is jointly managed
- Exit risk is owned

---

## 12. Operating Workflow

1. Discover direct dependencies
2. Identify provider and consumer owners
3. Classify dependency consequence
4. Document interface and limits
5. Define failure and recovery behavior
6. Establish change and escalation paths
7. Test material dependency failures
8. Review alternatives and exit risk

The workflow should be proportionate to service criticality. High-consequence services require stronger evidence, more independent review, more frequent verification, and clearer escalation.

---

## 13. Required Evidence

Useful evidence includes:

- Dependency register
- Interface contract
- Failure-mode test
- Escalation test
- Version-support record
- Deprecation plan
- Exit decision

Evidence should show what happened, who accepted it, when it was verified, and what remains unresolved.

---

## 14. Common Failure Modes

Watch for:

- A team name recorded without acceptance
- Responsibility assigned without authority
- Several teams described as jointly accountable
- A component owner treated as the service-outcome owner
- Personal knowledge replacing team capability
- Stale contacts or nonexistent teams
- Temporary arrangements without expiry
- Unknown values hidden by empty or misleading fields
- Documentation treated as evidence without testing
- Risk accepted by a person without authority
- Recovery declared complete before the user outcome is verified
- Lifecycle change that leaves ownership behind

---

## 15. Production Scenario

A payment service receives HTTP success from a provider while settlement events are delayed. Provider health appears green, but the consumer journey is failing. The payment owner detects the user consequence, escalates through the dependency route, activates a safe response, and verifies settlement recovery.

### Analysis Questions

1. What service or user outcome is at risk?
2. Which team is accountable for that outcome?
3. Which supporting owners must act?
4. Which decision rights are required?
5. What should happen immediately?
6. What evidence proves recovery?
7. Which durable correction prevents recurrence?

---

## 16. Practical Output: Dependency ownership record

Create a record containing:

- Consumer service and owner:
- Provider capability and owner:
- Interface and supported version:
- Criticality and user consequence:
- Limits and assumptions:
- Failure behavior:
- Observability and evidence:
- Support and escalation:
- Change and deprecation:
- Alternative and exit plan:

Do not mark an unknown field as not applicable. Record the uncertainty, assign an investigator, and set a due date.

---

## 17. Practical Exercise

Choose one real or realistic production service.

1. Define the service outcome and boundary.
2. Identify every owner required by this section.
3. Confirm accountability and authority.
4. Locate or produce the required evidence.
5. Test one normal handoff.
6. Test one production-failure scenario.
7. Record gaps, overlaps, disputes, and exceptions.
8. Assign remediation owners and dates.
9. Obtain acceptance from the accountable team.
10. Schedule the next review.

### Completion Evidence

- Completed Dependency ownership record
- Owner acceptance
- Verification result
- Scenario analysis
- Open-gap register
- Corrective-action plan

---

## 18. Review Checklist

- [ ] Consumer service and owner is complete, current, and supported by evidence.
- [ ] Provider capability and owner is complete, current, and supported by evidence.
- [ ] Interface and supported version is complete, current, and supported by evidence.
- [ ] Criticality and user consequence is complete, current, and supported by evidence.
- [ ] Limits and assumptions is complete, current, and supported by evidence.
- [ ] Failure behavior is complete, current, and supported by evidence.
- [ ] Observability and evidence is complete, current, and supported by evidence.
- [ ] Support and escalation is complete, current, and supported by evidence.
- [ ] Change and deprecation is complete, current, and supported by evidence.
- [ ] Alternative and exit plan is complete, current, and supported by evidence.

- [ ] One accountable team exists for each defined scope.
- [ ] Supporting teams are recorded without obscuring end-to-end accountability.
- [ ] Authority matches responsibility.
- [ ] Contact and escalation routes were tested.
- [ ] Temporary conditions have expiry dates.
- [ ] Sensitive information is protected.
- [ ] Review triggers are recorded.
- [ ] Open gaps have owners and due dates.

---

## 19. Knowledge Check

1. Explain dependency relationship and identify the evidence that would prove it works.
2. Explain consumer ownership and identify the evidence that would prove it works.
3. Explain provider ownership and identify the evidence that would prove it works.
4. Explain critical dependencies and identify the evidence that would prove it works.
5. Explain dependency contracts and identify the evidence that would prove it works.
6. Explain failure handling and identify the evidence that would prove it works.
7. Explain dependency observability and identify the evidence that would prove it works.
8. Explain change and deprecation and identify the evidence that would prove it works.
9. Explain transitive risk and identify the evidence that would prove it works.
10. Explain exit planning and identify the evidence that would prove it works.

---

## 20. Knowledge Check Answers

1. A dependency relationship includes a provider capability, a consuming service, an interface, assumptions, failure behavior, and ownership on both sides.
2. The consumer owns dependency selection, correct use, timeouts, retries, fallback behavior, observability, and user-impact assessment.
3. The provider owns the published capability, supported interface, change communication, support route, and defined recovery obligations.
4. Criticality depends on user consequence, concentration, alternatives, failure propagation, and recovery order.
5. Contracts may define interfaces, limits, supported versions, maintenance communication, escalation, and deprecation.
6. Consumers should define behavior for timeout, partial failure, incorrect response, rate limiting, stale data, and complete unavailability.
7. Evidence should distinguish provider health, consumer integration failure, and end-to-end service impact.
8. Providers announce breaking change and retirement. Consumers track adoption and removal before deadlines.
9. Material transitive dependencies should be visible when they affect shared failure, recovery, security, or capacity.
10. High-consequence dependencies need a credible plan for replacement, isolation, degraded operation, or accepted exposure.

---

## 21. Key Takeaways

- Define accountability for selecting, integrating, operating against, escalating, replacing, and exiting service dependencies.
- Ownership is defined by outcomes and obligations, not labels.
- One accountable team remains answerable for each defined scope.
- Supporting ownership must connect through explicit interfaces.
- Authority, access, knowledge, staffing, and evidence make ownership credible.
- Criticality determines the rigor of verification and review.
- Unknowns, exceptions, and temporary arrangements remain visible.
- Production recovery is complete only when the required outcome is verified.
- Ownership continues through organizational and lifecycle change.
- The Dependency ownership record turns the section into an inspectable production artifact.

---

## Navigation

[Previous: Service Ownership Metadata](./10-Service-Ownership-Metadata.md)

[Next: Shared Service and Platform Ownership](./12-Shared-Service-and-Platform-Ownership.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> Ownership is credible when the organization can identify the outcome, name the accountable team, exercise the authority, inspect the evidence, and recover when the system fails.

