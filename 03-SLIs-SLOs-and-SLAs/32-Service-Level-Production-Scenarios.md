# Service Level Production Scenarios

> Production evidence is incomplete, conflicting, and shaped by measurement choices. These scenarios test whether a learner can reconstruct the real service-level problem before choosing a remedy.

## Section Purpose

This section presents twelve realistic cases. For every case, analyze facts, unknowns, user impact, measurement boundary, SLI defects, SLO or SLA implications, immediate action, durable correction, authority, and verification evidence. Do not infer missing facts merely to complete the exercise.

## Analysis Record

```markdown
### Scenario
- Confirmed facts:
- Material unknowns:
- Affected user outcome:
- Measurement boundary:
- SLI defect or uncertainty:
- SLO/SLA implication:
- Immediate action:
- Durable correction:
- Accountable owner and decision authority:
- Evidence that verifies recovery and correction:
```

## 1. Available Checkout, Failed Payments

Checkout reports 99.99% availability. The SLI counts HTTP responses below 500 as good. A deployment causes the payment adapter to return `200` with `status: declined` for transactions that the provider actually authorized. Some customers retry and are charged twice.

Determine whether transport success belongs in the numerator, which semantic outcomes are bad, how to identify affected transactions, and who may suspend checkout. Verification must reconcile internal orders, provider authorizations, and customer-visible state.

## 2. Healthy Global Latency, Harmed Region

The global threshold SLI is 99.2% under 400 ms, above its 99% objective. In one region, only 82% meet the threshold and the 99th percentile exceeds eight seconds. That region provides 1.5% of global traffic and includes regulated customers.

Decide whether the original aggregation is defensible, which segment deserves an objective, and whether a low traffic share reduces the business obligation. Do not replace threshold analysis with a single percentile.

## 3. One Failed Payroll Run

A payroll pipeline runs monthly. Eleven prior runs succeeded; the current run misses the legal submission deadline. A request-style ratio would report 91.7% across twelve runs, while a monthly report contains only one eligible event.

Define timeliness, completeness, and correctness separately. Address low volume, binary period results, recovery evidence, and why a long historical average cannot erase the current missed deadline.

## 4. Accepted but Never Completed

An ingestion API acknowledges 99.999% of messages within 100 ms. A consumer offset defect prevents 7% from producing the promised downstream record. The producer sees successful acceptance.

Specify the end-to-end outcome, correlation key, completion deadline, duplicate handling, and unknown state. Decide whether acceptance and completion require separate SLIs rather than one composite that obscures the failure stage.

## 5. Silence Reported as Success

During a telemetry outage, no bad events are recorded. The dashboard query divides recorded bad events by expected traffic and treats absent series as zero bad. Reported compliance improves during the incident.

Identify the authoritative traffic evidence, quantify coverage, classify the affected interval, correct the report, and define when a result must be marked unknown. Verify by deliberately interrupting the measurement path.

## 6. Dependency Meets SLA, Journey Misses SLO

A third-party identity provider meets its 99.9% monthly SLA. Its failures occur during the retailer's peak hour, causing the sign-in journey to miss a 99.95% rolling SLO. The provider excludes scheduled maintenance that the retailer did not shield from users.

Separate contractual compliance from end-to-end reliability. Identify architectural controls, dependency assumptions, escalation rights, and whether the retailer's own SLO remains breached.

## 7. Proposed 100% Objective

A product team requests a 100% availability SLO for an optional profile-theme selector because “users expect it to work.” The feature has a safe default and no contractual commitment.

Require evidence for user harm, alternative behavior, cost, measurement uncertainty, and decision use. Propose a defensible objective or explain why the feature may not need a standalone SLO.

## 8. Internal and External Measurements Disagree

The internal SLO uses server-side valid requests over a 28-day rolling window. The customer SLA uses edge logs over each calendar month and includes a subset of regions. A network impairment affects clients before requests reach the service. Internal compliance passes; the SLA fails.

Map both definitions without forcing them to match. Identify the data authority, coverage gap, reporting correction process, and operating headroom needed to protect the external commitment.

## 9. Twenty-Seven Objectives, No Decisions

A service has 27 SLOs covering hosts, queues, endpoints, dependencies, and business transactions. All appear on a dashboard. There is no stated priority, owner, or action when one misses.

Classify which measures are diagnostics, which protect distinct user outcomes, and which duplicate one another. Produce a smaller decision-bearing set while retaining useful non-SLO telemetry.

## 10. Late Correctness Discovery

A reconciliation job discovers that 0.4% of invoices issued six weeks ago used the wrong tax rule. The monthly compliance report for that period was already approved at 99.99% correctness because the defect was not observable then.

Decide how late-arriving truth revises past reporting, which audit trail is required, whether an SLA claim can be reopened, and how detection lag becomes part of the measurement-quality model.

## 11. Query Changes Mid-Period

An engineer changes the SLI query on day 18 of a calendar month to exclude client-cancelled requests. Historical panels recalculate the entire month using the new logic, but the approved specification still uses the old definition.

Identify the authoritative version, effective date, parallel calculation, approval authority, and reporting annotation. Determine whether retroactive recomputation is permissible and how to preserve reproducibility.

## 12. Premium Promise Exceeds Architecture

Sales proposes a 99.99% SLA for premium customers. Premium and standard requests share the same storage, regional control plane, and recovery path. Current end-to-end performance is 99.93%, and traffic cannot be isolated during failure.

Assess feasibility, segmentation integrity, shared failure modes, headroom, contractual measurement, and who can accept the risk. State what must change before the commitment becomes supportable.

## Evaluation Standard

A strong analysis:

- separates confirmed evidence from assumptions;
- begins with the user outcome rather than the dashboard;
- states the exact measurement and reporting boundary;
- distinguishes SLI validity, SLO compliance, and SLA consequence;
- names both accountable team and authorized decision-maker;
- provides containment and a durable system correction;
- requires evidence that can disprove the claimed recovery.

## Practical Output

Complete one analysis record for each scenario and add a final comparison showing which failures arose from specification, implementation, data quality, target selection, governance, or contractual misalignment.

## Navigation

- Previous: [Service Level Anti-Patterns](31-Service-Level-Anti-Patterns.md)
- Next: [Service Level Practical Exercises](33-Service-Level-Practical-Exercises.md)
- Collection: [SLIs, SLOs, and SLAs](README.md)

---

Part of **SRE World**, maintained by **VERIQTA**.
