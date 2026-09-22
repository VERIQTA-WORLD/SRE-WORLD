# Service Ownership Acceptance Criteria

> Define the evidence a team must provide before it can credibly accept accountability for a production service.

## Section Purpose

Define the evidence a team must provide before it can credibly accept accountability for a production service.

Strong service ownership requires explicit outcomes, boundaries, accountable teams, authority, evidence, and review. A name in a catalog is not enough. The ownership arrangement must continue to work during change, failure, leave, reorganization, recovery, and retirement.

The practical output is a **Service-ownership acceptance record**.

This section defines the acceptance gate. It does not repeat production-readiness engineering or the detailed onboarding workflow in Section 17.

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
8. Produce and verify a complete Service-ownership acceptance record.

---

## 1. Acceptance purpose

Acceptance prevents ownership from being assigned to a team that lacks knowledge, access, authority, staffing, or evidence.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 2. Service understanding

The team must understand purpose, users, boundary, critical journeys, classification, criticality, and lifecycle state.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 3. Technical knowledge

The team should understand architecture, runtime, data, dependencies, failure modes, configuration, and change mechanisms.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 4. Operational capability

Required dashboards, alerts, runbooks, support routes, access, deployment, rollback, and recovery procedures must exist.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 5. Authority

The team must be able to influence reliability work, changes, capacity, incidents, recovery, and retirement.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 6. Continuity

Knowledge and access must not depend on one person.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 7. Known risk

Open risks, exceptions, unsupported conditions, debt, and remediation commitments must be visible.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 8. Support and recovery

Coverage, escalation, restore capability, and validation responsibilities must match criticality.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 9. Evidence quality

Acceptance uses demonstrations, exercises, records, and direct checks rather than verbal assurance alone.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 10. Conditional acceptance

Unmet criteria may receive time-bounded conditions, named risk ownership, and explicit restrictions.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 11. Core Principles

- Acceptance is explicit
- Evidence replaces assumption
- Criticality sets rigor
- Authority accompanies accountability
- Known gaps remain visible
- Conditions have owners and dates
- Rejection protects production
- Acceptance is reviewed after material change

---

## 12. Operating Workflow

1. Confirm service identity and scope
2. Assess each acceptance domain
3. Demonstrate operational capabilities
4. Record gaps and residual risk
5. Decide accept, conditionally accept, or reject
6. Obtain authorized approvals
7. Track conditions to closure
8. Schedule post-acceptance review

The workflow should be proportionate to service criticality. High-consequence services require stronger evidence, more independent review, more frequent verification, and clearer escalation.

---

## 13. Required Evidence

Useful evidence includes:

- Acceptance checklist
- Capability demonstration
- Access verification
- Recovery exercise
- Risk register
- Conditional-acceptance decision
- Team acknowledgement

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

A team is asked to accept a legacy service but cannot deploy, lacks recovery access, and depends on a former employee's notes. The service receives conditional temporary ownership with change restrictions while access, documentation, and recovery evidence are rebuilt.

### Analysis Questions

1. What service or user outcome is at risk?
2. Which team is accountable for that outcome?
3. Which supporting owners must act?
4. Which decision rights are required?
5. What should happen immediately?
6. What evidence proves recovery?
7. Which durable correction prevents recurrence?

---

## 16. Practical Output: Service-ownership acceptance record

Create a record containing:

- Service scope and tier:
- Receiving team:
- Acceptance domains:
- Evidence reviewed:
- Unmet criteria:
- Risk and consequence:
- Conditions and restrictions:
- Remediation owners and dates:
- Decision and authority:
- Effective and review dates:

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

- Completed Service-ownership acceptance record
- Owner acceptance
- Verification result
- Scenario analysis
- Open-gap register
- Corrective-action plan

---

## 18. Review Checklist

- [ ] Service scope and tier is complete, current, and supported by evidence.
- [ ] Receiving team is complete, current, and supported by evidence.
- [ ] Acceptance domains is complete, current, and supported by evidence.
- [ ] Evidence reviewed is complete, current, and supported by evidence.
- [ ] Unmet criteria is complete, current, and supported by evidence.
- [ ] Risk and consequence is complete, current, and supported by evidence.
- [ ] Conditions and restrictions is complete, current, and supported by evidence.
- [ ] Remediation owners and dates is complete, current, and supported by evidence.
- [ ] Decision and authority is complete, current, and supported by evidence.
- [ ] Effective and review dates is complete, current, and supported by evidence.

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

1. Explain acceptance purpose and identify the evidence that would prove it works.
2. Explain service understanding and identify the evidence that would prove it works.
3. Explain technical knowledge and identify the evidence that would prove it works.
4. Explain operational capability and identify the evidence that would prove it works.
5. Explain authority and identify the evidence that would prove it works.
6. Explain continuity and identify the evidence that would prove it works.
7. Explain known risk and identify the evidence that would prove it works.
8. Explain support and recovery and identify the evidence that would prove it works.
9. Explain evidence quality and identify the evidence that would prove it works.
10. Explain conditional acceptance and identify the evidence that would prove it works.

---

## 20. Knowledge Check Answers

1. Acceptance prevents ownership from being assigned to a team that lacks knowledge, access, authority, staffing, or evidence.
2. The team must understand purpose, users, boundary, critical journeys, classification, criticality, and lifecycle state.
3. The team should understand architecture, runtime, data, dependencies, failure modes, configuration, and change mechanisms.
4. Required dashboards, alerts, runbooks, support routes, access, deployment, rollback, and recovery procedures must exist.
5. The team must be able to influence reliability work, changes, capacity, incidents, recovery, and retirement.
6. Knowledge and access must not depend on one person.
7. Open risks, exceptions, unsupported conditions, debt, and remediation commitments must be visible.
8. Coverage, escalation, restore capability, and validation responsibilities must match criticality.
9. Acceptance uses demonstrations, exercises, records, and direct checks rather than verbal assurance alone.
10. Unmet criteria may receive time-bounded conditions, named risk ownership, and explicit restrictions.

---

## 21. Key Takeaways

- Define the evidence a team must provide before it can credibly accept accountability for a production service.
- Ownership is defined by outcomes and obligations, not labels.
- One accountable team remains answerable for each defined scope.
- Supporting ownership must connect through explicit interfaces.
- Authority, access, knowledge, staffing, and evidence make ownership credible.
- Criticality determines the rigor of verification and review.
- Unknowns, exceptions, and temporary arrangements remain visible.
- Production recovery is complete only when the required outcome is verified.
- Ownership continues through organizational and lifecycle change.
- The Service-ownership acceptance record turns the section into an inspectable production artifact.

---

## Navigation

[Previous: Support Coverage and Escalation Ownership](./15-Support-Coverage-and-Escalation-Ownership.md)

[Next: Onboarding a Service Into Ownership](./17-Onboarding-a-Service-Into-Ownership.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> Ownership is credible when the organization can identify the outcome, name the accountable team, exercise the authority, inspect the evidence, and recover when the system fails.

