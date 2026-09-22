# Orphaned and Abandoned Services

> Detect, contain, assign, recover, transfer, or retire production services that lack a functioning accountable owner.

## Section Purpose

Detect, contain, assign, recover, transfer, or retire production services that lack a functioning accountable owner.

Strong service ownership requires explicit outcomes, boundaries, accountable teams, authority, evidence, and review. A name in a catalog is not enough. The ownership arrangement must continue to work during change, failure, leave, reorganization, recovery, and retirement.

The practical output is a **Orphaned-service disposition record**.

This section focuses on unowned services. It does not repeat general service discovery, lifecycle retirement, or temporary ownership rules.

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
8. Produce and verify a complete Orphaned-service disposition record.

---

## 1. Orphan definition

An orphaned service has no functioning accountable team even if a username, repository, or obsolete team remains recorded.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 2. Abandonment signals

Signals include inactive owners, denied ownership, failed contacts, stale deployments, unknown cost, missing access, and unsupported technology.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 3. Detection sources

Use runtime discovery, billing, DNS, certificates, traffic, repositories, monitoring, incidents, and dependency reports.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 4. Immediate containment

Assess user harm, security, data, cost, and change risk before attempting cleanup.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 5. Temporary ownership

Assign an authorized team with enough authority to stabilize and investigate the service.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 6. Reconstruction

Recover purpose, users, boundary, architecture, data, dependencies, access, and operational history.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 7. Disposition decision

Choose permanent ownership, consolidation, replacement, isolation, or retirement.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 8. Unsafe deletion

Do not remove an unknown service based only on low traffic or missing documentation.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 9. Ownership debt

Track orphan count, age, tier, exposure, and time to disposition as governance debt.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 10. Prevention

Lifecycle gates, catalog checks, offboarding, repository rules, and organization-change reviews reduce future orphans.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 11. Core Principles

- An owner field does not prove ownership
- Unknown production is treated as risk
- Contain before changing
- Temporary ownership has authority and expiry
- User and dependency impact are investigated
- Disposition is explicit
- Deletion requires evidence
- Prevention is built into lifecycle controls

---

## 12. Operating Workflow

1. Detect and confirm the orphan
2. Assess consequence and active use
3. Assign temporary accountability
4. Restrict unsafe change
5. Reconstruct service knowledge
6. Choose disposition
7. Execute transfer or retirement
8. Verify removal of the ownership gap

The workflow should be proportionate to service criticality. High-consequence services require stronger evidence, more independent review, more frequent verification, and clearer escalation.

---

## 13. Required Evidence

Useful evidence includes:

- Discovery record
- Impact assessment
- Temporary assignment
- Access and dependency map
- Disposition decision
- Retirement or transfer evidence
- Prevention action

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

A monthly settlement job is owned by a departed employee and has no dashboard. The organization assigns temporary ownership, observes the next run, maps business impact, restores replay procedures, and transfers it to the Finance Systems team instead of deleting it.

### Analysis Questions

1. What service or user outcome is at risk?
2. Which team is accountable for that outcome?
3. Which supporting owners must act?
4. Which decision rights are required?
5. What should happen immediately?
6. What evidence proves recovery?
7. Which durable correction prevents recurrence?

---

## 16. Practical Output: Orphaned-service disposition record

Create a record containing:

- Discovery source:
- Service identity:
- Current evidence of use:
- User and business impact:
- Security, data, and cost exposure:
- Temporary owner:
- Reconstruction findings:
- Disposition decision:
- Execution plan:
- Verification and prevention:

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

- Completed Orphaned-service disposition record
- Owner acceptance
- Verification result
- Scenario analysis
- Open-gap register
- Corrective-action plan

---

## 18. Review Checklist

- [ ] Discovery source is complete, current, and supported by evidence.
- [ ] Service identity is complete, current, and supported by evidence.
- [ ] Current evidence of use is complete, current, and supported by evidence.
- [ ] User and business impact is complete, current, and supported by evidence.
- [ ] Security, data, and cost exposure is complete, current, and supported by evidence.
- [ ] Temporary owner is complete, current, and supported by evidence.
- [ ] Reconstruction findings is complete, current, and supported by evidence.
- [ ] Disposition decision is complete, current, and supported by evidence.
- [ ] Execution plan is complete, current, and supported by evidence.
- [ ] Verification and prevention is complete, current, and supported by evidence.

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

1. Explain orphan definition and identify the evidence that would prove it works.
2. Explain abandonment signals and identify the evidence that would prove it works.
3. Explain detection sources and identify the evidence that would prove it works.
4. Explain immediate containment and identify the evidence that would prove it works.
5. Explain temporary ownership and identify the evidence that would prove it works.
6. Explain reconstruction and identify the evidence that would prove it works.
7. Explain disposition decision and identify the evidence that would prove it works.
8. Explain unsafe deletion and identify the evidence that would prove it works.
9. Explain ownership debt and identify the evidence that would prove it works.
10. Explain prevention and identify the evidence that would prove it works.

---

## 20. Knowledge Check Answers

1. An orphaned service has no functioning accountable team even if a username, repository, or obsolete team remains recorded.
2. Signals include inactive owners, denied ownership, failed contacts, stale deployments, unknown cost, missing access, and unsupported technology.
3. Use runtime discovery, billing, DNS, certificates, traffic, repositories, monitoring, incidents, and dependency reports.
4. Assess user harm, security, data, cost, and change risk before attempting cleanup.
5. Assign an authorized team with enough authority to stabilize and investigate the service.
6. Recover purpose, users, boundary, architecture, data, dependencies, access, and operational history.
7. Choose permanent ownership, consolidation, replacement, isolation, or retirement.
8. Do not remove an unknown service based only on low traffic or missing documentation.
9. Track orphan count, age, tier, exposure, and time to disposition as governance debt.
10. Lifecycle gates, catalog checks, offboarding, repository rules, and organization-change reviews reduce future orphans.

---

## 21. Key Takeaways

- Detect, contain, assign, recover, transfer, or retire production services that lack a functioning accountable owner.
- Ownership is defined by outcomes and obligations, not labels.
- One accountable team remains answerable for each defined scope.
- Supporting ownership must connect through explicit interfaces.
- Authority, access, knowledge, staffing, and evidence make ownership credible.
- Criticality determines the rigor of verification and review.
- Unknowns, exceptions, and temporary arrangements remain visible.
- Production recovery is complete only when the required outcome is verified.
- Ownership continues through organizational and lifecycle change.
- The Orphaned-service disposition record turns the section into an inspectable production artifact.

---

## Navigation

[Previous: Ownership During Organizational Change](./19-Ownership-During-Organizational-Change.md)

[Next: Third-Party and Vendor Service Ownership](./21-Third-Party-and-Vendor-Service-Ownership.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> Ownership is credible when the organization can identify the outcome, name the accountable team, exercise the authority, inspect the evidence, and recover when the system fails.

