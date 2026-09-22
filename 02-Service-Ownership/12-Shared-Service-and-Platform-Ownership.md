# Shared Service and Platform Ownership

> Define ownership where one platform or shared service supports many consuming teams with different risks and operating needs.

## Section Purpose

Define ownership where one platform or shared service supports many consuming teams with different risks and operating needs.

Strong service ownership requires explicit outcomes, boundaries, accountable teams, authority, evidence, and review. A name in a catalog is not enough. The ownership arrangement must continue to work during change, failure, leave, reorganization, recovery, and retirement.

The practical output is a **Shared-service ownership agreement**.

This section focuses on provider-consumer ownership for shared services. It does not repeat dependency records, control-plane engineering, or platform product design.

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
8. Produce and verify a complete Shared-service ownership agreement.

---

## 1. Shared capability

A shared service supplies a reusable capability to several consumers and therefore creates both economies of scale and concentration risk.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 2. Provider accountability

The provider owns the platform outcome, supported interfaces, platform reliability, capacity, security baseline, change communication, and lifecycle.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 3. Consumer accountability

Consumers own correct use, workload behavior, service-specific configuration, application recovery, and the user consequences of integration.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 4. Service boundaries

Separate the platform boundary from each consuming service boundary so incidents and changes have clear owners.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 5. Consumer tiers

A platform may serve consumers with different criticality. Support and design commitments must state which tiers are supported.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 6. Guardrails

Platforms may enforce safe defaults and policies while providing controlled exception and escalation paths.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 7. Change management

Provider changes require impact analysis, compatibility policy, preview, communication, adoption windows, and rollback.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 8. Capacity allocation

Shared capacity needs demand visibility, quota ownership, fair allocation, emergency expansion, and contention rules.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 9. Incident coordination

Platform incidents require provider command, consumer-impact reporting, cross-team communication, and end-to-end validation.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 10. Platform exit

Consumers need migration information, data portability, replacement paths, and retirement timelines.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 11. Core Principles

- The platform is operated as a service
- Provider and consumer outcomes are distinct
- Supported responsibilities are published
- Shared risk is visible
- Consumer criticality influences commitments
- Changes protect compatibility
- Capacity contention has rules
- Platform recovery includes consumer validation

---

## 12. Operating Workflow

1. Define the shared capability and consumers
2. Separate provider and consumer scopes
3. Publish responsibilities and supported tiers
4. Define onboarding and configuration rules
5. Establish capacity, change, and incident interfaces
6. Test shared-failure coordination
7. Measure consumer experience
8. Manage deprecation and exit

The workflow should be proportionate to service criticality. High-consequence services require stronger evidence, more independent review, more frequent verification, and clearer escalation.

---

## 13. Required Evidence

Useful evidence includes:

- Platform service definition
- Consumer agreement
- Supported-tier policy
- Change notice
- Capacity allocation record
- Incident impact map
- Migration plan

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

A shared deployment platform remains available, but a new policy blocks one consumer's releases. The platform owner investigates the policy capability, while the consumer owns application delivery impact and validates its pipeline after correction.

### Analysis Questions

1. What service or user outcome is at risk?
2. Which team is accountable for that outcome?
3. Which supporting owners must act?
4. Which decision rights are required?
5. What should happen immediately?
6. What evidence proves recovery?
7. Which durable correction prevents recurrence?

---

## 16. Practical Output: Shared-service ownership agreement

Create a record containing:

- Provider outcome and owner:
- Eligible consumers:
- Provider obligations:
- Consumer obligations:
- Supported tiers:
- Configuration boundary:
- Capacity and quota rules:
- Change and incident process:
- Evidence and measures:
- Migration and exit:

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

- Completed Shared-service ownership agreement
- Owner acceptance
- Verification result
- Scenario analysis
- Open-gap register
- Corrective-action plan

---

## 18. Review Checklist

- [ ] Provider outcome and owner is complete, current, and supported by evidence.
- [ ] Eligible consumers is complete, current, and supported by evidence.
- [ ] Provider obligations is complete, current, and supported by evidence.
- [ ] Consumer obligations is complete, current, and supported by evidence.
- [ ] Supported tiers is complete, current, and supported by evidence.
- [ ] Configuration boundary is complete, current, and supported by evidence.
- [ ] Capacity and quota rules is complete, current, and supported by evidence.
- [ ] Change and incident process is complete, current, and supported by evidence.
- [ ] Evidence and measures is complete, current, and supported by evidence.
- [ ] Migration and exit is complete, current, and supported by evidence.

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

1. Explain shared capability and identify the evidence that would prove it works.
2. Explain provider accountability and identify the evidence that would prove it works.
3. Explain consumer accountability and identify the evidence that would prove it works.
4. Explain service boundaries and identify the evidence that would prove it works.
5. Explain consumer tiers and identify the evidence that would prove it works.
6. Explain guardrails and identify the evidence that would prove it works.
7. Explain change management and identify the evidence that would prove it works.
8. Explain capacity allocation and identify the evidence that would prove it works.
9. Explain incident coordination and identify the evidence that would prove it works.
10. Explain platform exit and identify the evidence that would prove it works.

---

## 20. Knowledge Check Answers

1. A shared service supplies a reusable capability to several consumers and therefore creates both economies of scale and concentration risk.
2. The provider owns the platform outcome, supported interfaces, platform reliability, capacity, security baseline, change communication, and lifecycle.
3. Consumers own correct use, workload behavior, service-specific configuration, application recovery, and the user consequences of integration.
4. Separate the platform boundary from each consuming service boundary so incidents and changes have clear owners.
5. A platform may serve consumers with different criticality. Support and design commitments must state which tiers are supported.
6. Platforms may enforce safe defaults and policies while providing controlled exception and escalation paths.
7. Provider changes require impact analysis, compatibility policy, preview, communication, adoption windows, and rollback.
8. Shared capacity needs demand visibility, quota ownership, fair allocation, emergency expansion, and contention rules.
9. Platform incidents require provider command, consumer-impact reporting, cross-team communication, and end-to-end validation.
10. Consumers need migration information, data portability, replacement paths, and retirement timelines.

---

## 21. Key Takeaways

- Define ownership where one platform or shared service supports many consuming teams with different risks and operating needs.
- Ownership is defined by outcomes and obligations, not labels.
- One accountable team remains answerable for each defined scope.
- Supporting ownership must connect through explicit interfaces.
- Authority, access, knowledge, staffing, and evidence make ownership credible.
- Criticality determines the rigor of verification and review.
- Unknowns, exceptions, and temporary arrangements remain visible.
- Production recovery is complete only when the required outcome is verified.
- Ownership continues through organizational and lifecycle change.
- The Shared-service ownership agreement turns the section into an inspectable production artifact.

---

## Navigation

[Previous: Dependency Ownership](./11-Dependency-Ownership.md)

[Next: End-to-End Journey Ownership](./13-End-to-End-Journey-Ownership.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> Ownership is credible when the organization can identify the outcome, name the accountable team, exercise the authority, inspect the evidence, and recover when the system fails.

