# Support Coverage and Escalation Ownership

> Define who receives, triages, investigates, communicates, escalates, and resolves production issues across time and severity.

## Section Purpose

Define who receives, triages, investigates, communicates, escalates, and resolves production issues across time and severity.

Strong service ownership requires explicit outcomes, boundaries, accountable teams, authority, evidence, and review. A name in a catalog is not enough. The ownership arrangement must continue to work during change, failure, leave, reorganization, recovery, and retirement.

The practical output is a **Support and escalation ownership plan**.

This section defines ownership of support coverage and escalation. It does not design complete on-call rotations or incident-command practice.

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
8. Produce and verify a complete Support and escalation ownership plan.

---

## 1. Coverage commitment

Coverage should match service criticality, business timing, user expectations, and available alternatives.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 2. Support layers

Distinguish intake, triage, technical response, specialist escalation, management escalation, vendor escalation, and business communication.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 3. Primary route

The primary route should be monitored, durable, appropriate to purpose, and tested.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 4. Secondary route

The secondary route should provide a credible alternative rather than repeat the same failure condition.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 5. Escalation triggers

Define severity, elapsed time, failed mitigation, data risk, security exposure, safety impact, and business deadlines.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 6. Acknowledgement

A handoff is incomplete until the receiving owner accepts it.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 7. After-hours ownership

State which services require continuous response and which use business-hours support.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 8. Vendor escalation

Record entitlement, contact method, required diagnostic evidence, and internal relationship owner.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 9. Escalation failure

Detect unreachable teams, stale contacts, delayed acknowledgement, unclear severity, and authority gaps.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 10. Testing

Exercise contact routes and scenario escalation without creating unnecessary production disruption.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 11. Core Principles

- Coverage follows consequence
- Support routes are durable
- General and emergency routes are separate
- Escalation has objective triggers
- Handoffs require acceptance
- After-hours obligations are explicit
- Vendor escalation has an internal owner
- Routes are tested

---

## 12. Operating Workflow

1. Classify support needs
2. Define support layers and coverage windows
3. Name owners and routes
4. Set escalation triggers and timers
5. Connect authority and communication
6. Define vendor and business escalation
7. Test contact and handoff paths
8. Review failures and staffing sustainability

The workflow should be proportionate to service criticality. High-consequence services require stronger evidence, more independent review, more frequent verification, and clearer escalation.

---

## 13. Required Evidence

Useful evidence includes:

- Coverage record
- Contact-route test
- Acknowledgement timestamp
- Escalation log
- Vendor case
- Coverage exception
- Review result

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

A batch service fails two hours before payroll cutoff. Normal business-hours support is insufficient because the failure is time sensitive. The escalation policy identifies the batch owner, business-process owner, database specialist, and management authority before the deadline is missed.

### Analysis Questions

1. What service or user outcome is at risk?
2. Which team is accountable for that outcome?
3. Which supporting owners must act?
4. Which decision rights are required?
5. What should happen immediately?
6. What evidence proves recovery?
7. Which durable correction prevents recurrence?

---

## 16. Practical Output: Support and escalation ownership plan

Create a record containing:

- Service and tier:
- Coverage window:
- Support layers and owners:
- Primary and secondary routes:
- Escalation triggers:
- Acknowledgement target:
- Specialist and vendor routes:
- Business communication owner:
- Exceptions:
- Test and review dates:

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

- Completed Support and escalation ownership plan
- Owner acceptance
- Verification result
- Scenario analysis
- Open-gap register
- Corrective-action plan

---

## 18. Review Checklist

- [ ] Service and tier is complete, current, and supported by evidence.
- [ ] Coverage window is complete, current, and supported by evidence.
- [ ] Support layers and owners is complete, current, and supported by evidence.
- [ ] Primary and secondary routes is complete, current, and supported by evidence.
- [ ] Escalation triggers is complete, current, and supported by evidence.
- [ ] Acknowledgement target is complete, current, and supported by evidence.
- [ ] Specialist and vendor routes is complete, current, and supported by evidence.
- [ ] Business communication owner is complete, current, and supported by evidence.
- [ ] Exceptions is complete, current, and supported by evidence.
- [ ] Test and review dates is complete, current, and supported by evidence.

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

1. Explain coverage commitment and identify the evidence that would prove it works.
2. Explain support layers and identify the evidence that would prove it works.
3. Explain primary route and identify the evidence that would prove it works.
4. Explain secondary route and identify the evidence that would prove it works.
5. Explain escalation triggers and identify the evidence that would prove it works.
6. Explain acknowledgement and identify the evidence that would prove it works.
7. Explain after-hours ownership and identify the evidence that would prove it works.
8. Explain vendor escalation and identify the evidence that would prove it works.
9. Explain escalation failure and identify the evidence that would prove it works.
10. Explain testing and identify the evidence that would prove it works.

---

## 20. Knowledge Check Answers

1. Coverage should match service criticality, business timing, user expectations, and available alternatives.
2. Distinguish intake, triage, technical response, specialist escalation, management escalation, vendor escalation, and business communication.
3. The primary route should be monitored, durable, appropriate to purpose, and tested.
4. The secondary route should provide a credible alternative rather than repeat the same failure condition.
5. Define severity, elapsed time, failed mitigation, data risk, security exposure, safety impact, and business deadlines.
6. A handoff is incomplete until the receiving owner accepts it.
7. State which services require continuous response and which use business-hours support.
8. Record entitlement, contact method, required diagnostic evidence, and internal relationship owner.
9. Detect unreachable teams, stale contacts, delayed acknowledgement, unclear severity, and authority gaps.
10. Exercise contact routes and scenario escalation without creating unnecessary production disruption.

---

## 21. Key Takeaways

- Define who receives, triages, investigates, communicates, escalates, and resolves production issues across time and severity.
- Ownership is defined by outcomes and obligations, not labels.
- One accountable team remains answerable for each defined scope.
- Supporting ownership must connect through explicit interfaces.
- Authority, access, knowledge, staffing, and evidence make ownership credible.
- Criticality determines the rigor of verification and review.
- Unknowns, exceptions, and temporary arrangements remain visible.
- Production recovery is complete only when the required outcome is verified.
- Ownership continues through organizational and lifecycle change.
- The Support and escalation ownership plan turns the section into an inspectable production artifact.

---

## Navigation

[Previous: Cross-Team Ownership Boundaries](./14-Cross-Team-Ownership-Boundaries.md)

[Next: Service Ownership Acceptance Criteria](./16-Service-Ownership-Acceptance-Criteria.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> Ownership is credible when the organization can identify the outcome, name the accountable team, exercise the authority, inspect the evidence, and recover when the system fails.

