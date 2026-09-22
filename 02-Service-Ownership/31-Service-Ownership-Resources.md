# Service Ownership Resources

> Provide a curated map of authoritative books, standards, frameworks, documentation, and further study supporting service ownership practice.

## Section Purpose

Provide a curated map of authoritative books, standards, frameworks, documentation, and further study supporting service ownership practice.

Strong service ownership requires explicit outcomes, boundaries, accountable teams, authority, evidence, and review. A name in a catalog is not enough. The ownership arrangement must continue to work during change, failure, leave, reorganization, recovery, and retirement.

The practical output is a **Curated service-ownership resource index**.

This section is a guided resource map, not a link dump. It does not repeat the teaching content of Sections 1 through 30.

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
8. Produce and verify a complete Curated service-ownership resource index.

---

## 1. Google SRE books

Use the original Site Reliability Engineering book, The Site Reliability Workbook, and Building Secure and Reliable Systems for production ownership, service levels, toil, incident response, and organizational practice.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 2. Google SRE resources

Use sre.google for practices, case studies, reliability guidance, and public SRE material.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 3. Cloud architecture frameworks

AWS Well-Architected, Google Cloud Architecture Framework, and Microsoft Azure Well-Architected Framework provide provider-specific responsibility, reliability, operations, security, and cost guidance.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 4. CNCF material

CNCF technical advisory groups and project documentation support platform, cloud-native, observability, and operational ownership decisions.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 5. Backstage documentation

Backstage service-catalog concepts provide useful implementation ideas for software catalogs, entities, ownership, and relations.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 6. NIST publications

NIST Cybersecurity Framework, Secure Software Development Framework, contingency planning, and identity guidance support control and evidence ownership.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 7. IT service management

ITIL and related service-management practices offer language for service ownership, support, change, configuration, and continual improvement.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 8. Resilience and safety

Resilience engineering, human factors, learning-from-incidents, and safety literature broaden ownership beyond component uptime.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 9. Data governance

DAMA, NIST privacy material, and organizational data-governance standards support data ownership, stewardship, lineage, retention, and accountability.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 10. Internal evidence

Architecture decisions, incidents, service catalogs, support records, exercises, risk registers, and postmortems are primary sources for the organization's real ownership model.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## Primary Authoritative Resources

| Resource | Official location | Use for |
| --- | --- | --- |
| Google SRE books | [sre.google/books](https://sre.google/books/) | Production ownership, SLOs, toil, incidents, reliability practices, and organizational models |
| Google SRE resources | [sre.google/resources](https://sre.google/resources/) | Articles, practices, talks, and case material from the Google SRE community |
| AWS Well-Architected Framework | [aws.amazon.com/architecture/well-architected](https://aws.amazon.com/architecture/well-architected/) | Operational excellence, reliability, security, cost, and shared-responsibility decisions on AWS |
| Google Cloud Architecture Framework | [cloud.google.com/architecture/framework](https://cloud.google.com/architecture/framework) | Reliability, operations, security, cost, performance, and system-design guidance |
| Microsoft Azure Well-Architected Framework | [learn.microsoft.com/azure/well-architected](https://learn.microsoft.com/azure/well-architected/) | Workload ownership, reliability, operational excellence, security, performance, and cost guidance |
| Backstage Software Catalog | [backstage.io/docs/features/software-catalog](https://backstage.io/docs/features/software-catalog/) | Catalog entities, ownership metadata, relations, discoverability, and catalog implementation ideas |
| CNCF | [cncf.io](https://www.cncf.io/) | Cloud-native projects, technical guidance, platform practices, and community working groups |
| NIST Cybersecurity Framework | [nist.gov/cyberframework](https://www.nist.gov/cyberframework) | Governance, responsibility, risk, protection, detection, response, and recovery ownership |
| NIST Secure Software Development Framework | [csrc.nist.gov/Projects/ssdf](https://csrc.nist.gov/Projects/ssdf) | Secure software roles, practices, evidence, and development accountability |
| NIST Privacy Framework | [nist.gov/privacy-framework](https://www.nist.gov/privacy-framework) | Data processing, privacy risk, governance, and accountability |
| DORA | [dora.dev](https://dora.dev/) | Software-delivery performance, organizational capability, research, and measurement cautions |

### Resource Selection Rules

- Prefer official documentation, standards bodies, original books, and primary research.
- Use vendor guidance for the environment it actually covers.
- Separate a provider's responsibility from the consuming organization's accountability.
- Record which decision or practice the resource supports.
- State limitations and assumptions.
- Verify links, versions, and editions before publishing an update.
- Remove resources that are obsolete, duplicated, promotional, or unsupported.
- Do not add a resource only to increase the size of the list.

---

## 11. Core Principles

- Prefer primary sources
- Use resources for a defined decision
- Separate principles from vendor implementation
- Verify links and editions before publication
- Do not treat certification summaries as authority
- Record why a resource is included
- Review resources periodically
- Remove obsolete or low-value material

---

## 12. Operating Workflow

1. Define the ownership question
2. Choose primary authoritative sources
3. Compare guidance with organizational context
4. Record applicability and limitations
5. Extract a decision or practice
6. Test it against production evidence
7. Cite the source cleanly
8. Review the resource collection

The workflow should be proportionate to service criticality. High-consequence services require stronger evidence, more independent review, more frequent verification, and clearer escalation.

---

## 13. Required Evidence

Useful evidence includes:

- Resource review record
- Source authority
- Applicability note
- Decision influenced
- Last verification date
- Replacement or removal decision

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

A team copies a cloud-provider responsibility diagram without considering its own application, data, support, and recovery obligations. The resource review distinguishes provider responsibility from the organization's service-outcome accountability.

### Analysis Questions

1. What service or user outcome is at risk?
2. Which team is accountable for that outcome?
3. Which supporting owners must act?
4. Which decision rights are required?
5. What should happen immediately?
6. What evidence proves recovery?
7. Which durable correction prevents recurrence?

---

## 16. Practical Output: Curated service-ownership resource index

Create a record containing:

- Resource title:
- Publisher or author:
- Resource type:
- Ownership topic:
- Why it matters:
- Applicable audience:
- Limitations:
- Official location:
- Last verified:
- Related SRE World section:

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

- Completed Curated service-ownership resource index
- Owner acceptance
- Verification result
- Scenario analysis
- Open-gap register
- Corrective-action plan

---

## 18. Review Checklist

- [ ] Resource title is complete, current, and supported by evidence.
- [ ] Publisher or author is complete, current, and supported by evidence.
- [ ] Resource type is complete, current, and supported by evidence.
- [ ] Ownership topic is complete, current, and supported by evidence.
- [ ] Why it matters is complete, current, and supported by evidence.
- [ ] Applicable audience is complete, current, and supported by evidence.
- [ ] Limitations is complete, current, and supported by evidence.
- [ ] Official location is complete, current, and supported by evidence.
- [ ] Last verified is complete, current, and supported by evidence.
- [ ] Related SRE World section is complete, current, and supported by evidence.

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

1. Explain google sre books and identify the evidence that would prove it works.
2. Explain google sre resources and identify the evidence that would prove it works.
3. Explain cloud architecture frameworks and identify the evidence that would prove it works.
4. Explain cncf material and identify the evidence that would prove it works.
5. Explain backstage documentation and identify the evidence that would prove it works.
6. Explain nist publications and identify the evidence that would prove it works.
7. Explain it service management and identify the evidence that would prove it works.
8. Explain resilience and safety and identify the evidence that would prove it works.
9. Explain data governance and identify the evidence that would prove it works.
10. Explain internal evidence and identify the evidence that would prove it works.

---

## 20. Knowledge Check Answers

1. Use the original Site Reliability Engineering book, The Site Reliability Workbook, and Building Secure and Reliable Systems for production ownership, service levels, toil, incident response, and organizational practice.
2. Use sre.google for practices, case studies, reliability guidance, and public SRE material.
3. AWS Well-Architected, Google Cloud Architecture Framework, and Microsoft Azure Well-Architected Framework provide provider-specific responsibility, reliability, operations, security, and cost guidance.
4. CNCF technical advisory groups and project documentation support platform, cloud-native, observability, and operational ownership decisions.
5. Backstage service-catalog concepts provide useful implementation ideas for software catalogs, entities, ownership, and relations.
6. NIST Cybersecurity Framework, Secure Software Development Framework, contingency planning, and identity guidance support control and evidence ownership.
7. ITIL and related service-management practices offer language for service ownership, support, change, configuration, and continual improvement.
8. Resilience engineering, human factors, learning-from-incidents, and safety literature broaden ownership beyond component uptime.
9. DAMA, NIST privacy material, and organizational data-governance standards support data ownership, stewardship, lineage, retention, and accountability.
10. Architecture decisions, incidents, service catalogs, support records, exercises, risk registers, and postmortems are primary sources for the organization's real ownership model.

---

## 21. Key Takeaways

- Provide a curated map of authoritative books, standards, frameworks, documentation, and further study supporting service ownership practice.
- Ownership is defined by outcomes and obligations, not labels.
- One accountable team remains answerable for each defined scope.
- Supporting ownership must connect through explicit interfaces.
- Authority, access, knowledge, staffing, and evidence make ownership credible.
- Criticality determines the rigor of verification and review.
- Unknowns, exceptions, and temporary arrangements remain visible.
- Production recovery is complete only when the required outcome is verified.
- Ownership continues through organizational and lifecycle change.
- The Curated service-ownership resource index turns the section into an inspectable production artifact.

---

## Navigation

[Previous: Service Ownership Templates](./30-Service-Ownership-Templates.md)

[Next: Service Ownership Completion Assessment](./32-Service-Ownership-Completion-Assessment.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> Ownership is credible when the organization can identify the outcome, name the accountable team, exercise the authority, inspect the evidence, and recover when the system fails.
