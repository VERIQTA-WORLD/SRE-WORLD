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

