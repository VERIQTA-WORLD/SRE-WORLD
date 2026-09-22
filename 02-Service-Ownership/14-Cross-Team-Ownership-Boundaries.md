# Cross-Team Ownership Boundaries

> Define clear operational interfaces where service responsibilities, authority, work, and evidence cross team boundaries.

## Section Purpose

Define clear operational interfaces where service responsibilities, authority, work, and evidence cross team boundaries.

Strong service ownership requires explicit outcomes, boundaries, accountable teams, authority, evidence, and review. A name in a catalog is not enough. The ownership arrangement must continue to work during change, failure, leave, reorganization, recovery, and retirement.

The practical output is a **Cross-team ownership-boundary agreement**.

This section defines cross-team boundaries. It does not repeat service boundaries, shared-platform agreements, or formal service-transfer procedures.

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
8. Produce and verify a complete Cross-team ownership-boundary agreement.

---

## 1. Boundary statement

A cross-team boundary states what one team provides, what another consumes, and where responsibility changes.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 2. Inputs and outputs

Define information, artifacts, approvals, events, and operational outcomes passed across the boundary.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 3. Handoffs

A handoff needs a trigger, required context, receiver acknowledgement, completion rule, and escalation path.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 4. Authority boundary

Record which team may change, stop, restore, approve, or accept risk within each scope.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 5. Failure boundary

Define detection, containment, investigation, mitigation, recovery, and validation responsibilities.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 6. Data boundary

Clarify read, write, schema, quality, retention, correction, and incident obligations.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 7. Security boundary

Clarify trust, identity, privileged access, control operation, exceptions, and evidence.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 8. Conflict resolution

Boundary disputes need a named resolver and temporary protection while the decision is pending.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 9. Boundary evidence

Use service records, contracts, runbooks, ownership matrices, change records, and exercises.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 10. Boundary review

Review when architecture, teams, criticality, technology, or lifecycle state changes.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 11. Core Principles

- Boundaries are written in outcome terms
- Handoffs require acknowledgement
- Authority is explicit
- Failure work is divided before incidents
- Data and security responsibilities are visible
- Disputes have a resolver
- Temporary controls protect production
- Boundary evidence is reviewed

---

## 12. Operating Workflow

1. Identify cross-team interactions
2. Define provider and consumer outcomes
3. Map handoffs and authority
4. Define failure, data, and security boundaries
5. Establish escalation and dispute resolution
6. Test a normal and failure handoff
7. Record gaps and temporary controls
8. Approve and review

The workflow should be proportionate to service criticality. High-consequence services require stronger evidence, more independent review, more frequent verification, and clearer escalation.

---

## 13. Required Evidence

Useful evidence includes:

- Boundary agreement
- Handoff test
- Authority map
- Incident record
- Access and data agreement
- Dispute decision

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

An application team requests a database restore. The database team needs a validated restore point and approval, while the application team must stop writes and later verify business correctness. A written boundary prevents both teams from waiting for the other during recovery.

### Analysis Questions

1. What service or user outcome is at risk?
2. Which team is accountable for that outcome?
3. Which supporting owners must act?
4. Which decision rights are required?
5. What should happen immediately?
6. What evidence proves recovery?
7. Which durable correction prevents recurrence?

---

## 16. Practical Output: Cross-team ownership-boundary agreement

Create a record containing:

- Teams and scopes:
- Provided and consumed outcomes:
- Inputs and outputs:
- Handoff triggers:
- Authority boundaries:
- Failure responsibilities:
- Data and security obligations:
- Escalation and dispute resolver:
- Evidence:
- Review triggers:

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

- Completed Cross-team ownership-boundary agreement
- Owner acceptance
- Verification result
- Scenario analysis
- Open-gap register
- Corrective-action plan

---

## 18. Review Checklist

- [ ] Teams and scopes is complete, current, and supported by evidence.
- [ ] Provided and consumed outcomes is complete, current, and supported by evidence.
- [ ] Inputs and outputs is complete, current, and supported by evidence.
- [ ] Handoff triggers is complete, current, and supported by evidence.
- [ ] Authority boundaries is complete, current, and supported by evidence.
- [ ] Failure responsibilities is complete, current, and supported by evidence.
- [ ] Data and security obligations is complete, current, and supported by evidence.
- [ ] Escalation and dispute resolver is complete, current, and supported by evidence.
- [ ] Evidence is complete, current, and supported by evidence.
- [ ] Review triggers is complete, current, and supported by evidence.

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

1. Explain boundary statement and identify the evidence that would prove it works.
2. Explain inputs and outputs and identify the evidence that would prove it works.
3. Explain handoffs and identify the evidence that would prove it works.
4. Explain authority boundary and identify the evidence that would prove it works.
5. Explain failure boundary and identify the evidence that would prove it works.
6. Explain data boundary and identify the evidence that would prove it works.
7. Explain security boundary and identify the evidence that would prove it works.
8. Explain conflict resolution and identify the evidence that would prove it works.
9. Explain boundary evidence and identify the evidence that would prove it works.
10. Explain boundary review and identify the evidence that would prove it works.

---

## 20. Knowledge Check Answers

1. A cross-team boundary states what one team provides, what another consumes, and where responsibility changes.
2. Define information, artifacts, approvals, events, and operational outcomes passed across the boundary.
3. A handoff needs a trigger, required context, receiver acknowledgement, completion rule, and escalation path.
4. Record which team may change, stop, restore, approve, or accept risk within each scope.
5. Define detection, containment, investigation, mitigation, recovery, and validation responsibilities.
6. Clarify read, write, schema, quality, retention, correction, and incident obligations.
7. Clarify trust, identity, privileged access, control operation, exceptions, and evidence.
8. Boundary disputes need a named resolver and temporary protection while the decision is pending.
9. Use service records, contracts, runbooks, ownership matrices, change records, and exercises.
10. Review when architecture, teams, criticality, technology, or lifecycle state changes.

---

## 21. Key Takeaways

- Define clear operational interfaces where service responsibilities, authority, work, and evidence cross team boundaries.
- Ownership is defined by outcomes and obligations, not labels.
- One accountable team remains answerable for each defined scope.
- Supporting ownership must connect through explicit interfaces.
- Authority, access, knowledge, staffing, and evidence make ownership credible.
- Criticality determines the rigor of verification and review.
- Unknowns, exceptions, and temporary arrangements remain visible.
- Production recovery is complete only when the required outcome is verified.
- Ownership continues through organizational and lifecycle change.
- The Cross-team ownership-boundary agreement turns the section into an inspectable production artifact.

---

## Navigation

[Previous: End-to-End Journey Ownership](./13-End-to-End-Journey-Ownership.md)

[Next: Support Coverage and Escalation Ownership](./15-Support-Coverage-and-Escalation-Ownership.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> Ownership is credible when the organization can identify the outcome, name the accountable team, exercise the authority, inspect the evidence, and recover when the system fails.

