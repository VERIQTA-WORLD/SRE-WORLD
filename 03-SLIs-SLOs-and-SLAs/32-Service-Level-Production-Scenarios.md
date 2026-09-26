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

## Model Analyses

The analyses below demonstrate the expected reasoning. A real investigation may reach a different conclusion when additional evidence changes the facts.

### Scenario 1 Analysis: Available Checkout, Failed Payments

- **Facts:** the availability indicator treats non-5xx responses as good; authorized payments and order state disagree; retries created duplicate charges.
- **Unknowns:** affected population, duration, provider behavior, idempotency coverage, and whether all duplicates are known.
- **User impact:** financial harm and ambiguous order state.
- **Boundary:** one logical checkout attempt must extend through authorization, exactly-one order creation, and durable confirmation.
- **SLI defect:** HTTP status represents transport, not semantic correctness.
- **Implication:** the reported 99.99 percent does not establish checkout reliability; correctness attainment must be recalculated.
- **Immediate action:** stop unsafe processing or route to a safe mode, identify transactions, prevent further duplicates, and reconcile customers.
- **Durable correction:** implement idempotent business effects and a reconciled correctness SLI.
- **Authority:** checkout owner directs mitigation; payments, finance, support, and risk owners handle correction and communication.
- **Verification:** provider authorizations, ledger entries, orders, and customer confirmations reconcile one to one.

### Scenario 2 Analysis: Healthy Global Latency, Harmed Region

- **Facts:** global threshold attainment passes; one region has 82 percent attainment and severe tail delay; regulated users are present.
- **Unknowns:** cause, regional demand pattern, contractual scope, and whether measurement coverage differs.
- **User impact:** a small global share experiences material delay.
- **Boundary:** retain the same valid-request boundary, segmented by region.
- **SLI defect:** aggregation hides a decision-relevant population.
- **Implication:** global compliance does not excuse the protected regional failure.
- **Immediate action:** declare regional impact, investigate routing and dependencies, and apply safe traffic control.
- **Durable correction:** define mandatory regional segmentation and a separate objective if harm or commitments differ.
- **Authority:** service owner acts; regional risk and product owners decide tolerance.
- **Verification:** raw segment counts reconcile globally and regional threshold and tail behavior recover.

### Scenario 3 Analysis: Failed Payroll Run

- **Facts:** the only run in the current month missed a legal deadline.
- **Unknowns:** completeness, correctness, workaround, and downstream acceptance.
- **User impact:** payroll or regulatory processing is late.
- **Boundary:** source-ready or scheduled time through validated submission availability.
- **SLI defect:** a twelve-run historical average dilutes the current deadline failure.
- **Implication:** current-period timeliness is 0 percent; longer history may inform planning, not overwrite the miss.
- **Immediate action:** execute authorized recovery, notify stakeholders, and preserve evidence.
- **Durable correction:** separate completion, timeliness, completeness, and correctness SLIs.
- **Authority:** payroll service and business-process owners coordinate; compliance authority handles regulatory action.
- **Verification:** accepted submission, complete population reconciliation, and documented achieved deadline.

### Scenario 4 Analysis: Accepted but Never Completed

- **Facts:** acceptance is excellent; 7 percent never produce the promised record.
- **Unknowns:** affected event types, replay safety, backlog age, duplicates, and loss point.
- **User impact:** producers receive false confidence while required effects are absent.
- **Boundary:** acceptance and end-to-end completion require separate indicators joined by event ID.
- **SLI defect:** the indicator ends at acknowledgement.
- **Implication:** acceptance SLO may pass while completion SLO fails severely.
- **Immediate action:** stop unsafe acknowledgement if necessary, contain consumers, and replay only with idempotency controls.
- **Durable correction:** define terminal states, completion deadline, reconciliation, and unknown handling.
- **Authority:** event-service owner manages recovery; downstream owners verify effects.
- **Verification:** every accepted event reaches one valid terminal state and totals reconcile.

### Scenario 5 Analysis: Silence Reported as Success

- **Facts:** missing telemetry removes bad events and improves the result.
- **Unknowns:** actual service performance and exact missing population.
- **User impact:** cannot be established reliably from the failed source.
- **Boundary:** unchanged; the measurement system has failed.
- **SLI defect:** absence is coerced to zero bad rather than unknown.
- **Implication:** compliance is indeterminate for the affected interval.
- **Immediate action:** mark reporting unknown, use independent sources, and communicate uncertainty.
- **Durable correction:** coverage controls, source reconciliation, and fail-closed compliance logic.
- **Authority:** data owner repairs measurement; SLO owner controls the compliance statement.
- **Verification:** a deliberate source interruption produces an unknown state and an independent alert.

### Scenario 6 Analysis: Provider Meets SLA, Journey Misses SLO

- **Facts:** provider meets its agreement; concentrated failures break the retailer's journey; maintenance was not shielded.
- **Unknowns:** provider exclusion details, fallback feasibility, and peak impact.
- **User impact:** customers cannot sign in at a high-value time.
- **Boundary:** retailer's end-to-end sign-in journey, not provider compliance.
- **SLI defect:** none necessarily; the dependency model or target assumption is inadequate.
- **Implication:** the retailer's SLO remains missed even when no provider remedy applies.
- **Immediate action:** activate fallback or degraded access and escalate with evidence.
- **Durable correction:** reduce dependency concentration, cache safely, or revise the unsupported target.
- **Authority:** retailer owns customer outcome; vendor manager administers the SLA.
- **Verification:** failure injection shows the journey remains within its objective during allowed provider disruption.

### Scenario 7 Analysis: Proposed 100 Percent Objective

- **Facts:** feature is noncritical and has a safe default; no external commitment exists.
- **Unknowns:** actual user harm, traffic, dependency cost, and whether a standalone SLO supports a decision.
- **User impact:** limited if fallback is correct.
- **Boundary:** theme selection through durable application of preference.
- **SLI defect:** none yet; target reasoning is absent.
- **Implication:** 100 percent creates no error budget and is difficult to measure honestly.
- **Immediate action:** reject arbitrary approval and collect baseline and harm evidence.
- **Durable correction:** choose a defensible lower target or retain the measure as diagnostic telemetry.
- **Authority:** product and service owners decide with risk evidence.
- **Verification:** target decision record explains trade-offs and resulting actions.

### Scenario 8 Analysis: Internal and External Measures Disagree

- **Facts:** sources, populations, and windows differ; client failures occur before the server boundary.
- **Unknowns:** exact contract definitions, source completeness, and reporting corrections.
- **User impact:** customers experience failures that the internal SLI cannot see.
- **Boundary:** maintain both definitions but map them explicitly.
- **SLI defect:** internal measure is too narrow if described as complete user availability.
- **Implication:** internal SLO can pass while SLA fails.
- **Immediate action:** calculate both authoritatively and follow SLA notice and claim procedures.
- **Durable correction:** add edge or client evidence and sufficient internal headroom.
- **Authority:** SLO owner governs internal measure; SLA authority handles external commitment.
- **Verification:** alignment matrix and replayed pre-server failure show both expected results.

### Scenario 9 Analysis: Twenty-Seven Objectives

- **Facts:** many objectives exist without owners, priority, or response.
- **Unknowns:** which protect unique CUJs and which duplicate diagnostics.
- **User impact:** decision delay and divided reliability focus.
- **Boundary:** reassess each objective against a protected outcome.
- **SLI defect:** possible metric-to-SLO promotion without user analysis.
- **Implication:** compliance reporting has little operational meaning.
- **Immediate action:** preserve telemetry but suspend unsupported governance claims.
- **Durable correction:** retain the smallest set with distinct user outcome, owner, and decision.
- **Authority:** accountable service owner approves the objective portfolio.
- **Verification:** every retained SLO passes the outcome-owner-decision test.

### Scenario 10 Analysis: Late Correctness Discovery

- **Facts:** 0.4 percent of invoices were wrong; the prior report lacked observability.
- **Unknowns:** full affected population, legal correction duties, and claim reopening terms.
- **User impact:** incorrect financial or tax records.
- **Boundary:** issue through later authoritative validation.
- **SLI defect:** the finalization model ignored delayed truth.
- **Implication:** historical correctness must be restated or annotated; SLA treatment depends on terms.
- **Immediate action:** correct invoices, notify authorities as required, and preserve original evidence.
- **Durable correction:** provisional reporting, reconciliation coverage, and late-data policy.
- **Authority:** service and finance owners correct data; legal or compliance authority decides notifications.
- **Verification:** all invoices reconcile against the authoritative tax rule and amended reports retain audit history.

### Scenario 11 Analysis: Query Changes Mid-Period

- **Facts:** logic changed without specification approval and rewrote prior days.
- **Unknowns:** whether cancellations are eligible and how much attainment changed.
- **User impact:** reliability may be misstated.
- **Boundary:** controlled by the approved specification, not the edited dashboard.
- **SLI defect:** implementation and semantic version are no longer aligned.
- **Implication:** current report is not authoritative.
- **Immediate action:** freeze the change, restore or reproduce the approved query, and calculate both versions.
- **Durable correction:** code review, immutable versions, effective dates, and parallel cutover.
- **Authority:** SLI owner and approval authority decide semantic changes.
- **Verification:** historical results reproduce from pinned source and query versions.

### Scenario 12 Analysis: Unsupported Premium Commitment

- **Facts:** premium traffic shares failure domains with standard traffic; baseline misses the proposed target; isolation is absent.
- **Unknowns:** investment plan, traffic mix, pricing exposure, and legal terms.
- **User impact:** premium customers would receive a promise the system cannot distinguish or support.
- **Boundary:** premium population must be identifiable end to end.
- **SLI defect:** segmentation may be unimplementable.
- **Implication:** the SLA is not technically feasible and lacks headroom.
- **Immediate action:** do not approve the promise; document quantified risk.
- **Durable correction:** build isolation and prioritization, choose a supportable commitment, or renegotiate scope.
- **Authority:** engineering provides evidence; authorized commercial and legal leaders control commitment.
- **Verification:** load and failure tests prove premium segmentation and historical evidence supports headroom.

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
