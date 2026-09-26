# Service Level Anti-Patterns

> A service-level system fails when its numbers look authoritative but do not represent user outcomes, support decisions, or remain trustworthy over time.

## Section Purpose

This section provides a diagnostic method for finding misleading SLIs, unusable SLOs, and misaligned SLAs. It applies the measurement and governance practices established earlier in this collection. It does not replace the dedicated observability, alerting, or error-budget policy collections.

## Assessment Method

For each candidate anti-pattern, record six things: the visible symptom, the concealed risk, the likely production consequence, the evidence that confirms the problem, the corrective action, and the evidence that proves correction. A concern is not closed merely because a query or dashboard changed.

## Anti-Pattern Assessment

| Anti-pattern | Symptom and hidden risk | Production consequence | Detection evidence | Corrective action | Verification |
| --- | --- | --- | --- | --- | --- |
| Any available metric becomes an SLI | The team starts with collected data rather than a user outcome. Easy-to-measure activity substitutes for reliability. | Reports stay green while the protected journey fails. | No written link from metric to CUJ, reliability dimension, and decision. | Begin with the outcome and write a complete SLI specification. | Trace sampled good and bad events from user result to numerator and denominator. |
| Infrastructure health represents user success | Host, pod, or database health is reported as service reliability. | Healthy components conceal failed transactions or unusable results. | Synthetic or client evidence disagrees with infrastructure dashboards. | Measure at the service boundary closest to the consumer. | Inject a semantic failure and confirm that the SLI becomes bad. |
| Availability means process uptime | A running process is counted as available regardless of responses. | Reachable but incorrect, slow, or rejected requests count as success. | Process uptime materially exceeds valid-request success. | Use eligible service interactions and explicit success criteria. | Reconcile request samples with user-visible outcomes. |
| Average latency is the latency SLI | One mean value hides distribution shape and tail harm. | A region or important segment experiences severe delay without an SLO miss. | Percentiles, histograms, or threshold ratios reveal a long tail. | Define good as eligible events completed below a justified threshold; segment where needed. | Replay known slow events and confirm correct classification. |
| HTTP 200 means correctness | Transport success is treated as a valid business result. | Empty, stale, duplicated, or incorrect results count as good. | Domain validation or downstream reconciliation contradicts status codes. | Add semantic success and integrity conditions. | Test representative incorrect `200` responses and confirm they count as bad. |
| Exclusions remove real failures | Broad maintenance, dependency, retry, or customer-error clauses shrink the denominator. | Reliability is overstated and affected users disappear from reports. | Exclusion volume rises during incidents or lacks a narrow reason code. | Permit only documented, bounded, attributable exclusions; report them separately. | Review excluded samples and trend exclusion rate alongside the SLI. |
| Missing data counts as good | Absent events, scrape gaps, or delayed telemetry default to success. | Monitoring failure improves the reported SLI. | Traffic records and SLI event counts diverge. | Classify missing evidence as unknown and define conservative reporting rules. | Disable the source in a test and confirm the result becomes unknown, not good. |
| Global averages hide segments | All users, regions, operations, or plans are combined. | Severe localized harm is diluted by healthy high-volume traffic. | Segment-level results differ materially from the global value. | Define decision-relevant segmentation and minimum-volume rules. | Recompute using known regional or cohort failures. |
| Every metric becomes an SLO | Dashboards contain many objectives with no priority or action. | Teams cannot tell which breach matters or what decision follows. | Objective inventory has no CUJ mapping, owner, or policy. | Keep only objectives that protect a meaningful outcome and trigger a defined decision. | Each retained SLO passes the outcome-owner-decision test. |
| Target is an arbitrary 99.9% | A familiar number is selected without evidence or trade-off analysis. | Investment is too high, too low, or directed at the wrong dimension. | No record of user need, baseline, risk, cost, or feasibility. | Use a target decision record with demand, harm, historical performance, and constraints. | Independent reviewers can reproduce the rationale from evidence. |
| SLO is 100% | The objective allows no measured failure or normal uncertainty. | Change freezes, hidden exclusions, and dishonest measurement follow. | Teams reinterpret eligibility or suppress bad events to preserve compliance. | Define the real tolerance and separately identify truly intolerable failure classes. | The target has explicit economic and user rationale and a usable error budget. |
| Target is copied from an SLA | A contractual threshold becomes the engineering objective without headroom. | Teams detect danger only when a contractual breach is imminent. | Internal and external thresholds are identical without justification. | Set an operating SLO that protects the external commitment with evidence-based headroom. | Alignment matrix shows threshold, source, window, and escalation differences. |
| SLA is the internal operating target | Operations optimize only to avoid credits or claims. | Users suffer before intervention and chronic near-breach performance becomes normal. | Reliability action begins only at the contractual boundary. | Establish a stronger internal SLO and leading indicators. | Governance records show action before the SLA threshold is threatened. |
| Objective has no owner | Nobody controls the specification, data, target, or review. | Defects and breaches persist without resolution. | Owner fields are missing, individual-only, or stale. | Assign accountable team, SLI owner, data owner, and approval authority. | Ownership is accepted and tested through a review or escalation exercise. |
| Objective has no decision | Compliance is reported but nothing changes. | SLO work becomes decorative measurement. | No documented response to healthy, at-risk, or breached states. | Define decision rights and expected actions for each state. | A tabletop proves that evidence reaches an authorized decision-maker. |
| Objective is never reviewed | The SLO outlives architecture, traffic, product, or criticality changes. | The number remains precise but no longer represents the service. | Review date is expired or material changes were not assessed. | Establish cadence and event-driven review triggers. | Version history records review, evidence, decision, and effective date. |
| Tooling generates the SLO without user analysis | A wizard proposes metrics and targets from telemetry alone. | Machine-visible behavior replaces actual user need. | No CUJ map, boundary record, or stakeholder validation exists. | Treat generated suggestions as drafts; perform user and service analysis. | Users, service owners, and measurement owners approve the specification. |
| Measurement source changes without versioning | Query, instrumentation, or provider changes silently alter results. | Trend breaks are mistaken for reliability change; compliance becomes disputed. | Step changes align with a source change but no version marker exists. | Version specifications and queries; use parallel measurement and a cutover record. | Old and new sources are reconciled and the effective boundary is explicit. |
| Dashboard is treated as the agreement | Visual configuration becomes the only definition. | Filters, defaults, and edits silently change meaning. | The team cannot produce a stable written specification. | Store authoritative definitions, owners, windows, and versions outside the dashboard. | A reviewer can reproduce the display from the approved record. |
| SLO is an individual performance target | Reliability is attributed to one person's appraisal. | People hide failure, avoid risk, and optimize the number rather than the system. | Performance reviews directly reward or punish individual SLO attainment. | Evaluate system outcomes and team practices; never use SLOs as individual quotas. | Governance and HR criteria separate learning evidence from individual blame. |

## Severity

- **Critical:** the defect can falsely declare compliance, conceal material user harm, or invalidate an external claim.
- **High:** the defect routinely drives the wrong engineering or product decision.
- **Medium:** the objective is usable but incomplete, fragile, or difficult to govern.
- **Low:** clarity or maintainability is reduced without changing the current result.

Prioritize integrity failures before target refinement. A sophisticated target cannot repair an invalid numerator, denominator, boundary, or data source.

## Practical Output: Service-Level Anti-Pattern Assessment

```markdown
# Service-Level Anti-Pattern Assessment

- Service:
- Assessor:
- Assessment date:
- Evidence period:

| Objective | Anti-pattern | Severity | Evidence | User or decision risk | Owner | Correction | Verification | Due date |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |

## Cross-cutting findings
## Immediate containment
## Required specification changes
## Required governance changes
## Residual uncertainty
## Approval
```

## Review Checklist

- [ ] Every finding cites inspectable evidence.
- [ ] Measurement integrity issues are separated from performance issues.
- [ ] A correction changes the authoritative specification, not only a chart.
- [ ] Verification can prove that known good, bad, excluded, and unknown events behave correctly.
- [ ] Owners and decision authority are named.
- [ ] Changes are versioned and communicated.

## Navigation

- Previous: [Aligning SLIs, SLOs, SLAs, and Internal Commitments](30-Aligning-SLIs-SLOs-SLAs-and-Internal-Commitments.md)
- Next: [Service Level Production Scenarios](32-Service-Level-Production-Scenarios.md)
- Collection: [SLIs, SLOs, and SLAs](README.md)

---

Part of **SRE World**, maintained by **VERIQTA**.
