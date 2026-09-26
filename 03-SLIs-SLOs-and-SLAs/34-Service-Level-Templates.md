# Service Level Templates

> These templates turn service-level decisions into versioned, reviewable records. Copy them, remove fields that genuinely do not apply, and preserve the reasoning behind every material choice.

## Section Purpose

This library contains twenty-nine directly usable Markdown and YAML templates. They share stable identifiers so records can be linked instead of duplicating definitions. Replace every placeholder; unresolved fields should say `unknown` with an owner and due date.

## 1. Service-Level Engineering Charter

```yaml
service: <catalog-id>
charter_version: 1.0.0
accountable_team: <team>
purpose: <user outcome protected>
in_scope: [<journey-or-operation>]
out_of_scope: [<explicit boundary>]
participants:
  product: <role>
  service: <role>
  sre: <role>
  data: <role>
decision_rights:
  approve_sli: <role>
  approve_slo: <role>
  accept_exception: <role>
authoritative_records: <path-or-url>
review_cadence: <cadence>
```

## 2. CUJ-to-Service-Level Map

```markdown
# CUJ-to-Service-Level Map: <journey>

| Field | Definition |
| --- | --- |
| User/consumer | |
| Intended outcome | |
| Start and successful end | |
| Critical steps | |
| Material failure | |
| Accountable journey owner | |

| Reliability dimension | User expectation | Candidate SLI | Decision supported |
| --- | --- | --- | --- |
| Availability | | | |
| Latency | | | |
| Correctness | | | |
| Quality/freshness/durability | | | |
```

## 3. Measurement Boundary Record

```yaml
boundary_id: <id>
service: <id>
consumer: <population>
event_start: <observable point>
event_end: <observable point>
eligible_population: <rule>
observation_point: <client-edge-server-or-downstream>
included_failures: [<failure>]
outside_boundary: [<condition>]
known_blind_spots: [<gap>]
correlation_key: <field>
timezone: UTC
owner: <team>
version: 1.0.0
```

## 4. Complete SLI Specification

```yaml
sli_id: <stable-id>
name: <name>
service: <service-id>
user_outcome: <outcome>
dimension: <availability|latency|correctness|quality|freshness|durability>
population: <eligible event rule>
good_event: <boolean rule>
bad_event: <boolean rule>
excluded_event: <narrow rule>
unknown_event: <rule>
formula: good_events / valid_events
unit: ratio
source: <authoritative dataset>
query_version: <commit-or-version>
segments: [<decision-relevant dimension>]
late_data_policy: <policy>
missing_data_policy: <policy>
sli_owner: <team>
data_owner: <team>
effective_from: <timestamp>
review_trigger: [<event>]
```

## 5. Valid-Event and Exclusion Policy

```markdown
# Event Eligibility Policy

- SLI ID:
- Eligible event definition:
- Duplicate/retry treatment:
- Synthetic traffic treatment:
- Invalid or unauthorized request treatment:
- Planned-maintenance treatment:
- Dependency-failure treatment:
- Unknown/missing treatment:

| Exclusion code | Exact rule | User affected? | Evidence | Approver | Expiry |
| --- | --- | --- | --- | --- | --- |

Exclusions are reported separately and never default to good.
```

## 6. Event-Classification Test Table

```markdown
| Test ID | Event facts | Expected class | Rule invoked | Reason | Actual | Pass? |
| --- | --- | --- | --- | --- | --- | --- |
| EVT-001 | | good/bad/excluded/unknown | | | | |

Reconciliation: good + bad = valid; valid + excluded + unknown = observed population.
```

## 7. Availability SLI

```yaml
dimension: availability
eligible_event: <valid attempt>
good_event: <required response or completed outcome>
formula: good_attempts / eligible_attempts
timeouts: bad
rejections: <rule>
partial_success: <rule>
measurement_boundary: <record-id>
```

## 8. Latency SLI

```yaml
dimension: latency
event_start: <timestamp definition>
event_end: <timestamp definition>
thresholds:
  - {limit_ms: 300, required_ratio: <target>}
  - {limit_ms: 1000, required_ratio: <target>}
timeouts: bad
successful_only: false
clock_and_sampling_limits: <limits>
```

## 9. Correctness SLI

```yaml
dimension: correctness
eligible_result: <result population>
correct_result: <domain-valid result>
validation_source: <reconciliation-or-truth-source>
formula: correct_results / eligible_results
late_discovery_policy: <restatement policy>
duplicates_and_omissions: <rules>
```

## 10. Quality and Degradation SLI

```yaml
dimension: quality
quality_levels:
  full: <criteria>
  degraded_acceptable: <criteria and weight>
  unusable: <criteria>
formula: <threshold ratio or weighted method>
degradation_visibility: <user-facing signal>
maximum_degraded_duration: <duration>
```

## 11. Freshness SLI

```yaml
dimension: freshness
source_event_time: <field>
available_time: <field>
maximum_age: <duration>
good_event: available_time - source_event_time <= maximum_age
timezone_and_watermark: <rules>
late_arrival_policy: <policy>
```

## 12. Durability SLI

```yaml
dimension: durability
committed_object: <object/event definition>
commit_point: <boundary>
preserved_and_retrievable: <test>
integrity_validation: <checksum/reconciliation>
observation_period: <period>
formula: valid_retrievable_objects / committed_objects
restore_evidence: <test record>
```

## 13. Batch and Pipeline SLI Set

```yaml
workload: <job-or-pipeline>
run_population: <scheduled and valid runs>
completion: {good: <completed>, deadline: <timestamp rule>}
completeness: {formula: processed_expected / expected}
correctness: {validation: <rule>, formula: correct / validated}
freshness: {maximum_age: <duration>}
rerun_policy: <whether original result is restated>
partial_run_policy: <rule>
```

## 14. Event-Driven SLI

```yaml
event_type: <type>
acceptance_point: <point>
completion_point: <promised effect>
correlation_key: <id>
completion_deadline: <duration>
exactly_once_expectation: <required behavior>
good_event: <accepted event reaches valid terminal state on time>
duplicates_missing_unknown: <rules>
```

## 15. Measurement-Source Decision Record

```markdown
# Measurement-Source Decision: <SLI ID>

| Candidate | Boundary | Coverage | Accuracy | Delay | Failure independence | Cost | Privacy | Decision |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | |

- Selected authority:
- Corroborating source:
- Known bias:
- Reconciliation control:
- Cutover and rollback plan:
- Approver and date:
```

## 16. Segmentation Plan

```yaml
sli_id: <id>
global_view: <purpose>
segments:
  - dimension: <region|operation|plan|client|journey>
    reason: <distinct harm or decision>
    minimum_volume: <rule>
    separate_objective: <true|false>
cardinality_controls: <rules>
reconciliation: segment totals must equal global totals
review_trigger: <mix or risk change>
```

## 17. SLI Data-Quality Control Plan

```markdown
| Quality dimension | Control | Threshold | Frequency | Failure behavior | Owner | Evidence |
| --- | --- | --- | --- | --- | --- | --- |
| Completeness | Source-to-traffic reconciliation | | | mark unknown | | |
| Uniqueness | Duplicate-key test | | | | | |
| Validity | Schema/range test | | | | | |
| Freshness | Ingestion lag | | | | | |
| Lineage | Version and source check | | | | | |
```

## 18. SLO Document

```yaml
slo_id: <id>
service: <id>
status: <provisional|approved|deprecated>
sli_specification: <id-and-version>
target: <ratio>
window: <rolling-or-calendar and duration>
scope: <population and segments>
rationale: <user need, risk, baseline, feasibility>
decision_use: <actions supported>
accountable_owner: <team>
approval_authority: <role>
dependencies: [<id>]
limitations: [<known limitation>]
effective_from: <date>
review_date: <date>
review_triggers: [<change>]
```

## 19. SLO Target Decision Record

```markdown
# Target Decision: <SLO ID>

- User harm being limited:
- Historical baseline and period:
- Demand and criticality:
- External/internal commitments:
- Measurement uncertainty:

| Candidate target | Permitted failure | User consequence | Engineering cost | Feasibility | Decision |
| --- | --- | --- | --- | --- | --- |

- Selected target and rationale:
- Rejected alternatives:
- Evidence that would trigger reconsideration:
- Decision-maker/date:
```

## 20. SLO Time-Window Decision Record

```yaml
slo_id: <id>
window_type: <rolling|calendar>
duration: <value>
timezone: UTC
calculation_frequency: <frequency>
late_data_cutoff: <duration>
restatement_policy: <policy>
low_volume_policy: <policy>
operational_reason: <reason>
reporting_reason: <reason>
approved_by: <role/date>
```

## 21. Multi-SLO Service Model

```markdown
| SLO ID | CUJ | Dimension | Segment/tier | SLI | Target/window | Decision | Owner |
| --- | --- | --- | --- | --- | --- | --- | --- |

Conflict rule:
Priority rule:
Why each objective is independently necessary:
Metrics intentionally retained as diagnostics rather than SLOs:
```

## 22. Dependency and End-to-End SLO Map

```markdown
| Journey step | Provider | Dependency type | Local measure | Assumption/commitment | Failure seen by user? | Escalation owner |
| --- | --- | --- | --- | --- | --- | --- |

- End-to-end success rule:
- Serial/parallel paths:
- Shared and correlated failure domains:
- Third-party boundary:
- Budget-allocation assumptions:
- Local-success/end-to-end-failure test:
```

## 23. Error-Budget Calculation Worksheet

```markdown
- SLO target `T`:
- Eligible volume `N`:
- Good events `G`:
- Bad events `B = N - G`:
- Allowed bad events `E = N × (1 - T)`:
- Budget consumed `B / E`:
- Budget remaining `E - B`:
- Measurement uncertainty:
- Segment/window:
- Interpretation and decision supported:
```

## 24. SLO Review and Approval Record

```markdown
| Review item | Evidence | Finding | Required change | Owner |
| --- | --- | --- | --- | --- |
| CUJ and boundary | | | | |
| SLI implementation/tests | | | | |
| Data quality | | | | |
| Target/window rationale | | | | |
| Dependency alignment | | | | |
| Decision use | | | | |

- Decision: approve / approve provisionally / reject / deprecate
- Effective version/date:
- Approvers:
- Next review or trigger:
```

## 25. SLO Governance Exception

```yaml
exception_id: <id>
slo_id: <id>
requirement_not_met: <requirement>
reason: <evidence>
risk: <user and decision risk>
temporary_controls: [<control>]
owner: <team>
approver: <authorized role>
issued: <date>
expires: <date>
closure_evidence: <required proof>
renewal_allowed: <true|false>
```

## 26. SLA Requirements Record

```markdown
# SLA Requirements Record

- Provider/customer:
- Covered service, users, locations, and operations:
- Commitment and compliance period:
- Measurement method and data authority:
- Reporting and correction process:
- Responsibilities and notification:
- Exclusions:
- Consequences/remedies:
- Claim window and evidence:
- Regulatory/commercial dependencies:
- Engineering feasibility owner:
- Legal/commercial approvers:
```

## 27. SLA Measurability Checklist

```markdown
- [ ] Covered population and boundary are unambiguous.
- [ ] Good, bad, excluded, and unknown outcomes are defined.
- [ ] Source, query, timezone, window, and rounding are authoritative.
- [ ] Planned maintenance and dependency treatment are bounded.
- [ ] Missing and corrected data have explicit rules.
- [ ] Provider and customer can obtain dispute evidence.
- [ ] Reporting, claim, credit, and correction timelines are operable.
- [ ] Architecture and internal SLO provide credible headroom.
- [ ] Engineering, commercial, and legal authorities approved the terms.
```

## 28. SLI-SLO-SLA Alignment Matrix

```markdown
| Layer | Measure/boundary | Target | Window | Source | Owner | Consequence | Headroom/conflict |
| --- | --- | --- | --- | --- | --- | --- | --- |
| SLI | | n/a | | | | measurement | |
| Internal SLO | | | | | | engineering decision | |
| Platform/vendor commitment | | | | | | escalation/remedy | |
| Customer SLA | | | | | | contractual consequence | |
```

## 29. Service-Level Health Review

```markdown
# Service-Level Health Review: <service>

- Review period/version:
- Material user or architecture changes:
- SLI coverage and data-quality status:
- SLO performance and decision history:
- SLA alignment and disputes:
- Unknowns and measurement failures:
- Anti-pattern findings:

| Action | Evidence/risk | Priority | Owner | Due | Verification |
| --- | --- | --- | --- | --- | --- |

- Objectives to retain/change/deprecate:
- Approval and next review:
```

## Template Use Rules

1. Link records with stable IDs; do not copy inconsistent definitions across files.
2. Keep specifications and queries in version control.
3. Require review for boundary, source, target, window, or eligibility changes.
4. Preserve past versions needed to reproduce historical reports.
5. Separate engineering approval from legal or commercial authorization.
6. Treat blank fields as defects; use explicit `not applicable` or tracked `unknown`.

## Navigation

- Previous: [Service Level Practical Exercises](33-Service-Level-Practical-Exercises.md)
- Next: [Service Level Resources](35-Service-Level-Resources.md)
- Collection: [SLIs, SLOs, and SLAs](README.md)

---

Part of **SRE World**, maintained by **VERIQTA**.
