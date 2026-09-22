# Service Ownership Metadata

> Define the minimum, extended, sensitive, and lifecycle metadata needed to make ownership records actionable and machine-readable.

## Section Purpose

Define the minimum, extended, sensitive, and lifecycle metadata needed to make ownership records actionable and machine-readable.

Strong service ownership requires explicit outcomes, boundaries, accountable teams, authority, evidence, and review. A name in a catalog is not enough. The ownership arrangement must continue to work during change, failure, leave, reorganization, recovery, and retirement.

The practical output is a **Service-ownership metadata schema**.

This section defines ownership metadata. It does not redesign the service catalog, service boundary, taxonomy, or criticality method.

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
8. Produce and verify a complete Service-ownership metadata schema.

---

## 1. Stable identity

Every service and accountable team needs a stable identifier that survives display-name changes.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 2. Core identity metadata

Record service name, purpose, boundary reference, lifecycle state, classification, criticality, and accountable team.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 3. Contact metadata

Separate general contact, support, emergency escalation, business owner, technical owner, and public contact routes.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 4. Operational metadata

Link runtime environments, repositories, dashboards, runbooks, recovery records, and change mechanisms.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 5. Relationship metadata

Represent dependencies, consumers, platforms, data sets, control ownership, and business capabilities.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 6. Temporal metadata

Store effective dates, verification dates, expiry dates, previous owners, and lifecycle transitions.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 7. Evidence metadata

Record verification method, evidence location, exceptions, open gaps, and remediation ownership.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 8. Sensitivity

Classify fields so personal details, security routes, internal identifiers, and privileged information are not exposed improperly.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 9. Schema governance

Use documented definitions, allowed values, validation rules, versioning, and deprecation processes.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 10. Automation

Validate required fields and stale references without allowing automation to invent an accountable owner.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 11. Core Principles

- Every field has a defined meaning
- Stable identifiers accompany display names
- Required and optional fields are distinct
- Sensitive data is minimized
- Metadata has an authoritative source
- History is preserved
- Validation is automated where safe
- Human acceptance remains necessary

---

## 12. Operating Workflow

1. Identify decisions supported by metadata
2. Define the minimum schema
3. Define extended fields by service type and tier
4. Classify sensitive fields
5. Map authoritative sources
6. Define validation and synchronization
7. Migrate existing records
8. Measure completeness and freshness

The workflow should be proportionate to service criticality. High-consequence services require stronger evidence, more independent review, more frequent verification, and clearer escalation.

---

## 13. Required Evidence

Useful evidence includes:

- Schema definition
- Field dictionary
- Validation result
- Ownership verification record
- Change history
- Sensitivity classification

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

A team changes its name during a reorganization. The stable team identifier remains unchanged, catalog views update the display name, historical records remain traceable, and escalation routes are verified rather than silently copied.

### Analysis Questions

1. What service or user outcome is at risk?
2. Which team is accountable for that outcome?
3. Which supporting owners must act?
4. Which decision rights are required?
5. What should happen immediately?
6. What evidence proves recovery?
7. Which durable correction prevents recurrence?

---

## 16. Practical Output: Service-ownership metadata schema

Create a record containing:

- Field name:
- Definition:
- Data type:
- Allowed values:
- Required condition:
- Authoritative source:
- Sensitivity:
- Validation rule:
- Update trigger:
- Retention and history:

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

- Completed Service-ownership metadata schema
- Owner acceptance
- Verification result
- Scenario analysis
- Open-gap register
- Corrective-action plan

---

## 18. Review Checklist

- [ ] Field name is complete, current, and supported by evidence.
- [ ] Definition is complete, current, and supported by evidence.
- [ ] Data type is complete, current, and supported by evidence.
- [ ] Allowed values is complete, current, and supported by evidence.
- [ ] Required condition is complete, current, and supported by evidence.
- [ ] Authoritative source is complete, current, and supported by evidence.
- [ ] Sensitivity is complete, current, and supported by evidence.
- [ ] Validation rule is complete, current, and supported by evidence.
- [ ] Update trigger is complete, current, and supported by evidence.
- [ ] Retention and history is complete, current, and supported by evidence.

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

1. Explain stable identity and identify the evidence that would prove it works.
2. Explain core identity metadata and identify the evidence that would prove it works.
3. Explain contact metadata and identify the evidence that would prove it works.
4. Explain operational metadata and identify the evidence that would prove it works.
5. Explain relationship metadata and identify the evidence that would prove it works.
6. Explain temporal metadata and identify the evidence that would prove it works.
7. Explain evidence metadata and identify the evidence that would prove it works.
8. Explain sensitivity and identify the evidence that would prove it works.
9. Explain schema governance and identify the evidence that would prove it works.
10. Explain automation and identify the evidence that would prove it works.

---

## 20. Knowledge Check Answers

1. Every service and accountable team needs a stable identifier that survives display-name changes.
2. Record service name, purpose, boundary reference, lifecycle state, classification, criticality, and accountable team.
3. Separate general contact, support, emergency escalation, business owner, technical owner, and public contact routes.
4. Link runtime environments, repositories, dashboards, runbooks, recovery records, and change mechanisms.
5. Represent dependencies, consumers, platforms, data sets, control ownership, and business capabilities.
6. Store effective dates, verification dates, expiry dates, previous owners, and lifecycle transitions.
7. Record verification method, evidence location, exceptions, open gaps, and remediation ownership.
8. Classify fields so personal details, security routes, internal identifiers, and privileged information are not exposed improperly.
9. Use documented definitions, allowed values, validation rules, versioning, and deprecation processes.
10. Validate required fields and stale references without allowing automation to invent an accountable owner.

---

## 21. Key Takeaways

- Define the minimum, extended, sensitive, and lifecycle metadata needed to make ownership records actionable and machine-readable.
- Ownership is defined by outcomes and obligations, not labels.
- One accountable team remains answerable for each defined scope.
- Supporting ownership must connect through explicit interfaces.
- Authority, access, knowledge, staffing, and evidence make ownership credible.
- Criticality determines the rigor of verification and review.
- Unknowns, exceptions, and temporary arrangements remain visible.
- Production recovery is complete only when the required outcome is verified.
- Ownership continues through organizational and lifecycle change.
- The Service-ownership metadata schema turns the section into an inspectable production artifact.

---

## Navigation

[Previous: Service Catalogs](./09-Service-Catalogs.md)

[Next: Dependency Ownership](./11-Dependency-Ownership.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> Ownership is credible when the organization can identify the outcome, name the accountable team, exercise the authority, inspect the evidence, and recover when the system fails.

