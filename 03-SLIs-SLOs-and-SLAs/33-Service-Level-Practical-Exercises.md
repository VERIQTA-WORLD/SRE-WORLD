# Service Level Practical Exercises

> Service-level engineering becomes credible when a learner can produce definitions, calculations, decisions, and verification evidence that another engineer can reproduce.

## Section Purpose

These nineteen exercises form a practical portfolio. Use one consistent fictional or real service so the artifacts connect. Remove confidential data before contributing completed examples to a public repository.

## Standard Exercise Record

For every exercise record: scenario, supplied inputs, instructions, required calculation or decision, artifact, verification criteria, review questions, and optional extension.

## Exercise Set

### 1. Map a CUJ to Reliability Dimensions

**Scenario:** Users submit a payment and require exactly one durable confirmation. **Inputs:** journey steps, user types, failure examples. **Work:** identify availability, latency, correctness, durability, and quality needs without redefining the CUJ. **Artifact:** `cuj-service-level-map.md`. **Verify:** every proposed measure protects a stated outcome. **Review:** Which dimension would infrastructure uptime miss? **Extension:** add a machine consumer.

### 2. Define a Measurement Boundary

**Scenario:** Requests cross an edge, API, queue, worker, and database. **Inputs:** topology and telemetry locations. **Work:** choose event start, end, population, and observation point. **Artifact:** `measurement-boundary-record.md`. **Verify:** sampled events are included once and only once. **Review:** Which failures occur outside the boundary? **Extension:** compare client and server boundaries.

### 3. Write an SLI Specification

**Scenario:** Protect successful checkout. **Inputs:** outcome, event schema, known exceptions. **Work:** write population, numerator, denominator, thresholds, exclusions, source, segmentation, unknown handling, and owner. **Artifact:** `sli-specification.md`. **Verify:** two reviewers classify the same samples identically. **Review:** Can the specification be implemented without guessing? **Extension:** version a changed definition.

### 4. Classify Events

**Scenario:** A sample contains successes, timeouts, invalid requests, retries, telemetry gaps, and maintenance traffic. **Inputs:** 30 labeled event records. **Work:** classify valid, good, bad, excluded, or unknown and justify each rule. **Artifact:** `event-classification-tests.md`. **Verify:** totals reconcile and exclusions are independently visible. **Review:** Which classification is most open to manipulation? **Extension:** add late-arriving truth.

### 5. Calculate Availability

**Scenario:** 49,850 of 50,000 eligible requests succeed. **Inputs:** event counts and exclusion list. **Work:** calculate SLI, bad-event rate, and confidence concerns. **Artifact:** availability calculation in `sli-calculations.md`. **Verify:** numerator plus bad events equals eligible total. **Review:** Would time-based availability tell the same story? **Extension:** calculate by region.

### 6. Calculate Threshold Latency

**Scenario:** 98,700 of 100,000 valid requests finish within 300 ms; 99,600 finish within 1 s. **Work:** calculate both threshold SLIs and identify the experience each protects. **Artifact:** latency calculations. **Verify:** threshold populations are identical and nested. **Review:** Why is an average insufficient? **Extension:** define separate write and read thresholds.

### 7. Analyze a Latency Distribution

**Scenario:** A histogram shows a stable median and growing tail. **Inputs:** bucket counts by region. **Work:** compute threshold ratios, approximate relevant percentiles, and locate harmed segments. **Artifact:** distribution analysis. **Verify:** totals match raw events and bucket boundaries are documented. **Review:** Which conclusion is sensitive to bucket design? **Extension:** compare load bands.

### 8. Design Correctness, Freshness, and Batch SLIs

**Scenario:** A nightly account statement must be complete, correct, and available by 06:00. **Inputs:** source totals, reconciliation result, completion timestamps. **Work:** define three independent SLIs. **Artifact:** three specifications. **Verify:** a run can pass one dimension and fail another. **Review:** Is one composite score useful? **Extension:** handle a corrected rerun.

### 9. Compare Client and Server Measurement

**Scenario:** Edge and application counts disagree during network loss. **Inputs:** client probes, edge logs, server logs. **Work:** compare coverage, bias, delay, and authority. **Artifact:** `measurement-source-decision.md`. **Verify:** known pre-server failures are represented. **Review:** Which source is authoritative for which decision? **Extension:** add real-user telemetry privacy constraints.

### 10. Detect Aggregation Errors

**Scenario:** Global success is 99.95%, but one payment method is at 91%. **Inputs:** counts by region, operation, plan, and payment method. **Work:** calculate weighted totals and segment results; identify Simpson's-paradox risk. **Artifact:** `segmentation-plan.md`. **Verify:** segment numerators and denominators reconcile to the global result. **Review:** Which segment needs a separate objective? **Extension:** add minimum sample rules.

### 11. Audit SLI Data Quality

**Scenario:** Event counts fall 12% after an instrumentation release. **Inputs:** traffic, log, trace, and billing counts. **Work:** test completeness, freshness, uniqueness, validity, and lineage. **Artifact:** `sli-data-quality-plan.md`. **Verify:** each control has threshold, owner, and failure behavior. **Review:** When should compliance be unknown? **Extension:** design a dual-source reconciliation.

### 12. Write an SLO Document

**Scenario:** The checkout SLI is approved for operational use. **Inputs:** specification, baseline, user need, owner. **Work:** write objective, scope, target, window, rationale, decision use, dependencies, limitations, and review triggers. **Artifact:** `slo-document.md`. **Verify:** the result is reproducible and actionable. **Review:** What decision changes on breach? **Extension:** add a provisional status.

### 13. Select and Defend a Target

**Scenario:** Baseline ranges from 99.82% to 99.97%; users abandon after repeated failures. **Inputs:** impact, traffic, costs, external promises, historical data. **Work:** compare candidate targets and document trade-offs. **Artifact:** `slo-target-decision.md`. **Verify:** target follows evidence, not a familiar number. **Review:** What new evidence would change it? **Extension:** model investment scenarios.

### 14. Compare Time Windows

**Scenario:** A five-hour outage crosses month-end. **Inputs:** event counts for rolling 28-day and two calendar months. **Work:** calculate compliance and explain decision and reporting differences. **Artifact:** `time-window-decision.md`. **Verify:** timestamps, timezone, and late data rules are explicit. **Review:** Which window serves operations and which serves contract administration? **Extension:** add a weekly objective.

### 15. Derive an Error Budget

**Scenario:** An objective is 99.9% over 10 million eligible requests. **Work:** derive permitted bad events, consumed budget, remaining budget, and uncertainty for observed volume. **Artifact:** `error-budget-worksheet.md`. **Verify:** formulas reconcile with SLI compliance. **Review:** Why is this not an SLA penalty threshold? **Extension:** calculate a low-volume case.

### 16. Map Dependencies and End-to-End Objectives

**Scenario:** Sign-in depends on edge, identity, user store, and policy services. **Inputs:** local objectives and dependency paths. **Work:** map serial, parallel, shared, and third-party dependencies; identify local success with journey failure. **Artifact:** `dependency-slo-map.md`. **Verify:** every critical path and owner is represented. **Review:** Where can budgets not simply be added? **Extension:** model correlated failure.

### 17. Evaluate an SLA

**Scenario:** A draft promises 99.95% but does not define eligible requests or data authority. **Inputs:** draft terms and available measurements. **Work:** assess scope, calculation, exclusions, reporting, claims, and consequences. **Artifact:** `sla-measurability-review.md`. **Verify:** every commitment is measurable or explicitly flagged. **Review:** Which questions require legal or commercial authority? **Extension:** test a dispute.

### 18. Build an Alignment Matrix

**Scenario:** Vendor, internal platform, product SLO, and customer SLA use different boundaries. **Inputs:** four commitments. **Work:** map measure, threshold, window, source, owner, consequence, and headroom. **Artifact:** `sli-slo-sla-alignment-matrix.md`. **Verify:** conflicts and unsupported promises are visible. **Review:** Which commitment controls operations? **Extension:** propose renegotiation.

### 19. Review a Service-Level System

**Scenario:** Assess an existing service with dashboards and objectives. **Inputs:** specifications, queries, reports, ownership, decisions, and change history. **Work:** apply the anti-pattern assessment and prioritize corrections. **Artifact:** `service-level-health-review.md`. **Verify:** findings cite evidence and closure tests. **Review:** Which defect could most seriously misstate user harm? **Extension:** repeat after remediation.

## Expected Results and Solution Guidance

Use these expectations to review the artifacts. They identify required reasoning, not a single acceptable wording.

| Exercise | Minimum correct result |
| ---: | --- |
| 1 | The map begins with a consumer outcome and identifies at least two noninterchangeable dimensions. Components appear only as supporting evidence. |
| 2 | The record states entry, terminal state, observation point, correlation key, population, and blind spots. It explains one alternative boundary and why it was rejected. |
| 3 | Another engineer can implement the indicator without inventing eligibility, success, source, segment, or missing-data rules. |
| 4 | Every observation enters exactly one class after deduplication; good + bad = valid; excluded and unknown remain separately countable. |
| 5 | Availability equals `49,850 / 50,000 = 99.7%`. The learner states whether excluded or unknown events can change the conclusion. |
| 6 | The 300 ms SLI is 98.7 percent and the 1 s SLI is 99.6 percent. The learner does not average the two values. |
| 7 | Threshold counts reconcile to total observations; tail harm and segment differences are visible; percentiles are not averaged across groups. |
| 8 | Completion, correctness, and freshness or timeliness can pass or fail independently. A rerun does not erase the original missed deadline. |
| 9 | The decision names one authoritative source and at least one corroborating source, with bias, coverage, reconciliation, and cutover controls. |
| 10 | Global results are calculated from counts, not average percentages; mandatory segments are tied to distinct harm or action. |
| 11 | Controls cover completeness, uniqueness, validity, freshness, and lineage, and define when compliance becomes unknown. |
| 12 | The SLO references a versioned SLI and includes target, window, scope, rationale, owner, decision use, limitations, and review triggers. |
| 13 | At least three candidate targets are compared through allowed failure, user harm, cost, feasibility, and measurement uncertainty. |
| 14 | The learner calculates both rolling and calendar results and explains why one incident can appear differently without either calculation being wrong. |
| 15 | For 99.9 percent across 10 million events, allowed bad events equal 10,000. Consumption and remaining budget use observed bad events. |
| 16 | The map distinguishes local and end-to-end success, records shared failure domains, and avoids assuming dependency independence without evidence. |
| 17 | Every commitment is measurable or explicitly marked ambiguous; legal and commercial questions are not answered by engineering assumption. |
| 18 | The matrix compares complete definitions, not only percentages, and identifies whether operating headroom is real. |
| 19 | Findings distinguish measurement defects from service-performance problems and include verification evidence for closure. |

## Calculation Answer Example

For Exercise 15, if the service observes 7,500 bad events:

$$
Allowed = 10{,}000{,}000(1-0.999)=10{,}000
$$

$$
Consumed = \frac{7{,}500}{10{,}000}=75\%
$$

$$
Remaining = 10{,}000-7{,}500=2{,}500\ events
$$

If 4,000 additional outcomes are unknown, report a budget range. Do not treat them as good.

## Review Procedure

1. Exchange artifacts with another learner or reviewer.
2. Give the reviewer five raw events not used by the author.
3. Ask the reviewer to classify and calculate them using only the artifact.
4. Record every assumption the reviewer had to invent.
5. Revise the artifact until independent results match.
6. Change one boundary, source, or segment and evaluate which dependent artifacts require a new version.

## Portfolio Acceptance Criteria

- Definitions are implementation-ready and versioned.
- Calculations show formulas, units, populations, and rounding.
- Decisions identify evidence, authority, trade-offs, and review triggers.
- Unknown and missing data never silently become good.
- Artifacts agree with one another across boundary, source, target, and window.
- Verification includes adversarial or failure examples, not only normal traffic.

## Navigation

- Previous: [Service Level Production Scenarios](32-Service-Level-Production-Scenarios.md)
- Next: [Service Level Templates](34-Service-Level-Templates.md)
- Collection: [SLIs, SLOs, and SLAs](README.md)

---

Part of **SRE World**, maintained by **VERIQTA**.
