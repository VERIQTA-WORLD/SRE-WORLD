# Service Ownership Templates

> Provide a governed template index for creating consistent, inspectable ownership records without forcing every service into one oversized document.

## Section Purpose

Provide a governed template index for creating consistent, inspectable ownership records without forcing every service into one oversized document.

Strong service ownership requires explicit outcomes, boundaries, accountable teams, authority, evidence, and review. A name in a catalog is not enough. The ownership arrangement must continue to work during change, failure, leave, reorganization, recovery, and retirement.

The practical output is a **Service-ownership template library**.

This section provides template specifications and usage rules. It does not repeat the complete teaching content behind each template.

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
8. Produce and verify a complete Service-ownership template library.

---

## 1. Template system

Templates should share stable identifiers, service context, owners, dates, evidence, gaps, decisions, and review triggers.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 2. Inventory template

Captures the initial list of production services and discovery confidence.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 3. Boundary template

Defines included outcomes, components, data, runtime, dependencies, ownership, and exclusions.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 4. Taxonomy and lifecycle templates

Record classification reasoning, lifecycle state, transition evidence, and authority.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 5. Criticality template

Captures consequence dimensions, tier decision, ownership obligations, and reclassification triggers.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 6. Owner and dimensions templates

Record accountable teams, named roles, continuity, dimension scopes, interfaces, and verification.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 7. Authority and catalog templates

Record decision rights, metadata, authoritative sources, access views, and freshness.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 8. Dependency and platform templates

Record consumer-provider obligations, supported tiers, failure behavior, and exit.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 9. Acceptance, onboarding, and transfer templates

Control assumption and movement of accountability.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 10. Governance templates

Cover exceptions, orphan disposition, health scorecards, anti-pattern findings, and review evidence.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 11. Core Principles

- Use the smallest sufficient template
- Required fields support decisions
- Unknown values remain visible
- Evidence is linked
- Sensitive fields are classified
- Versions and history are preserved
- Templates evolve through governance
- Completion does not replace verification

---

## 12. Operating Workflow

1. Choose the decision being supported
2. Select the matching template
3. Complete required service context
4. Add evidence and owners
5. Record unknowns and exceptions
6. Obtain acceptance
7. Store in the authoritative location
8. Review on trigger or schedule

The workflow should be proportionate to service criticality. High-consequence services require stronger evidence, more independent review, more frequent verification, and clearer escalation.

---

## 13. Required Evidence

Useful evidence includes:

- Completed template
- Approval
- Linked evidence
- Version history
- Exception record
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

A team attempts to use the criticality template as a service boundary record. Reviewers reject the substitution because consequence classification cannot prove what belongs inside the service or who owns excluded components.

### Analysis Questions

1. What service or user outcome is at risk?
2. Which team is accountable for that outcome?
3. Which supporting owners must act?
4. Which decision rights are required?
5. What should happen immediately?
6. What evidence proves recovery?
7. Which durable correction prevents recurrence?

---

## 16. Practical Output: Service-ownership template library

Create a record containing:

- Template name:
- Decision supported:
- Required users:
- Required fields:
- Optional extensions:
- Evidence requirements:
- Sensitivity:
- Approval:
- Review trigger:
- Authoritative location:

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

- Completed Service-ownership template library
- Owner acceptance
- Verification result
- Scenario analysis
- Open-gap register
- Corrective-action plan

---

## 18. Review Checklist

- [ ] Template name is complete, current, and supported by evidence.
- [ ] Decision supported is complete, current, and supported by evidence.
- [ ] Required users is complete, current, and supported by evidence.
- [ ] Required fields is complete, current, and supported by evidence.
- [ ] Optional extensions is complete, current, and supported by evidence.
- [ ] Evidence requirements is complete, current, and supported by evidence.
- [ ] Sensitivity is complete, current, and supported by evidence.
- [ ] Approval is complete, current, and supported by evidence.
- [ ] Review trigger is complete, current, and supported by evidence.
- [ ] Authoritative location is complete, current, and supported by evidence.

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

1. Explain template system and identify the evidence that would prove it works.
2. Explain inventory template and identify the evidence that would prove it works.
3. Explain boundary template and identify the evidence that would prove it works.
4. Explain taxonomy and lifecycle templates and identify the evidence that would prove it works.
5. Explain criticality template and identify the evidence that would prove it works.
6. Explain owner and dimensions templates and identify the evidence that would prove it works.
7. Explain authority and catalog templates and identify the evidence that would prove it works.
8. Explain dependency and platform templates and identify the evidence that would prove it works.
9. Explain acceptance, onboarding, and transfer templates and identify the evidence that would prove it works.
10. Explain governance templates and identify the evidence that would prove it works.

---

## 20. Knowledge Check Answers

1. Templates should share stable identifiers, service context, owners, dates, evidence, gaps, decisions, and review triggers.
2. Captures the initial list of production services and discovery confidence.
3. Defines included outcomes, components, data, runtime, dependencies, ownership, and exclusions.
4. Record classification reasoning, lifecycle state, transition evidence, and authority.
5. Captures consequence dimensions, tier decision, ownership obligations, and reclassification triggers.
6. Record accountable teams, named roles, continuity, dimension scopes, interfaces, and verification.
7. Record decision rights, metadata, authoritative sources, access views, and freshness.
8. Record consumer-provider obligations, supported tiers, failure behavior, and exit.
9. Control assumption and movement of accountability.
10. Cover exceptions, orphan disposition, health scorecards, anti-pattern findings, and review evidence.

---

## 21. Key Takeaways

- Provide a governed template index for creating consistent, inspectable ownership records without forcing every service into one oversized document.
- Ownership is defined by outcomes and obligations, not labels.
- One accountable team remains answerable for each defined scope.
- Supporting ownership must connect through explicit interfaces.
- Authority, access, knowledge, staffing, and evidence make ownership credible.
- Criticality determines the rigor of verification and review.
- Unknowns, exceptions, and temporary arrangements remain visible.
- Production recovery is complete only when the required outcome is verified.
- Ownership continues through organizational and lifecycle change.
- The Service-ownership template library turns the section into an inspectable production artifact.

---

## Navigation

[Previous: Service Ownership Practical Exercises](./29-Service-Ownership-Practical-Exercises.md)

[Next: Service Ownership Resources](./31-Service-Ownership-Resources.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> Ownership is credible when the organization can identify the outcome, name the accountable team, exercise the authority, inspect the evidence, and recover when the system fails.

