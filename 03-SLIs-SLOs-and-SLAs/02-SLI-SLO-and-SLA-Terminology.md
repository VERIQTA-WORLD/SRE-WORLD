# SLI, SLO, and SLA Terminology

> Precise terminology prevents teams from measuring one thing, promising another, and making decisions about neither.

## Section Purpose

This section establishes the vocabulary used throughout the collection. It separates concepts that are frequently collapsed into “uptime,” including indicators, objectives, agreements, error budgets, compliance periods, operational commitments, recovery objectives, KPIs, and KRIs.

Later sections design and implement these artifacts. This section defines their meaning, relationships, and authority boundaries.

## Learning Objectives

After completing this section, you should be able to:

1. Define SLI, SLO, and SLA without using the terms interchangeably.
2. Distinguish a measurement from a target, and a target from a commitment.
3. Explain valid, good, bad, excluded, and unknown events.
4. Distinguish measurement windows, compliance periods, and reporting periods.
5. Explain error budgets without confusing them with SLA credits.
6. Separate service levels from KPIs, KRIs, RTOs, RPOs, OLAs, and support promises.
7. Diagnose ambiguous service-level language.

## 1. Service Level

A **service level** is the measured degree to which a service delivers a defined behavior to a defined population under stated conditions during a stated period.

“The service level was 99.9 percent” is incomplete. It could refer to request success, process uptime, latency compliance, durability, or an SLA calculation with exclusions. A complete statement identifies:

- the behavior;
- the consumer population;
- the eligible events or intervals;
- the success criteria;
- the observation point;
- the calculation period.

## 2. Service Level Indicator

A **Service Level Indicator**, or **SLI**, is a carefully specified quantitative measure of one aspect of delivered service.

For an event-based indicator:

$$
SLI = \frac{\text{good valid events}}{\text{all valid events}}
$$

If 9,970 of 10,000 valid operations complete correctly within the required threshold:

$$
SLI = \frac{9{,}970}{10{,}000} = 0.997 = 99.7\%
$$

The result is meaningful only if “valid operation” and “complete correctly” are defined. `http_requests_total` is a raw metric. “Proportion of eligible checkout attempts that create exactly one correct order within two seconds” is an SLI. Several raw events may be joined to implement it.

## 3. Service Level Objective

A **Service Level Objective**, or **SLO**, is a target value or acceptable range for an SLI over a defined compliance period.

A complete SLO states:

- the referenced SLI and version;
- the target;
- the compliance window;
- the population and segments;
- the accountable owner;
- the decision the objective supports;
- the effective date and review triggers.

Example:

> At least 99.95 percent of eligible checkout attempts will create exactly one correct order within two seconds over each rolling 28-day window, measured by `checkout-completion-sli` version 2.1.

The sentence is complete enough to evaluate, but the target still requires evidence and approval.

## 4. Service Level Agreement

A **Service Level Agreement**, or **SLA**, is an agreement between identified parties that contains measurable service commitments, responsibilities, administration rules, and consequences when commitments are not met.

Consequences may include service credits, refunds, corrective plans, escalation, termination rights, or another agreed remedy. An SLA normally defines:

- provider and customer;
- covered service, users, operations, and locations;
- commitment and compliance period;
- measurement method and authoritative source;
- exclusions;
- reporting and notification;
- claim procedure;
- remedies and dispute handling.

SRE and engineering assess measurability and feasibility. They do not unilaterally create contractual language or interpret legal enforceability.

## 5. SLI, SLO, and SLA Compared

| Concept | Function | Core question | Example | Miss consequence |
| --- | --- | --- | --- | --- |
| SLI | Measurement | What service was delivered? | 99.93% valid checkout success | None by definition |
| SLO | Internal objective | What level should be achieved? | At least 99.95% over 28 days | Engineering or product decision |
| SLA | Formal agreement | What was promised under agreed terms? | 99.9% per calendar month | Contractual or formal remedy |

One SLI can support both an SLO and an SLA, but it does not have to. Internal and external calculations may differ in scope, source, or period. Those differences must be explicit and reconciled.

## 6. Event Classes

### Observed Event

Any recorded candidate occurrence. It may later be classified, deduplicated, or rejected.

### Valid Event

An event eligible for the denominator after applying the approved population rules.

### Good Event

A valid event that satisfies every required success condition.

### Bad Event

A valid event that does not satisfy the success conditions. An incorrect `200` response, late result, duplicate charge, or stale record can be bad.

### Excluded Event

An observed event deliberately outside the valid population for a narrow, documented reason. Excluded does not mean good, and excluded volume remains visible.

### Unknown Event

An event whose outcome cannot be determined from trustworthy evidence. Unknown must not silently become good, bad, or excluded.

| Checkout observation | Classification | Reason |
| --- | --- | --- |
| Valid order completes once in 800 ms | Good | Meets every criterion |
| Valid order times out | Bad | Eligible attempt failed |
| Malformed request rejected before checkout | Excluded if policy makes it ineligible | Outside protected population |
| Valid order fails because provider is unavailable | Bad | The consumer experienced failure |
| Duplicate telemetry for one idempotency key | Deduplicate | One logical attempt |
| Result absent because the event stream failed | Unknown | Evidence cannot establish outcome |

## 7. Numerator, Denominator, and Threshold

For a basic availability SLI:

$$
Availability = \frac{G}{G + B}
$$

where $G$ is good events and $B$ is bad events. Excluded and unknown observations require separate reporting and a policy for whether compliance can be determined.

A **threshold** defines good performance for one event. In latency measurement, `500 ms` may separate useful completion from excessive delay. The **target** then defines the required proportion, such as 99 percent of valid events within 500 ms. Threshold and target answer different questions.

## 8. Time Terms

- **Measurement interval:** period used to aggregate observations, such as one minute.
- **Compliance period:** period over which the SLO or SLA is evaluated.
- **Reporting period:** period covered by a published report.
- **Rolling window:** continuously moves with evaluation time, such as the preceding 28 days.
- **Calendar window:** aligns to named calendar boundaries, such as a UTC month.

A dashboard may show five-minute SLI values, calculate a rolling 28-day SLO, and publish a monthly report. An SLA may use a calendar month. Every result needs its period label.

## 9. Error Budget

An **error budget** is the permitted unreliability implied by an SLO.

For target $T$:

$$
Error\ Budget\ Fraction = 1 - T
$$

For a 99.9 percent SLO and 2,000,000 valid events:

$$
Allowed\ Bad\ Events = 2{,}000{,}000 \times (1 - 0.999) = 2{,}000
$$

The budget is not a planned outage allocation, permission to fail users, or the threshold for SLA credits. It expresses the SLO's tolerance. A separate policy controls how consumption affects decisions.

## 10. Attainment and Compliance

**Attainment** is the measured SLI result for a period. **Compliance** states whether the result satisfies the objective or agreement under its rules.

If attainment is 99.92 percent, it complies with a 99.9 percent objective and misses a 99.95 percent objective. If material evidence is unknown, the organization may be unable to declare compliance even when recorded traffic exceeds the target.

## 11. Related Terms That Are Not Synonyms

| Term | Meaning | Why it is not an SLI or SLO |
| --- | --- | --- |
| KPI | Progress toward a business or operational goal | It may measure revenue, adoption, or cost rather than delivered service. |
| KRI | Signal of changing risk exposure | It may aggregate several controls or conditions. |
| RTO | Target restoration time after disruption | It addresses recovery, not continuous performance. |
| RPO | Maximum acceptable data loss relative to a recovery point | It is not availability or durability attainment. |
| OLA | Internal agreement supporting a wider commitment | Its scope and consequence are organization-specific. |
| Support target | Expected support acknowledgement or response | It does not prove service restoration. |
| Alert threshold | Condition that triggers notification | It may predict SLO risk but is not the SLO. |

## 12. Ownership Terms

- **SLI owner:** maintains the definition and faithful implementation.
- **Data owner:** maintains source integrity, lineage, coverage, and access.
- **SLO owner:** remains accountable for the objective, decision use, and lifecycle.
- **Service owner:** remains accountable for the production outcome.
- **SLA authority:** approves formal commitments within commercial and legal governance.

One team may perform several roles, but the responsibilities remain distinct.

## 13. Common Language Failures

| Statement | Problem | Corrective question |
| --- | --- | --- |
| “Our SLA is 99.9%.” | No parties, measure, period, or consequence. | Which agreement and exact calculation? |
| “CPU is our SLI.” | Component activity may not represent delivered service. | Which user outcome does it measure? |
| “The SLO is five minutes.” | It could mean latency, recovery, support, or alerting. | Five minutes for which event and population? |
| “We met uptime.” | Boundary and usability are undefined. | Could users complete the protected action? |
| “Maintenance does not count.” | The exclusion may hide user harm. | Which approved rule excludes it, and why? |
| “No data means no errors.” | Measurement failure is treated as success. | Can compliance be established? |

## Production Scenario: Three Different 99.9 Percentages

A team reports that 99.9 percent of servers were running, 99.9 percent of valid API requests returned a correct result, and the customer contract promises 99.9 percent monthly availability at the edge.

The first value is a component-state measure. The second may be an SLI. The third is a contractual commitment with its own population, source, exclusions, and consequence. A service can satisfy one and fail another. Every result must identify its boundary, definition, period, and authority.

## Practical Output: Service-Level Terminology Reference

```markdown
# Service-Level Terminology Reference

| Term | Approved local definition | Example | Common misuse | Owner |
| --- | --- | --- | --- | --- |
| SLI | | | | |
| SLO | | | | |
| SLA | | | | |
| Valid event | | | | |
| Good event | | | | |
| Bad event | | | | |
| Excluded event | | | | |
| Unknown event | | | | |
| Compliance period | | | | |
| Error budget | | | | |
| RTO/RPO | | | | |
| OLA | | | | |
```

## Exercise

Collect ten reliability statements from dashboards, documents, contracts, or team discussions. Classify every noun and number as a measure, target, period, commitment, consequence, recovery objective, diagnostic signal, or undefined term. Rewrite ambiguous statements so an independent reviewer can calculate and administer them.

## Knowledge Check

1. What additional information turns a metric into an SLI specification?
2. Can one SLI support both an SLO and an SLA?
3. Why is an excluded event not a good event?
4. How does a latency threshold differ from an SLO target?
5. Why might compliance be unknown when the recorded result exceeds the target?
6. Which term limits acceptable data loss during recovery?

## Key Takeaways

- An SLI measures, an SLO sets an internal objective, and an SLA creates an agreement with consequences.
- Good and bad events are subsets of the valid population.
- Excluded and unknown events require visible treatment.
- Thresholds, targets, and windows answer different questions.
- Recovery, business, risk, support, and alerting measures are related to service levels but cannot replace them.

## Further Reading

- [Google SRE, Service Level Objectives](https://sre.google/sre-book/service-level-objectives/)
- [Google SRE Workbook, Implementing SLOs](https://sre.google/workbook/implementing-slos/)

## Navigation

- Previous: [Service Level Engineering](01-Service-Level-Engineering.md)
- Next: [From Critical User Journeys to Service Levels](03-From-Critical-User-Journeys-to-Service-Levels.md)
- Collection: [SLIs, SLOs, and SLAs](README.md)

---

Part of **SRE World**, maintained by **VERIQTA**.
