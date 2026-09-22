# Ownership Dimensions

> Separate the different outcomes, assets, controls, and operating capabilities that teams may own while preserving one accountable owner for the complete service outcome.

## Section Purpose

Separate the different outcomes, assets, controls, and operating capabilities that teams may own while preserving one accountable owner for the complete service outcome.

Strong service ownership requires explicit outcomes, boundaries, accountable teams, authority, evidence, and review. A name in a catalog is not enough. The ownership arrangement must continue to work during change, failure, leave, reorganization, recovery, and retirement.

The practical output is a **Ownership-dimensions matrix**.

This section maps ownership dimensions. It does not define detailed decision authority, catalog schemas, dependency contracts, support rotations, or governance metrics.

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
8. Produce and verify a complete Ownership-dimensions matrix.

---

## 1. Service outcome

The service-outcome owner remains answerable for the result experienced by users or dependent systems. That team coordinates the other dimensions even when it does not operate every supporting component.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 2. Source code

Code ownership covers maintenance, review, testing, vulnerability correction, release compatibility, and retirement of source artifacts. Repository ownership alone does not prove ownership of a running service.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 3. Runtime

Runtime ownership covers deployed processes, workload health, execution access, deployment state, rollback, and safe production intervention.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 4. Infrastructure

Infrastructure ownership covers compute, network, storage, clusters, accounts, DNS, and shared foundations. The infrastructure owner is not automatically accountable for application correctness.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 5. Configuration

Configuration ownership identifies authoritative sources, review rules, override authority, drift detection, rollback, and expiry of emergency changes.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 6. Data

Data ownership covers purpose, classification, integrity, access, retention, correction, deletion, and disposition. It differs from database administration and platform operation.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 7. Dependencies

The consuming team owns the decision to depend on another capability, correct integration, failure handling, impact detection, escalation, and exit planning.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 8. Security controls

Control owners operate defined controls. Service owners remain responsible for correct integration, applicable requirements, exceptions, and service-specific consequences.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 9. Capacity and cost

Capacity and cost require connected ownership across demand forecasting, provisioning, quotas, financial approval, allocation, anomaly response, and recovery headroom.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 10. Documentation and support

Documentation owners preserve authoritative knowledge. Support owners manage intake, triage, communication, and escalation without automatically owning the service outcome.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 11. Recovery and compliance evidence

Recovery ownership covers restoration and validation of the service outcome. Evidence ownership covers production, custody, review, retention, and retrieval of compliance records.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 12. Service lifecycle

Lifecycle ownership preserves accountability from proposal and production acceptance through maintenance, deprecation, retirement, and archival.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 13. Core Principles

- One accountable owner for every defined scope
- Service-outcome accountability remains visible
- Supporting owners have explicit boundaries
- Authority matches the assigned obligation
- Interfaces connect consumer and provider owners
- Evidence proves that ownership works
- Gaps and overlaps receive corrective action
- Ownership changes with controlled lifecycle transitions

---

## 14. Operating Workflow

1. Define the service outcome and boundary
2. List all applicable ownership dimensions
3. Name one accountable team for each scope
4. Record responsible and contributing parties
5. Define interfaces, authority, evidence, and escalation
6. Test the matrix against a realistic failure
7. Resolve gaps, overlaps, and disputed scopes
8. Approve and schedule review

The workflow should be proportionate to service criticality. High-consequence services require stronger evidence, more independent review, more frequent verification, and clearer escalation.

---

## 15. Required Evidence

Useful evidence includes:

- Accepted owner for every applicable dimension
- Authoritative repository, runtime, configuration, and data records
- Dependency and security-control interfaces
- Capacity and cost decision records
- Support and recovery evidence
- Lifecycle and compliance-evidence custody

Evidence should show what happened, who accepted it, when it was verified, and what remains unresolved.

---

## 16. Common Failure Modes

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

## 17. Production Scenario

A checkout service runs on a shared platform. The platform team restores a failed cluster, the database team restores storage, and the checkout team validates that customers can place correct orders. Component owners restore their scopes, while the checkout team remains accountable for the user outcome.

### Analysis Questions

1. What service or user outcome is at risk?
2. Which team is accountable for that outcome?
3. Which supporting owners must act?
4. Which decision rights are required?
5. What should happen immediately?
6. What evidence proves recovery?
7. Which durable correction prevents recurrence?

---

## 18. Practical Output: Ownership-dimensions matrix

Create a record containing:

- Service identifier and outcome:
- Dimension and defined scope:
- Accountable team:
- Responsible roles and contributors:
- Authority reference:
- Contact and escalation route:
- Required evidence:
- Status and last verification:
- Gap, exception, or dispute:
- Review trigger and next review:

Do not mark an unknown field as not applicable. Record the uncertainty, assign an investigator, and set a due date.

---

## 19. Practical Exercise

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

- Completed Ownership-dimensions matrix
- Owner acceptance
- Verification result
- Scenario analysis
- Open-gap register
- Corrective-action plan

---

## 20. Review Checklist

- [ ] Service identifier and outcome is complete, current, and supported by evidence.
- [ ] Dimension and defined scope is complete, current, and supported by evidence.
- [ ] Accountable team is complete, current, and supported by evidence.
- [ ] Responsible roles and contributors is complete, current, and supported by evidence.
- [ ] Authority reference is complete, current, and supported by evidence.
- [ ] Contact and escalation route is complete, current, and supported by evidence.
- [ ] Required evidence is complete, current, and supported by evidence.
- [ ] Status and last verification is complete, current, and supported by evidence.
- [ ] Gap, exception, or dispute is complete, current, and supported by evidence.
- [ ] Review trigger and next review is complete, current, and supported by evidence.

- [ ] One accountable team exists for each defined scope.
- [ ] Supporting teams are recorded without obscuring end-to-end accountability.
- [ ] Authority matches responsibility.
- [ ] Contact and escalation routes were tested.
- [ ] Temporary conditions have expiry dates.
- [ ] Sensitive information is protected.
- [ ] Review triggers are recorded.
- [ ] Open gaps have owners and due dates.

---

## 21. Knowledge Check

1. Explain service outcome and identify the evidence that would prove it works.
2. Explain source code and identify the evidence that would prove it works.
3. Explain runtime and identify the evidence that would prove it works.
4. Explain infrastructure and identify the evidence that would prove it works.
5. Explain configuration and identify the evidence that would prove it works.
6. Explain data and identify the evidence that would prove it works.
7. Explain dependencies and identify the evidence that would prove it works.
8. Explain security controls and identify the evidence that would prove it works.
9. Explain capacity and cost and identify the evidence that would prove it works.
10. Explain documentation and support and identify the evidence that would prove it works.

---

## 22. Knowledge Check Answers

1. The service-outcome owner remains answerable for the result experienced by users or dependent systems. That team coordinates the other dimensions even when it does not operate every supporting component.
2. Code ownership covers maintenance, review, testing, vulnerability correction, release compatibility, and retirement of source artifacts. Repository ownership alone does not prove ownership of a running service.
3. Runtime ownership covers deployed processes, workload health, execution access, deployment state, rollback, and safe production intervention.
4. Infrastructure ownership covers compute, network, storage, clusters, accounts, DNS, and shared foundations. The infrastructure owner is not automatically accountable for application correctness.
5. Configuration ownership identifies authoritative sources, review rules, override authority, drift detection, rollback, and expiry of emergency changes.
6. Data ownership covers purpose, classification, integrity, access, retention, correction, deletion, and disposition. It differs from database administration and platform operation.
7. The consuming team owns the decision to depend on another capability, correct integration, failure handling, impact detection, escalation, and exit planning.
8. Control owners operate defined controls. Service owners remain responsible for correct integration, applicable requirements, exceptions, and service-specific consequences.
9. Capacity and cost require connected ownership across demand forecasting, provisioning, quotas, financial approval, allocation, anomaly response, and recovery headroom.
10. Documentation owners preserve authoritative knowledge. Support owners manage intake, triage, communication, and escalation without automatically owning the service outcome.

---

## 23. Key Takeaways

- Separate the different outcomes, assets, controls, and operating capabilities that teams may own while preserving one accountable owner for the complete service outcome.
- Ownership is defined by outcomes and obligations, not labels.
- One accountable team remains answerable for each defined scope.
- Supporting ownership must connect through explicit interfaces.
- Authority, access, knowledge, staffing, and evidence make ownership credible.
- Criticality determines the rigor of verification and review.
- Unknowns, exceptions, and temporary arrangements remain visible.
- Production recovery is complete only when the required outcome is verified.
- Ownership continues through organizational and lifecycle change.
- The Ownership-dimensions matrix turns the section into an inspectable production artifact.

---

## Navigation

[Previous: Accountable Teams and Named Owners](./06-Accountable-Teams-and-Named-Owners.md)

[Next: Decision Rights and Production Authority](./08-Decision-Rights-and-Production-Authority.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> Ownership is credible when the organization can identify the outcome, name the accountable team, exercise the authority, inspect the evidence, and recover when the system fails.

