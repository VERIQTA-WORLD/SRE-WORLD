# Measuring Ownership Health

> Measure whether service ownership is complete, current, capable, sustainable, and effective without rewarding empty metadata completion.

## Section Purpose

Measure whether service ownership is complete, current, capable, sustainable, and effective without rewarding empty metadata completion.

Strong service ownership requires explicit outcomes, boundaries, accountable teams, authority, evidence, and review. A name in a catalog is not enough. The ownership arrangement must continue to work during change, failure, leave, reorganization, recovery, and retirement.

The practical output is a **Ownership-health scorecard**.

This section measures ownership health. It does not measure complete service reliability, SLO attainment, team productivity, or individual performance.

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
8. Produce and verify a complete Ownership-health scorecard.

---

## 1. Coverage

Measure production services with an accepted accountable team, not merely a populated owner field.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 2. Freshness

Measure records reviewed within policy and after material change.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 3. Capability

Measure access, knowledge, support, change, incident, recovery, and lifecycle capability.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 4. Continuity

Measure qualified backups, single-person dependencies, temporary ownership, and turnover resilience.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 5. Reachability

Measure tested primary, secondary, specialist, vendor, and business escalation routes.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 6. Gap exposure

Track orphaned services, disputed scopes, expired exceptions, missing dimensions, and unresolved conditions.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 7. Operational outcomes

Use ownership-related incident delays, failed handoffs, unowned corrective actions, and recovery confusion.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 8. Sustainability

Assess service load, support burden, skill concentration, toil, and staffing capacity.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 9. Metric quality

Avoid vanity percentages, unverifiable self-attestation, and aggregation that hides critical services.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 10. Reporting

Segment by tier, lifecycle, organization, service type, risk, and age so leaders can act.

Ask:

- What exact outcome or scope is being owned?
- Which team remains accountable?
- Which authority, evidence, and interface make the assignment real?
- What production failure appears if this responsibility is missing?

---

## 11. Core Principles

- Measure functioning capability
- Criticality shapes interpretation
- Coverage and quality are separate
- Metrics lead to decisions
- Individuals are not ranked
- Uncertainty is visible
- Trends matter more than snapshots
- Measures are audited for gaming

---

## 12. Operating Workflow

1. Define ownership-health questions
2. Select indicators and data sources
3. Define numerator, denominator, exclusions, and freshness
4. Segment by consequence
5. Set review and escalation thresholds
6. Validate data quality
7. Review trends and causes
8. Assign improvement actions

The workflow should be proportionate to service criticality. High-consequence services require stronger evidence, more independent review, more frequent verification, and clearer escalation.

---

## 13. Required Evidence

Useful evidence includes:

- Metric dictionary
- Data-quality assessment
- Ownership scorecard
- Exception list
- Trend review
- Corrective-action register

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

A dashboard reports 99 percent ownership because nearly every record has a team name. Verification shows many teams no longer exist and critical contacts fail. The organization replaces field-completion metrics with accepted and verified ownership measures.

### Analysis Questions

1. What service or user outcome is at risk?
2. Which team is accountable for that outcome?
3. Which supporting owners must act?
4. Which decision rights are required?
5. What should happen immediately?
6. What evidence proves recovery?
7. Which durable correction prevents recurrence?

---

## 16. Practical Output: Ownership-health scorecard

Create a record containing:

- Metric name and decision:
- Definition:
- Population and exclusions:
- Data source:
- Frequency:
- Segmentation:
- Threshold:
- Owner:
- Known limitation:
- Required action:

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

- Completed Ownership-health scorecard
- Owner acceptance
- Verification result
- Scenario analysis
- Open-gap register
- Corrective-action plan

---

## 18. Review Checklist

- [ ] Metric name and decision is complete, current, and supported by evidence.
- [ ] Definition is complete, current, and supported by evidence.
- [ ] Population and exclusions is complete, current, and supported by evidence.
- [ ] Data source is complete, current, and supported by evidence.
- [ ] Frequency is complete, current, and supported by evidence.
- [ ] Segmentation is complete, current, and supported by evidence.
- [ ] Threshold is complete, current, and supported by evidence.
- [ ] Owner is complete, current, and supported by evidence.
- [ ] Known limitation is complete, current, and supported by evidence.
- [ ] Required action is complete, current, and supported by evidence.

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

1. Explain coverage and identify the evidence that would prove it works.
2. Explain freshness and identify the evidence that would prove it works.
3. Explain capability and identify the evidence that would prove it works.
4. Explain continuity and identify the evidence that would prove it works.
5. Explain reachability and identify the evidence that would prove it works.
6. Explain gap exposure and identify the evidence that would prove it works.
7. Explain operational outcomes and identify the evidence that would prove it works.
8. Explain sustainability and identify the evidence that would prove it works.
9. Explain metric quality and identify the evidence that would prove it works.
10. Explain reporting and identify the evidence that would prove it works.

---

## 20. Knowledge Check Answers

1. Measure production services with an accepted accountable team, not merely a populated owner field.
2. Measure records reviewed within policy and after material change.
3. Measure access, knowledge, support, change, incident, recovery, and lifecycle capability.
4. Measure qualified backups, single-person dependencies, temporary ownership, and turnover resilience.
5. Measure tested primary, secondary, specialist, vendor, and business escalation routes.
6. Track orphaned services, disputed scopes, expired exceptions, missing dimensions, and unresolved conditions.
7. Use ownership-related incident delays, failed handoffs, unowned corrective actions, and recovery confusion.
8. Assess service load, support burden, skill concentration, toil, and staffing capacity.
9. Avoid vanity percentages, unverifiable self-attestation, and aggregation that hides critical services.
10. Segment by tier, lifecycle, organization, service type, risk, and age so leaders can act.

---

## 21. Key Takeaways

- Measure whether service ownership is complete, current, capable, sustainable, and effective without rewarding empty metadata completion.
- Ownership is defined by outcomes and obligations, not labels.
- One accountable team remains answerable for each defined scope.
- Supporting ownership must connect through explicit interfaces.
- Authority, access, knowledge, staffing, and evidence make ownership credible.
- Criticality determines the rigor of verification and review.
- Unknowns, exceptions, and temporary arrangements remain visible.
- Production recovery is complete only when the required outcome is verified.
- Ownership continues through organizational and lifecycle change.
- The Ownership-health scorecard turns the section into an inspectable production artifact.

---

## Navigation

[Previous: Service Ownership Governance](./25-Service-Ownership-Governance.md)

[Next: Service Ownership Anti-Patterns](./27-Service-Ownership-Anti-Patterns.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> Ownership is credible when the organization can identify the outcome, name the accountable team, exercise the authority, inspect the evidence, and recover when the system fails.

