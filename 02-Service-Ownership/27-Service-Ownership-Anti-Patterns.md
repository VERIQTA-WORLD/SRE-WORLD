# Service Ownership Anti-Patterns

> Identify recurring ownership models that create false accountability, hidden risk, unsustainable operations, and delayed recovery.

## Section Purpose

Identify recurring ownership models that create false accountability, hidden risk, unsustainable operations, and delayed recovery.

Strong service ownership requires explicit outcomes, boundaries, accountable teams, authority, evidence, and review. A name in a catalog is not enough. The ownership arrangement must continue to work during change, failure, leave, reorganization, recovery, and retirement.

The practical output is a **Ownership anti-pattern assessment**.

This section diagnoses anti-patterns. It does not repeat the full corrective processes defined in earlier sections.

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
8. Produce and verify a complete Ownership anti-pattern assessment.

---

## 1. Individual hero ownership

One person holds knowledge, access, authority, and response responsibility without team continuity.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 2. Everyone owns it

Many teams are listed without one accountable owner for a defined outcome.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 3. Repository equals service

Code-review responsibility is treated as proof of runtime, data, recovery, and lifecycle ownership.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 4. Platform owns every workload

The platform team is blamed for application behavior merely because workloads run on its infrastructure.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 5. SRE owns production

Product teams transfer accountability to SRE without sharing architecture, prioritization, or corrective work.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 6. Vendor owns it

An external provider is treated as the internal risk, integration, incident, and exit owner.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 7. Pager equals ownership

A response queue receives alerts but lacks authority, knowledge, or capacity to correct the service.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 8. Temporary forever

A transition team remains accountable indefinitely without an approved destination.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 9. Metadata theater

Records are complete but stale, unaccepted, unreachable, or unsupported by capability.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 10. Deprecated means abandoned

A service loses ownership while users, data, dependencies, or obligations still exist.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 11. Shared database ambiguity

Several services write shared state while no team owns integrity, schema, correction, or recovery.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 12. Highest-tier inflation

Every service claims maximum criticality, making ownership commitments impossible to prioritize.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 13. Core Principles

- Anti-patterns are system conditions
- Labels do not prove capability
- Ownership follows outcomes
- Authority and capacity matter
- Temporary states have exits
- Evidence challenges false confidence
- Correct causes rather than blame people
- Remediation is proportional to consequence

---

## 14. Operating Workflow

1. Detect the ownership symptom
2. Identify the underlying boundary or capability failure
3. Assess user and business exposure
4. Apply temporary protection
5. Choose the relevant corrective process
6. Assign remediation authority
7. Verify the corrected model
8. Capture prevention controls

The workflow should be proportionate to service criticality. High-consequence services require stronger evidence, more independent review, more frequent verification, and clearer escalation.

---

## 15. Required Evidence

Useful evidence includes:

- Anti-pattern finding
- Impact assessment
- Temporary control
- Corrective ownership record
- Verification result
- Prevention change

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

A central SRE team receives every page but cannot change product code or stop unsafe releases. Incidents recur because product teams treat SRE as the owner. The model is corrected by restoring product-team accountability and defining SRE's reliability responsibilities.

### Analysis Questions

1. What service or user outcome is at risk?
2. Which team is accountable for that outcome?
3. Which supporting owners must act?
4. Which decision rights are required?
5. What should happen immediately?
6. What evidence proves recovery?
7. Which durable correction prevents recurrence?

---

## 18. Practical Output: Ownership anti-pattern assessment

Create a record containing:

- Observed pattern:
- Affected service and tier:
- Evidence:
- User and operational consequence:
- Underlying cause:
- Temporary protection:
- Corrective model:
- Remediation owner:
- Verification:
- Prevention:

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

- Completed Ownership anti-pattern assessment
- Owner acceptance
- Verification result
- Scenario analysis
- Open-gap register
- Corrective-action plan

---

## 20. Review Checklist

- [ ] Observed pattern is complete, current, and supported by evidence.
- [ ] Affected service and tier is complete, current, and supported by evidence.
- [ ] Evidence is complete, current, and supported by evidence.
- [ ] User and operational consequence is complete, current, and supported by evidence.
- [ ] Underlying cause is complete, current, and supported by evidence.
- [ ] Temporary protection is complete, current, and supported by evidence.
- [ ] Corrective model is complete, current, and supported by evidence.
- [ ] Remediation owner is complete, current, and supported by evidence.
- [ ] Verification is complete, current, and supported by evidence.
- [ ] Prevention is complete, current, and supported by evidence.

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

1. Explain individual hero ownership and identify the evidence that would prove it works.
2. Explain everyone owns it and identify the evidence that would prove it works.
3. Explain repository equals service and identify the evidence that would prove it works.
4. Explain platform owns every workload and identify the evidence that would prove it works.
5. Explain sre owns production and identify the evidence that would prove it works.
6. Explain vendor owns it and identify the evidence that would prove it works.
7. Explain pager equals ownership and identify the evidence that would prove it works.
8. Explain temporary forever and identify the evidence that would prove it works.
9. Explain metadata theater and identify the evidence that would prove it works.
10. Explain deprecated means abandoned and identify the evidence that would prove it works.

---

## 22. Knowledge Check Answers

1. One person holds knowledge, access, authority, and response responsibility without team continuity.
2. Many teams are listed without one accountable owner for a defined outcome.
3. Code-review responsibility is treated as proof of runtime, data, recovery, and lifecycle ownership.
4. The platform team is blamed for application behavior merely because workloads run on its infrastructure.
5. Product teams transfer accountability to SRE without sharing architecture, prioritization, or corrective work.
6. An external provider is treated as the internal risk, integration, incident, and exit owner.
7. A response queue receives alerts but lacks authority, knowledge, or capacity to correct the service.
8. A transition team remains accountable indefinitely without an approved destination.
9. Records are complete but stale, unaccepted, unreachable, or unsupported by capability.
10. A service loses ownership while users, data, dependencies, or obligations still exist.

---

## 23. Key Takeaways

- Identify recurring ownership models that create false accountability, hidden risk, unsustainable operations, and delayed recovery.
- Ownership is defined by outcomes and obligations, not labels.
- One accountable team remains answerable for each defined scope.
- Supporting ownership must connect through explicit interfaces.
- Authority, access, knowledge, staffing, and evidence make ownership credible.
- Criticality determines the rigor of verification and review.
- Unknowns, exceptions, and temporary arrangements remain visible.
- Production recovery is complete only when the required outcome is verified.
- Ownership continues through organizational and lifecycle change.
- The Ownership anti-pattern assessment turns the section into an inspectable production artifact.

---

## Navigation

[Previous: Measuring Ownership Health](./26-Measuring-Ownership-Health.md)

[Next: Service Ownership Production Scenarios](./28-Service-Ownership-Production-Scenarios.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> Ownership is credible when the organization can identify the outcome, name the accountable team, exercise the authority, inspect the evidence, and recover when the system fails.

