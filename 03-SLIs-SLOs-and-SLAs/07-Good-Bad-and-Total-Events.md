# Good, Bad, and Total Events

> Classify eligible observations consistently and calculate event-based service levels without double counting or hiding unknown outcomes.

## Section Purpose

Classify eligible observations consistently and calculate event-based service levels without double counting or hiding unknown outcomes.

Eligibility comes from Section 6. This section determines how valid observations contribute to the numerator and failure population.

The practical output is a **Event-classification specification with test cases**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain the role of core ratio in a service-level system.
2. Explain the role of unknown outcomes in a service-level system.
3. Explain the role of multi-condition success in a service-level system.
4. Explain the role of partial success in a service-level system.
5. Explain the role of deduplication in a service-level system.
6. Explain the role of late classification in a service-level system.
7. Explain the role of mutual exclusivity in a service-level system.
8. Explain the role of reconciliation in a service-level system.

---

## Core ratio

For a good-event SLI, the common calculation is good valid events divided by total valid events. The bad-event ratio is bad valid events divided by total valid events. If every valid event is classifiable, the two ratios sum to one.

---

## Unknown outcomes

Unknown is not automatically good or bad. Publish the unknown rate and define a confidence threshold. If unknown volume is material, the SLI may be unavailable for decision-making.

---

## Multi-condition success

A payment may need authorization, correct amount, exactly-once recording, and completion within a latency threshold. The event is good only when every required condition holds.

---

## Partial success

A response containing some results may be useful or harmful depending on the product promise. Define minimum quality, required fields, or degraded categories instead of forcing all partial outcomes into one bucket.

---

## Deduplication

Choose whether the unit is a request, logical attempt, transaction, user session, or journey. A retry chain should not accidentally count one harmed user as ten independent failures unless request-level behavior is the objective.

---

## Late classification

Correctness or completion may become known after the initial event. Use stable identifiers, allowed lateness, and correction rules so historical results can be reconciled.

---

## Mutual exclusivity

Good, bad, excluded, and unknown classifications should not overlap. Test classification order when one event satisfies several failure rules.

---

## Reconciliation

Verify that total valid equals good plus bad plus unknown when that is the model. Sudden gaps or over-counts indicate query, join, or schema failure.

---

## Worked example

If 1,000 valid checkout attempts include 970 good, 20 bad, and 10 unknown, the reported good-event ratio is 97 percent only if the policy accepts unknown outside the numerator. The 1 percent unknown rate must remain visible.


---

## Event Algebra

After eligibility, every valid event must be classified by the SLI's success rule.

Let:

- $G$ be good valid events;
- $B$ be bad valid events;
- $V$ be all valid events.

Then:

$$
V = G + B
$$

and:

$$
SLI = \frac{G}{V} = \frac{G}{G+B}
$$

The bad-event rate is:

$$
Bad\ Rate = \frac{B}{V} = 1 - SLI
$$

These identities create powerful controls. If good plus bad does not equal valid, the pipeline has an unclassified, duplicated, or inconsistent population.

## Good Means Every Required Condition

When success requires several conditions, a good event satisfies all of them.

For checkout:

$$
Good = Available \land Correct \land ExactlyOnce \land WithinThreshold
$$

If 99.99 percent of attempts are reachable, 99.9 percent are correct, and 99.8 percent are timely, the complete success ratio cannot be inferred by averaging those percentages. The conditions may affect the same or different events. Measure the joint outcome directly when possible.

## Separate SLIs Versus Compound Success

Use a compound good-event rule when the outcome has one inseparable definition, such as “exactly one correct order within two seconds.” Use separate SLIs when dimensions need independent interpretation and decisions.

For example:

- availability SLI: did the attempt reach a valid terminal state?
- latency SLI: did a valid attempt complete within two seconds?
- correctness SLI: did the completed result match authoritative truth?

Separate measures expose which property failed. A compound outcome can still be retained as an end-to-end SLI if it has a clear decision purpose.

## Partial Success

Partial results need an explicit model. Three common approaches exist.

### Binary Classification

Any valid event below the required level is bad. Use this when partial delivery is not useful or is unsafe.

### Multiple Threshold SLIs

Define separate quality levels, for example:

- 99.9 percent of calls connect with usable audio;
- 99 percent connect with usable audio and video.

This is easier to interpret than a hidden weighted score.

### Weighted Quality Score

Assign documented weights when different levels have meaningful ordered value. For example, full service may score 1, approved degraded service 0.5, and unusable service 0.

Weighted SLIs require caution. A large amount of degraded service can appear acceptable, and the result may be difficult to connect to a user decision. Always publish the underlying event distribution.

## Unknown Outcomes

Unknown is an evidence state, not a service-quality state. Do not place unknown events into $G$ merely because no failure was recorded.

Report:

- good count;
- bad count;
- unknown count;
- excluded count;
- coverage ratio;
- best and worst possible result when unknowns could be valid.

Measurement coverage can be expressed as:

$$
Coverage = \frac{G+B}{G+B+U}
$$

A high SLI with low coverage is not strong reliability evidence.

## Late Classification and Mutable Truth

Correctness and durability may be known only after reconciliation. An event can move from provisionally good to bad when authoritative truth arrives.

The specification should define:

- provisional state;
- validation delay;
- finalization cutoff;
- report restatement rules;
- audit history;
- SLA dispute implications.

Never overwrite historical values without recording which data and specification version produced the revised result.

## Deduplication

Deduplication must happen at the logical-event level before classification. A reliable method defines:

- unique key;
- deduplication time horizon;
- canonical record selection;
- conflicting-record handling;
- late duplicate treatment.

If duplicates represent a harmful service effect, such as duplicate charges, do not merely discard them. Deduplicate telemetry while classifying the logical outcome as bad.

## Worked Calculation

A message-processing service observes the following logical events during a window:

- 2,500,000 valid events;
- 2,487,000 completed correctly before the deadline;
- 8,000 completed after the deadline;
- 3,000 produced an incorrect result;
- 2,000 never reached a terminal state;
- 5,000 additional observations are excluded test traffic;
- 1,000 candidate events are unknown because the sink audit is missing.

Good events:

$$
G = 2{,}487{,}000
$$

Bad events:

$$
B = 8{,}000 + 3{,}000 + 2{,}000 = 13{,}000
$$

SLI:

$$
\frac{2{,}487{,}000}{2{,}500{,}000} = 99.48\%
$$

The 5,000 test events do not enter the ratio. The 1,000 unknown events remain separate. If they might be valid, the worst-case result is:

$$
\frac{2{,}487{,}000}{2{,}501{,}000} \approx 99.44\%
$$

## Classification Test Design

Test cases should include:

- exact threshold boundaries;
- null and malformed fields;
- retries and duplicates;
- dependency failures;
- partial completion;
- late completion;
- conflicting truth sources;
- missing terminal events;
- clock skew;
- events crossing a reporting boundary.

Two independent reviewers should reach the same classification from the specification. Disagreement reveals ambiguity that must be resolved before implementation.

## Production Scenario

A payment retry produces one timeout, one successful authorization, and two duplicate callbacks. The team must decide whether the unit is an API request, payment attempt, or exactly-once completed transaction.

### Analysis Questions

1. Which user outcome is at risk?
2. What is the correct measurement population and boundary?
3. Which evidence is authoritative?
4. Which assumption could make the result misleading?
5. Who owns the indicator and decision?
6. What immediate correction is required?
7. How will the corrected design be verified?

---

## Practical Output: Event-classification specification with test cases

Create a record containing:

- Event identifier:
- Eligibility result:
- Good criteria:
- Bad criteria:
- Unknown criteria:
- Deduplication key:
- Classification order:
- Late update rule:
- Expected class:
- Verification evidence:

Unknown information must remain visible with an investigation owner and due date. Do not use “not applicable” to hide missing evidence.

---

## Review Checklist

- [ ] The protected user outcome is explicit.
- [ ] The evaluated population is defined.
- [ ] The measurement boundary is defensible.
- [ ] Good, bad, excluded, and unknown behavior cannot be confused.
- [ ] The calculation can be reproduced from authoritative evidence.
- [ ] Segments with materially different harm remain visible.
- [ ] Limitations and uncertainty are documented.
- [ ] Ownership, approval, version, and review triggers are recorded.
- [ ] The result supports a named production decision.

---

## Key Takeaways

- Classify eligible observations consistently and calculate event-based service levels without double counting or hiding unknown outcomes.
- A percentage without a precise population, calculation, window, and owner is not a trustworthy service level.
- User-visible outcomes take priority over convenient infrastructure signals.
- Unknown and excluded events require explicit treatment.
- Every service-level artifact needs validation and lifecycle control.

---

## Navigation

[Previous: Valid Events and Eligibility Rules](./06-Valid-Events-and-Eligibility-Rules.md)

[Next: Availability SLIs](./08-Availability-SLIs.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)
