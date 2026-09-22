# Decision Rights and Production Authority

> Define who may decide, approve, act, stop, override, escalate, and accept risk for a production service.

## Section Purpose

Define who may decide, approve, act, stop, override, escalate, and accept risk for a production service.

Strong service ownership requires explicit outcomes, boundaries, accountable teams, authority, evidence, and review. A name in a catalog is not enough. The ownership arrangement must continue to work during change, failure, leave, reorganization, recovery, and retirement.

The practical output is a **Production decision-rights register**.

This section defines authority. It does not design on-call schedules, incident command, change pipelines, or organization-wide governance bodies.

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
8. Produce and verify a complete Production decision-rights register.

---

## 1. Decision rights

A decision right identifies the role authorized to make a defined decision within a stated scope and condition.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 2. Operational authority

Operational authority permits actions such as rollback, traffic shifting, feature disablement, failover, scaling, and emergency access.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 3. Change authority

Normal, high-risk, and emergency changes require different approval and execution boundaries.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 4. Stop authority

Teams need an explicit right to halt unsafe releases, suspend damaging automation, or restrict change when risk exceeds agreed limits.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 5. Risk acceptance

Residual business risk must be accepted by an authorized risk owner, not silently absorbed by an engineer or SRE team.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 6. Delegation

Delegated authority must state the decision, limits, duration, evidence, and revocation conditions.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 7. Emergency authority

Emergency authority should be broad enough to reduce harm and constrained by scope, logging, review, and expiry.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 8. Separation of duties

High-consequence actions may require different initiators, approvers, executors, and reviewers.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 9. Conflict resolution

Conflicting technical, security, product, and business decisions need a named escalation authority.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 10. Authority review

Decision rights must be reviewed after reorganization, criticality change, incidents, access redesign, or service transfer.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 11. Core Principles

- Authority follows accountability
- Scope and conditions are explicit
- Emergency actions remain auditable
- Risk acceptance uses the correct organizational level
- Delegation is time bounded
- Separation of duties matches consequence
- Conflicts have a defined resolver
- Authority is verified before it is needed

---

## 12. Operating Workflow

1. Inventory recurring production decisions
2. Classify each decision by consequence and urgency
3. Name the accountable decision owner
4. Define approvers, executors, consultees, and reviewers
5. Specify normal and emergency conditions
6. Connect access controls to authority
7. Test conflicts and unavailable approvers
8. Review evidence and expiry

The workflow should be proportionate to service criticality. High-consequence services require stronger evidence, more independent review, more frequent verification, and clearer escalation.

---

## 13. Required Evidence

Useful evidence includes:

- Decision-right register
- Approved delegation record
- Access-role mapping
- Emergency-action log
- Risk-acceptance record
- Conflict-escalation outcome

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

During a severe release failure, an SRE can roll back immediately but cannot accept continued data-loss risk. The incident commander authorizes mitigation, the service owner validates recovery, and the business risk owner decides whether degraded operation may continue.

### Analysis Questions

1. What service or user outcome is at risk?
2. Which team is accountable for that outcome?
3. Which supporting owners must act?
4. Which decision rights are required?
5. What should happen immediately?
6. What evidence proves recovery?
7. Which durable correction prevents recurrence?

---

## 16. Practical Output: Production decision-rights register

Create a record containing:

- Decision or action:
- Applicable service scope:
- Normal authority:
- Emergency authority:
- Approval requirement:
- Execution role:
- Conditions and limits:
- Evidence and logging:
- Escalation authority:
- Review and expiry:

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

- Completed Production decision-rights register
- Owner acceptance
- Verification result
- Scenario analysis
- Open-gap register
- Corrective-action plan

---

## 18. Review Checklist

- [ ] Decision or action is complete, current, and supported by evidence.
- [ ] Applicable service scope is complete, current, and supported by evidence.
- [ ] Normal authority is complete, current, and supported by evidence.
- [ ] Emergency authority is complete, current, and supported by evidence.
- [ ] Approval requirement is complete, current, and supported by evidence.
- [ ] Execution role is complete, current, and supported by evidence.
- [ ] Conditions and limits is complete, current, and supported by evidence.
- [ ] Evidence and logging is complete, current, and supported by evidence.
- [ ] Escalation authority is complete, current, and supported by evidence.
- [ ] Review and expiry is complete, current, and supported by evidence.

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

1. Explain decision rights and identify the evidence that would prove it works.
2. Explain operational authority and identify the evidence that would prove it works.
3. Explain change authority and identify the evidence that would prove it works.
4. Explain stop authority and identify the evidence that would prove it works.
5. Explain risk acceptance and identify the evidence that would prove it works.
6. Explain delegation and identify the evidence that would prove it works.
7. Explain emergency authority and identify the evidence that would prove it works.
8. Explain separation of duties and identify the evidence that would prove it works.
9. Explain conflict resolution and identify the evidence that would prove it works.
10. Explain authority review and identify the evidence that would prove it works.

---

## 20. Knowledge Check Answers

1. A decision right identifies the role authorized to make a defined decision within a stated scope and condition.
2. Operational authority permits actions such as rollback, traffic shifting, feature disablement, failover, scaling, and emergency access.
3. Normal, high-risk, and emergency changes require different approval and execution boundaries.
4. Teams need an explicit right to halt unsafe releases, suspend damaging automation, or restrict change when risk exceeds agreed limits.
5. Residual business risk must be accepted by an authorized risk owner, not silently absorbed by an engineer or SRE team.
6. Delegated authority must state the decision, limits, duration, evidence, and revocation conditions.
7. Emergency authority should be broad enough to reduce harm and constrained by scope, logging, review, and expiry.
8. High-consequence actions may require different initiators, approvers, executors, and reviewers.
9. Conflicting technical, security, product, and business decisions need a named escalation authority.
10. Decision rights must be reviewed after reorganization, criticality change, incidents, access redesign, or service transfer.

---

## 21. Key Takeaways

- Define who may decide, approve, act, stop, override, escalate, and accept risk for a production service.
- Ownership is defined by outcomes and obligations, not labels.
- One accountable team remains answerable for each defined scope.
- Supporting ownership must connect through explicit interfaces.
- Authority, access, knowledge, staffing, and evidence make ownership credible.
- Criticality determines the rigor of verification and review.
- Unknowns, exceptions, and temporary arrangements remain visible.
- Production recovery is complete only when the required outcome is verified.
- Ownership continues through organizational and lifecycle change.
- The Production decision-rights register turns the section into an inspectable production artifact.

---

## Navigation

[Previous: Ownership Dimensions](./07-Ownership-Dimensions.md)

[Next: Service Catalogs](./09-Service-Catalogs.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> Ownership is credible when the organization can identify the outcome, name the accountable team, exercise the authority, inspect the evidence, and recover when the system fails.

