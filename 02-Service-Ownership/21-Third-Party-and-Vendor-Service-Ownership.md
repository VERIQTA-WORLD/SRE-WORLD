# Third-Party and Vendor Service Ownership

> Define internal accountability for services, platforms, data, controls, and recovery capabilities supplied by external organizations.

## Section Purpose

Define internal accountability for services, platforms, data, controls, and recovery capabilities supplied by external organizations.

Strong service ownership requires explicit outcomes, boundaries, accountable teams, authority, evidence, and review. A name in a catalog is not enough. The ownership arrangement must continue to work during change, failure, leave, reorganization, recovery, and retirement.

The practical output is a **Third-party service ownership record**.

This section focuses on third-party ownership. It does not replace procurement, legal review, security assessment, or general dependency management.

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
8. Produce and verify a complete Third-party service ownership record.

---

## 1. Internal accountability

A vendor may supply a capability, but an internal team must own its use and consequences.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 2. Relationship owner

The relationship owner coordinates commercial, support, renewal, escalation, and exit matters.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 3. Technical owner

The technical owner manages integration, configuration, identity, observability, and failure handling.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 4. Business owner

The business owner confirms purpose, consequence, affordability, contractual need, and acceptable residual risk.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 5. Shared responsibility

Document provider and customer duties for configuration, access, data, security, backup, recovery, and support.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 6. Contract alignment

Service commitments, notification, evidence, data handling, recovery, and termination terms should support actual production needs.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 7. Vendor incidents

Internal teams detect user impact, invoke vendor support, mitigate locally, communicate, and validate recovery.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 8. Concentration risk

Assess dependence on one provider, region, identity system, network, marketplace, or subcontractor.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 9. Change and renewal

Review ownership, use, risk, cost, and exit before renewal or material provider change.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 10. Exit and failure

Maintain data export, credential revocation, migration, replacement, and provider-failure plans appropriate to consequence.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 11. Core Principles

- Vendors do not replace internal accountability
- Shared responsibility is written
- Contracts reflect technical reality
- Internal monitoring remains necessary
- Vendor incidents have internal command
- Concentration is assessed
- Renewal is a reliability decision
- Exit is planned before urgency

---

## 12. Operating Workflow

1. Identify vendor-supported services
2. Name business, relationship, and technical owners
3. Map shared responsibilities
4. Assess criticality and concentration
5. Align support and contractual commitments
6. Integrate monitoring and escalation
7. Exercise failure and exit scenarios
8. Review before renewal

The workflow should be proportionate to service criticality. High-consequence services require stronger evidence, more independent review, more frequent verification, and clearer escalation.

---

## 13. Required Evidence

Useful evidence includes:

- Vendor ownership record
- Shared-responsibility matrix
- Support entitlement
- Contract requirement map
- Incident escalation test
- Data export test
- Renewal decision
- Exit plan

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

A SaaS identity provider suffers a regional outage. The vendor owns provider recovery, while the internal identity team owns user impact, fallback decisions, vendor escalation, communication, and verification that organizational access is safely restored.

### Analysis Questions

1. What service or user outcome is at risk?
2. Which team is accountable for that outcome?
3. Which supporting owners must act?
4. Which decision rights are required?
5. What should happen immediately?
6. What evidence proves recovery?
7. Which durable correction prevents recurrence?

---

## 16. Practical Output: Third-party service ownership record

Create a record containing:

- Vendor and capability:
- Internal business owner:
- Relationship owner:
- Technical owner:
- Shared responsibilities:
- Data and security obligations:
- Support and escalation:
- Concentration and alternatives:
- Renewal review:
- Exit and failure plan:

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

- Completed Third-party service ownership record
- Owner acceptance
- Verification result
- Scenario analysis
- Open-gap register
- Corrective-action plan

---

## 18. Review Checklist

- [ ] Vendor and capability is complete, current, and supported by evidence.
- [ ] Internal business owner is complete, current, and supported by evidence.
- [ ] Relationship owner is complete, current, and supported by evidence.
- [ ] Technical owner is complete, current, and supported by evidence.
- [ ] Shared responsibilities is complete, current, and supported by evidence.
- [ ] Data and security obligations is complete, current, and supported by evidence.
- [ ] Support and escalation is complete, current, and supported by evidence.
- [ ] Concentration and alternatives is complete, current, and supported by evidence.
- [ ] Renewal review is complete, current, and supported by evidence.
- [ ] Exit and failure plan is complete, current, and supported by evidence.

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

1. Explain internal accountability and identify the evidence that would prove it works.
2. Explain relationship owner and identify the evidence that would prove it works.
3. Explain technical owner and identify the evidence that would prove it works.
4. Explain business owner and identify the evidence that would prove it works.
5. Explain shared responsibility and identify the evidence that would prove it works.
6. Explain contract alignment and identify the evidence that would prove it works.
7. Explain vendor incidents and identify the evidence that would prove it works.
8. Explain concentration risk and identify the evidence that would prove it works.
9. Explain change and renewal and identify the evidence that would prove it works.
10. Explain exit and failure and identify the evidence that would prove it works.

---

## 20. Knowledge Check Answers

1. A vendor may supply a capability, but an internal team must own its use and consequences.
2. The relationship owner coordinates commercial, support, renewal, escalation, and exit matters.
3. The technical owner manages integration, configuration, identity, observability, and failure handling.
4. The business owner confirms purpose, consequence, affordability, contractual need, and acceptable residual risk.
5. Document provider and customer duties for configuration, access, data, security, backup, recovery, and support.
6. Service commitments, notification, evidence, data handling, recovery, and termination terms should support actual production needs.
7. Internal teams detect user impact, invoke vendor support, mitigate locally, communicate, and validate recovery.
8. Assess dependence on one provider, region, identity system, network, marketplace, or subcontractor.
9. Review ownership, use, risk, cost, and exit before renewal or material provider change.
10. Maintain data export, credential revocation, migration, replacement, and provider-failure plans appropriate to consequence.

---

## 21. Key Takeaways

- Define internal accountability for services, platforms, data, controls, and recovery capabilities supplied by external organizations.
- Ownership is defined by outcomes and obligations, not labels.
- One accountable team remains answerable for each defined scope.
- Supporting ownership must connect through explicit interfaces.
- Authority, access, knowledge, staffing, and evidence make ownership credible.
- Criticality determines the rigor of verification and review.
- Unknowns, exceptions, and temporary arrangements remain visible.
- Production recovery is complete only when the required outcome is verified.
- Ownership continues through organizational and lifecycle change.
- The Third-party service ownership record turns the section into an inspectable production artifact.

---

## Navigation

[Previous: Orphaned and Abandoned Services](./20-Orphaned-and-Abandoned-Services.md)

[Next: Ownership of Data and State](./22-Ownership-of-Data-and-State.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> Ownership is credible when the organization can identify the outcome, name the accountable team, exercise the authority, inspect the evidence, and recover when the system fails.

