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
