# Ownership of Data and State

> Define accountable ownership for service state, data meaning, integrity, access, schema, retention, backup, recovery, correction, and destruction.

## Section Purpose

Define accountable ownership for service state, data meaning, integrity, access, schema, retention, backup, recovery, correction, and destruction.

Strong service ownership requires explicit outcomes, boundaries, accountable teams, authority, evidence, and review. A name in a catalog is not enough. The ownership arrangement must continue to work during change, failure, leave, reorganization, recovery, and retirement.

The practical output is a **Data and state ownership record**.

This section focuses on data and state ownership. It does not repeat general service ownership or provide a full data-governance program.

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
8. Produce and verify a complete Data and state ownership record.

---

## 1. Authoritative state

Identify which state determines the truth of the service outcome and who may create, change, correct, or delete it.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 2. Data owner

The data owner remains accountable for purpose, classification, access, retention, integrity, and disposition.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 3. Data steward

The steward maintains definitions, quality rules, metadata, lineage, and governance practice.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 4. Platform owner

The platform owner provides reliable storage or processing without owning business meaning.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 5. Schema ownership

Define authority for schema change, compatibility, migration, validation, and consumer communication.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 6. Write ownership

Record which services and roles may write, under which conditions, and how conflicting writes are prevented.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 7. Integrity ownership

Define detection, containment, reconciliation, correction, user remediation, and verification.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 8. Backup and restore

Separate backup production, custody, restore execution, application compatibility, and outcome validation.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 9. Retention and deletion

Connect legal, business, privacy, operational, archival, and litigation requirements to authorized execution.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 10. State transfer

Ownership transfer and retirement require explicit data custody, export, migration, access removal, and destruction evidence.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 11. Core Principles

- Data meaning has an owner
- Storage administration is not data ownership
- Write authority is explicit
- Schema changes protect consumers
- Integrity failures have correction ownership
- Backup is not recovery
- Retention and deletion are authorized
- Data custody persists through lifecycle change

---

## 12. Operating Workflow

1. Inventory service data and state
2. Identify authoritative sources
3. Assign owner, steward, and platform roles
4. Map read, write, schema, and lineage relationships
5. Define integrity and recovery responsibilities
6. Set retention and disposition rules
7. Test restore and correction
8. Review changes and evidence

The workflow should be proportionate to service criticality. High-consequence services require stronger evidence, more independent review, more frequent verification, and clearer escalation.

---

## 13. Required Evidence

Useful evidence includes:

- Data ownership record
- Classification
- Schema history
- Lineage map
- Access review
- Integrity incident record
- Restore test
- Deletion evidence

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

A payment record is duplicated after a retry. The database platform is healthy, but business state is incorrect. The Payments team owns detection and correction logic, the data owner approves remediation, and the database team supports safe execution.

### Analysis Questions

1. What service or user outcome is at risk?
2. Which team is accountable for that outcome?
3. Which supporting owners must act?
4. Which decision rights are required?
5. What should happen immediately?
6. What evidence proves recovery?
7. Which durable correction prevents recurrence?

---

## 16. Practical Output: Data and state ownership record

Create a record containing:

- Data set and purpose:
- Authoritative state:
- Data owner and steward:
- Platform owner:
- Read and write authorities:
- Schema and consumer ownership:
- Integrity and correction:
- Backup and recovery:
- Retention and deletion:
- Transfer and retirement obligations:

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

- Completed Data and state ownership record
- Owner acceptance
- Verification result
- Scenario analysis
- Open-gap register
- Corrective-action plan

---

## 18. Review Checklist

- [ ] Data set and purpose is complete, current, and supported by evidence.
- [ ] Authoritative state is complete, current, and supported by evidence.
- [ ] Data owner and steward is complete, current, and supported by evidence.
- [ ] Platform owner is complete, current, and supported by evidence.
- [ ] Read and write authorities is complete, current, and supported by evidence.
- [ ] Schema and consumer ownership is complete, current, and supported by evidence.
- [ ] Integrity and correction is complete, current, and supported by evidence.
- [ ] Backup and recovery is complete, current, and supported by evidence.
- [ ] Retention and deletion is complete, current, and supported by evidence.
- [ ] Transfer and retirement obligations is complete, current, and supported by evidence.

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

1. Explain authoritative state and identify the evidence that would prove it works.
2. Explain data owner and identify the evidence that would prove it works.
3. Explain data steward and identify the evidence that would prove it works.
4. Explain platform owner and identify the evidence that would prove it works.
5. Explain schema ownership and identify the evidence that would prove it works.
6. Explain write ownership and identify the evidence that would prove it works.
7. Explain integrity ownership and identify the evidence that would prove it works.
8. Explain backup and restore and identify the evidence that would prove it works.
9. Explain retention and deletion and identify the evidence that would prove it works.
10. Explain state transfer and identify the evidence that would prove it works.

---

## 20. Knowledge Check Answers

1. Identify which state determines the truth of the service outcome and who may create, change, correct, or delete it.
2. The data owner remains accountable for purpose, classification, access, retention, integrity, and disposition.
3. The steward maintains definitions, quality rules, metadata, lineage, and governance practice.
4. The platform owner provides reliable storage or processing without owning business meaning.
5. Define authority for schema change, compatibility, migration, validation, and consumer communication.
6. Record which services and roles may write, under which conditions, and how conflicting writes are prevented.
7. Define detection, containment, reconciliation, correction, user remediation, and verification.
8. Separate backup production, custody, restore execution, application compatibility, and outcome validation.
9. Connect legal, business, privacy, operational, archival, and litigation requirements to authorized execution.
10. Ownership transfer and retirement require explicit data custody, export, migration, access removal, and destruction evidence.

---

## 21. Key Takeaways

- Define accountable ownership for service state, data meaning, integrity, access, schema, retention, backup, recovery, correction, and destruction.
- Ownership is defined by outcomes and obligations, not labels.
- One accountable team remains answerable for each defined scope.
- Supporting ownership must connect through explicit interfaces.
- Authority, access, knowledge, staffing, and evidence make ownership credible.
- Criticality determines the rigor of verification and review.
- Unknowns, exceptions, and temporary arrangements remain visible.
- Production recovery is complete only when the required outcome is verified.
- Ownership continues through organizational and lifecycle change.
- The Data and state ownership record turns the section into an inspectable production artifact.

---

## Navigation

[Previous: Third-Party and Vendor Service Ownership](./21-Third-Party-and-Vendor-Service-Ownership.md)

[Next: Ownership of Control Planes and Shared Infrastructure](./23-Ownership-of-Control-Planes-and-Shared-Infrastructure.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> Ownership is credible when the organization can identify the outcome, name the accountable team, exercise the authority, inspect the evidence, and recover when the system fails.

