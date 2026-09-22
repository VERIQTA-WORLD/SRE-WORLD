# Service Catalogs

> Explain how a service catalog provides a discoverable operational index without becoming a passive inventory or a replacement for ownership.

## Section Purpose

Explain how a service catalog provides a discoverable operational index without becoming a passive inventory or a replacement for ownership.

Strong service ownership requires explicit outcomes, boundaries, accountable teams, authority, evidence, and review. A name in a catalog is not enough. The ownership arrangement must continue to work during change, failure, leave, reorganization, recovery, and retirement.

The practical output is a **Service-catalog operating model**.

This section defines catalog purpose and operating behavior. It does not define every metadata field, which belongs in Section 10.

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
8. Produce and verify a complete Service-catalog operating model.

---

## 1. Catalog purpose

A service catalog helps people discover what exists, what it does, who owns it, how critical it is, and where authoritative operational information lives.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 2. Catalog versus inventory

An inventory proves that an item exists. A catalog adds relationships, ownership, lifecycle, interfaces, and operational context.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 3. Catalog scope

The catalog should include production services, internal services, platforms, data services, batch workloads, control planes, and relevant external dependencies.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 4. Authoritative sources

Catalog fields should reference authoritative systems rather than becoming uncontrolled copies.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 5. Federated catalogs

Large organizations may federate several catalogs while preserving stable service identifiers and shared minimum fields.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 6. Catalog onboarding

New production candidates should meet minimum catalog requirements before launch.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 7. Catalog maintenance

Lifecycle transitions, reorganizations, incidents, and architecture changes should trigger updates.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 8. Search and discovery

Users should be able to find services by outcome, owner, dependency, classification, technology, and business capability.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 9. Access and privacy

Public, internal, restricted, and sensitive views should expose only appropriate information.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 10. Catalog health

Freshness, completeness, reachability, ownership acceptance, and orphan detection measure whether the catalog is useful.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 11. Core Principles

- The catalog represents services, not only repositories
- Every record has a stable identifier
- Minimum fields are governed
- Authoritative sources are explicit
- Updates follow real production change
- Views respect information classification
- Catalog records link rather than duplicate where possible
- Catalog quality is measured

---

## 12. Operating Workflow

1. Define catalog users and decisions
2. Define included service types
3. Set minimum entry and exit criteria
4. Choose authoritative sources for each field
5. Design discovery and access views
6. Onboard existing services by criticality
7. Automate safe synchronization and stale-data checks
8. Review quality and ownership

The workflow should be proportionate to service criticality. High-consequence services require stronger evidence, more independent review, more frequent verification, and clearer escalation.

---

## 13. Required Evidence

Useful evidence includes:

- Catalog entry
- Source-system reference
- Ownership acceptance
- Freshness timestamp
- Dependency relationship
- Lifecycle history
- Access classification

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

An incident affects authentication. Responders search the catalog, identify consuming services, find the owning team, review the escalation route, and locate the recovery guide. The catalog shortens discovery without replacing the authoritative runbook or incident system.

### Analysis Questions

1. What service or user outcome is at risk?
2. Which team is accountable for that outcome?
3. Which supporting owners must act?
4. Which decision rights are required?
5. What should happen immediately?
6. What evidence proves recovery?
7. Which durable correction prevents recurrence?

---

## 16. Practical Output: Service-catalog operating model

Create a record containing:

- Catalog purpose and users:
- In-scope service types:
- Minimum entry requirements:
- Authoritative data sources:
- Update triggers:
- Access views:
- Quality controls:
- Governance owner:
- Exception process:
- Success measures:

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

- Completed Service-catalog operating model
- Owner acceptance
- Verification result
- Scenario analysis
- Open-gap register
- Corrective-action plan

---

## 18. Review Checklist

- [ ] Catalog purpose and users is complete, current, and supported by evidence.
- [ ] In-scope service types is complete, current, and supported by evidence.
- [ ] Minimum entry requirements is complete, current, and supported by evidence.
- [ ] Authoritative data sources is complete, current, and supported by evidence.
- [ ] Update triggers is complete, current, and supported by evidence.
- [ ] Access views is complete, current, and supported by evidence.
- [ ] Quality controls is complete, current, and supported by evidence.
- [ ] Governance owner is complete, current, and supported by evidence.
- [ ] Exception process is complete, current, and supported by evidence.
- [ ] Success measures is complete, current, and supported by evidence.

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

1. Explain catalog purpose and identify the evidence that would prove it works.
2. Explain catalog versus inventory and identify the evidence that would prove it works.
3. Explain catalog scope and identify the evidence that would prove it works.
4. Explain authoritative sources and identify the evidence that would prove it works.
5. Explain federated catalogs and identify the evidence that would prove it works.
6. Explain catalog onboarding and identify the evidence that would prove it works.
7. Explain catalog maintenance and identify the evidence that would prove it works.
8. Explain search and discovery and identify the evidence that would prove it works.
9. Explain access and privacy and identify the evidence that would prove it works.
10. Explain catalog health and identify the evidence that would prove it works.

---

## 20. Knowledge Check Answers

1. A service catalog helps people discover what exists, what it does, who owns it, how critical it is, and where authoritative operational information lives.
2. An inventory proves that an item exists. A catalog adds relationships, ownership, lifecycle, interfaces, and operational context.
3. The catalog should include production services, internal services, platforms, data services, batch workloads, control planes, and relevant external dependencies.
4. Catalog fields should reference authoritative systems rather than becoming uncontrolled copies.
5. Large organizations may federate several catalogs while preserving stable service identifiers and shared minimum fields.
6. New production candidates should meet minimum catalog requirements before launch.
7. Lifecycle transitions, reorganizations, incidents, and architecture changes should trigger updates.
8. Users should be able to find services by outcome, owner, dependency, classification, technology, and business capability.
9. Public, internal, restricted, and sensitive views should expose only appropriate information.
10. Freshness, completeness, reachability, ownership acceptance, and orphan detection measure whether the catalog is useful.

---

## 21. Key Takeaways

- Explain how a service catalog provides a discoverable operational index without becoming a passive inventory or a replacement for ownership.
- Ownership is defined by outcomes and obligations, not labels.
- One accountable team remains answerable for each defined scope.
- Supporting ownership must connect through explicit interfaces.
- Authority, access, knowledge, staffing, and evidence make ownership credible.
- Criticality determines the rigor of verification and review.
- Unknowns, exceptions, and temporary arrangements remain visible.
- Production recovery is complete only when the required outcome is verified.
- Ownership continues through organizational and lifecycle change.
- The Service-catalog operating model turns the section into an inspectable production artifact.

---

## Navigation

[Previous: Decision Rights and Production Authority](./08-Decision-Rights-and-Production-Authority.md)

[Next: Service Ownership Metadata](./10-Service-Ownership-Metadata.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> Ownership is credible when the organization can identify the outcome, name the accountable team, exercise the authority, inspect the evidence, and recover when the system fails.

