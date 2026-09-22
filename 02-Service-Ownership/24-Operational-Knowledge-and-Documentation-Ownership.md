# Operational Knowledge and Documentation Ownership

> Treat operational knowledge as a maintained production capability with owners, audiences, evidence, review triggers, and lifecycle controls.

## Section Purpose

Treat operational knowledge as a maintained production capability with owners, audiences, evidence, review triggers, and lifecycle controls.

Strong service ownership requires explicit outcomes, boundaries, accountable teams, authority, evidence, and review. A name in a catalog is not enough. The ownership arrangement must continue to work during change, failure, leave, reorganization, recovery, and retirement.

The practical output is a **Operational knowledge ownership register**.

This section governs operational knowledge. It does not repeat the content of individual runbooks, playbooks, architecture records, or recovery procedures.

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
8. Produce and verify a complete Operational knowledge ownership register.

---

## 1. Knowledge domains

Operational knowledge includes service purpose, architecture, dependencies, change, diagnosis, mitigation, recovery, security, data, support, and retirement.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 2. Document ownership

Every authoritative artifact needs an owner accountable for accuracy, access, review, and retirement.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 3. Knowledge distribution

Critical knowledge should be usable by more than one person and demonstrated through practice.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 4. Authoritative location

Teams need one accepted source for each artifact and rules for generated or copied views.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 5. Audience and usability

Content should match the needs of responders, developers, support, auditors, leaders, and consumers.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 6. Review triggers

Incidents, architecture change, ownership transfer, control change, recovery tests, and lifecycle transitions trigger review.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 7. Access and sensitivity

Protect credentials, internal routes, personal data, vulnerabilities, and restricted architecture while preserving responder access.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 8. Executable knowledge

Commands, automation, decision trees, and recovery steps require safe defaults, verification, rollback, and ownership.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 9. Knowledge validation

Use walkthroughs, exercises, novice execution, incident use, and recovery tests to prove usability.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 10. Retirement and archive

Remove obsolete guidance, preserve required history, and prevent retired procedures from being used.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 11. Core Principles

- Knowledge is a production dependency
- Every artifact has an owner
- Authoritative sources are discoverable
- Critical knowledge is distributed
- Documents are tested through use
- Sensitive information is controlled
- Changes trigger review
- Obsolete guidance is retired

---

## 12. Operating Workflow

1. Inventory operational knowledge
2. Classify artifacts and audiences
3. Assign owners and authoritative locations
4. Define review and access rules
5. Close critical gaps
6. Exercise high-consequence procedures
7. Track usage and failures
8. Archive or retire obsolete material

The workflow should be proportionate to service criticality. High-consequence services require stronger evidence, more independent review, more frequent verification, and clearer escalation.

---

## 13. Required Evidence

Useful evidence includes:

- Documentation register
- Owner acceptance
- Access test
- Walkthrough record
- Procedure execution result
- Review history
- Archive decision

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

A failover runbook exists but references a retired command and one former employee's credentials. A recovery exercise fails, proving the document is not operational evidence. The owner corrects access, commands, validation, and review triggers.

### Analysis Questions

1. What service or user outcome is at risk?
2. Which team is accountable for that outcome?
3. Which supporting owners must act?
4. Which decision rights are required?
5. What should happen immediately?
6. What evidence proves recovery?
7. Which durable correction prevents recurrence?

---

## 16. Practical Output: Operational knowledge ownership register

Create a record containing:

- Artifact and purpose:
- Audience:
- Accountable owner:
- Authoritative location:
- Sensitivity:
- Dependencies and prerequisites:
- Validation method:
- Last review:
- Review triggers:
- Retirement and archive rules:

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

- Completed Operational knowledge ownership register
- Owner acceptance
- Verification result
- Scenario analysis
- Open-gap register
- Corrective-action plan

---

## 18. Review Checklist

- [ ] Artifact and purpose is complete, current, and supported by evidence.
- [ ] Audience is complete, current, and supported by evidence.
- [ ] Accountable owner is complete, current, and supported by evidence.
- [ ] Authoritative location is complete, current, and supported by evidence.
- [ ] Sensitivity is complete, current, and supported by evidence.
- [ ] Dependencies and prerequisites is complete, current, and supported by evidence.
- [ ] Validation method is complete, current, and supported by evidence.
- [ ] Last review is complete, current, and supported by evidence.
- [ ] Review triggers is complete, current, and supported by evidence.
- [ ] Retirement and archive rules is complete, current, and supported by evidence.

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

1. Explain knowledge domains and identify the evidence that would prove it works.
2. Explain document ownership and identify the evidence that would prove it works.
3. Explain knowledge distribution and identify the evidence that would prove it works.
4. Explain authoritative location and identify the evidence that would prove it works.
5. Explain audience and usability and identify the evidence that would prove it works.
6. Explain review triggers and identify the evidence that would prove it works.
7. Explain access and sensitivity and identify the evidence that would prove it works.
8. Explain executable knowledge and identify the evidence that would prove it works.
9. Explain knowledge validation and identify the evidence that would prove it works.
10. Explain retirement and archive and identify the evidence that would prove it works.

---

## 20. Knowledge Check Answers

1. Operational knowledge includes service purpose, architecture, dependencies, change, diagnosis, mitigation, recovery, security, data, support, and retirement.
2. Every authoritative artifact needs an owner accountable for accuracy, access, review, and retirement.
3. Critical knowledge should be usable by more than one person and demonstrated through practice.
4. Teams need one accepted source for each artifact and rules for generated or copied views.
5. Content should match the needs of responders, developers, support, auditors, leaders, and consumers.
6. Incidents, architecture change, ownership transfer, control change, recovery tests, and lifecycle transitions trigger review.
7. Protect credentials, internal routes, personal data, vulnerabilities, and restricted architecture while preserving responder access.
8. Commands, automation, decision trees, and recovery steps require safe defaults, verification, rollback, and ownership.
9. Use walkthroughs, exercises, novice execution, incident use, and recovery tests to prove usability.
10. Remove obsolete guidance, preserve required history, and prevent retired procedures from being used.

---

## 21. Key Takeaways

- Treat operational knowledge as a maintained production capability with owners, audiences, evidence, review triggers, and lifecycle controls.
- Ownership is defined by outcomes and obligations, not labels.
- One accountable team remains answerable for each defined scope.
- Supporting ownership must connect through explicit interfaces.
- Authority, access, knowledge, staffing, and evidence make ownership credible.
- Criticality determines the rigor of verification and review.
- Unknowns, exceptions, and temporary arrangements remain visible.
- Production recovery is complete only when the required outcome is verified.
- Ownership continues through organizational and lifecycle change.
- The Operational knowledge ownership register turns the section into an inspectable production artifact.

---

## Navigation

[Previous: Ownership of Control Planes and Shared Infrastructure](./23-Ownership-of-Control-Planes-and-Shared-Infrastructure.md)

[Next: Service Ownership Governance](./25-Service-Ownership-Governance.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> Ownership is credible when the organization can identify the outcome, name the accountable team, exercise the authority, inspect the evidence, and recover when the system fails.

