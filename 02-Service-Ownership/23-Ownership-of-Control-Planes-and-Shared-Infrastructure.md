# Ownership of Control Planes and Shared Infrastructure

> Define ownership for high-leverage administrative systems and shared foundations whose failure or misuse can affect many services.

## Section Purpose

Define ownership for high-leverage administrative systems and shared foundations whose failure or misuse can affect many services.

Strong service ownership requires explicit outcomes, boundaries, accountable teams, authority, evidence, and review. A name in a catalog is not enough. The ownership arrangement must continue to work during change, failure, leave, reorganization, recovery, and retirement.

The practical output is a **Control-plane ownership model**.

This section focuses on control planes and shared infrastructure. It does not repeat general platform ownership or teach infrastructure architecture.

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
8. Produce and verify a complete Control-plane ownership model.

---

## 1. Control-plane scope

Control planes include systems that configure, schedule, authorize, route, deploy, or administer production resources.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 2. Data plane distinction

Separate the management path from the path carrying user workload or data.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 3. Administrative authority

Control-plane owners must define privileged actions, approvals, emergency access, logging, and recovery.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 4. Blast radius

Shared control planes can create organization-wide failure through configuration, automation, credentials, or provider outages.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 5. Tenant responsibility

Consumers own workload configuration and safe use within published platform constraints.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 6. Change safety

Control-plane changes need staged rollout, compatibility checks, rollback, blast-radius controls, and consumer communication.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 7. Dependency concentration

Identity, DNS, orchestration, secrets, deployment, and observability control planes may become systemic dependencies.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 8. Recovery

Restore control capability, reconcile desired and actual state, verify workloads, and prevent unsafe automated replay.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 9. Break-glass capability

Emergency paths require tight scope, independent access, audit, expiry, and testing.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 10. Governance

Critical control planes need clear tiering, ownership verification, access review, recovery tests, and retirement planning.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 11. Core Principles

- Control planes are services
- Management and workload paths are distinguished
- Privileged authority is constrained
- Blast radius shapes ownership obligations
- Consumers retain workload responsibility
- Changes are staged
- Recovery reconciles state
- Emergency access is tested

---

## 12. Operating Workflow

1. Inventory control planes and shared foundations
2. Define provider and tenant boundaries
3. Map privileged actions and failure domains
4. Assess systemic criticality
5. Define change, incident, and recovery ownership
6. Test break-glass and restoration
7. Review consumer dependencies
8. Govern access and lifecycle

The workflow should be proportionate to service criticality. High-consequence services require stronger evidence, more independent review, more frequent verification, and clearer escalation.

---

## 13. Required Evidence

Useful evidence includes:

- Control-plane service record
- Privilege map
- Change rollout record
- Consumer agreement
- Break-glass test
- Recovery exercise
- Access review

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

A deployment control plane pushes an invalid configuration to hundreds of services. The platform owner stops propagation and restores the control plane, while service owners validate their runtime state and user outcomes before releases resume.

### Analysis Questions

1. What service or user outcome is at risk?
2. Which team is accountable for that outcome?
3. Which supporting owners must act?
4. Which decision rights are required?
5. What should happen immediately?
6. What evidence proves recovery?
7. Which durable correction prevents recurrence?

---

## 16. Practical Output: Control-plane ownership model

Create a record containing:

- Control-plane capability:
- Provider owner:
- Consumer scopes:
- Administrative authority:
- Failure domains and blast radius:
- Change safeguards:
- Incident coordination:
- Recovery and reconciliation:
- Emergency access:
- Governance evidence:

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

- Completed Control-plane ownership model
- Owner acceptance
- Verification result
- Scenario analysis
- Open-gap register
- Corrective-action plan

---

## 18. Review Checklist

- [ ] Control-plane capability is complete, current, and supported by evidence.
- [ ] Provider owner is complete, current, and supported by evidence.
- [ ] Consumer scopes is complete, current, and supported by evidence.
- [ ] Administrative authority is complete, current, and supported by evidence.
- [ ] Failure domains and blast radius is complete, current, and supported by evidence.
- [ ] Change safeguards is complete, current, and supported by evidence.
- [ ] Incident coordination is complete, current, and supported by evidence.
- [ ] Recovery and reconciliation is complete, current, and supported by evidence.
- [ ] Emergency access is complete, current, and supported by evidence.
- [ ] Governance evidence is complete, current, and supported by evidence.

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

1. Explain control-plane scope and identify the evidence that would prove it works.
2. Explain data plane distinction and identify the evidence that would prove it works.
3. Explain administrative authority and identify the evidence that would prove it works.
4. Explain blast radius and identify the evidence that would prove it works.
5. Explain tenant responsibility and identify the evidence that would prove it works.
6. Explain change safety and identify the evidence that would prove it works.
7. Explain dependency concentration and identify the evidence that would prove it works.
8. Explain recovery and identify the evidence that would prove it works.
9. Explain break-glass capability and identify the evidence that would prove it works.
10. Explain governance and identify the evidence that would prove it works.

---

## 20. Knowledge Check Answers

1. Control planes include systems that configure, schedule, authorize, route, deploy, or administer production resources.
2. Separate the management path from the path carrying user workload or data.
3. Control-plane owners must define privileged actions, approvals, emergency access, logging, and recovery.
4. Shared control planes can create organization-wide failure through configuration, automation, credentials, or provider outages.
5. Consumers own workload configuration and safe use within published platform constraints.
6. Control-plane changes need staged rollout, compatibility checks, rollback, blast-radius controls, and consumer communication.
7. Identity, DNS, orchestration, secrets, deployment, and observability control planes may become systemic dependencies.
8. Restore control capability, reconcile desired and actual state, verify workloads, and prevent unsafe automated replay.
9. Emergency paths require tight scope, independent access, audit, expiry, and testing.
10. Critical control planes need clear tiering, ownership verification, access review, recovery tests, and retirement planning.

---

## 21. Key Takeaways

- Define ownership for high-leverage administrative systems and shared foundations whose failure or misuse can affect many services.
- Ownership is defined by outcomes and obligations, not labels.
- One accountable team remains answerable for each defined scope.
- Supporting ownership must connect through explicit interfaces.
- Authority, access, knowledge, staffing, and evidence make ownership credible.
- Criticality determines the rigor of verification and review.
- Unknowns, exceptions, and temporary arrangements remain visible.
- Production recovery is complete only when the required outcome is verified.
- Ownership continues through organizational and lifecycle change.
- The Control-plane ownership model turns the section into an inspectable production artifact.

---

## Navigation

[Previous: Ownership of Data and State](./22-Ownership-of-Data-and-State.md)

[Next: Operational Knowledge and Documentation Ownership](./24-Operational-Knowledge-and-Documentation-Ownership.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> Ownership is credible when the organization can identify the outcome, name the accountable team, exercise the authority, inspect the evidence, and recover when the system fails.

