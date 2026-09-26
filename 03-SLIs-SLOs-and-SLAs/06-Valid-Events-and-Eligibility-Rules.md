# Valid Events and Eligibility Rules

> Define which observations belong in the evaluated population without hiding genuine user harm or allowing denominator manipulation.

## Section Purpose

Define which observations belong in the evaluated population without hiding genuine user harm or allowing denominator manipulation.

This section controls eligibility. It does not decide whether an eligible event is good, which belongs in Section 7.

The practical output is a **Valid-event and exclusion policy**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain the role of eligibility before quality in a service-level system.
2. Explain the role of malformed and unauthorized requests in a service-level system.
3. Explain the role of client cancellation in a service-level system.
4. Explain the role of retries and duplicates in a service-level system.
5. Explain the role of synthetic and health traffic in a service-level system.
6. Explain the role of administrative and internal traffic in a service-level system.
7. Explain the role of abuse and attack traffic in a service-level system.
8. Explain the role of maintenance in a service-level system.

---

## Eligibility before quality

First decide whether an observation belongs in scope. Only then classify it as good or bad. Mixing the decisions creates exclusions that silently improve the result.

---

## Malformed and unauthorized requests

Some traffic is clearly outside the service contract. Other failures result from confusing product behavior or service defects. Exclusion requires a documented boundary, not a convenient status code.

---

## Client cancellation

A cancellation before the service begins work may be excluded. A cancellation caused by excessive latency represents user harm. The data must distinguish the cases.

---

## Retries and duplicates

Counting every retry can exaggerate both volume and failure. Deduplication may better represent a user attempt, while request-level reliability may intentionally count each server interaction. Choose explicitly.

---

## Synthetic and health traffic

Synthetic probes can validate reachability but should not silently dominate a user-traffic SLI. Separate synthetic and real-user populations unless the objective explicitly combines them.

---

## Administrative and internal traffic

Back-office, operator, migration, and maintenance operations may have different reliability expectations. Exclude them only if another indicator protects their required outcome.

---

## Abuse and attack traffic

Filtering malicious or abusive traffic may be justified, but the detection method can misclassify valid users. Record the control owner, uncertainty, and impact.

---

## Maintenance

Planned work is still experienced by users. An SLA may exclude approved maintenance, while an internal SLO may count it to preserve the engineering cost of downtime.

---

## Missing fields

An event that cannot be classified should become unknown, not automatically good. Track unknown volume and define when measurement confidence is lost.

---

## Anti-gaming controls

Review denominator changes, exclusion growth, filter ownership, and segment removal. Recalculate from raw data when possible and require approval for material rule changes.


---

## Building the Denominator

The denominator determines which opportunities for service enter the SLI. A team can produce an impressive result simply by removing difficult traffic. For that reason, denominator design needs the same engineering scrutiny as the success condition.

Start with the intended population, then express each eligibility rule as a testable predicate.

For an API:

$$
Valid(r) = InScopeConsumer(r) \land SupportedOperation(r) \land MeetsContract(r) \land EntersBoundary(r)
$$

This formula does not say that every rejected request is excluded. If the service misclassifies a valid request as unauthorized or malformed, the request may still be a bad event. Eligibility must be based on authoritative facts, not merely the service's response.

## Eligibility Decision Order

Classify in a stable order:

1. identify the logical event;
2. remove duplicate observations without removing the logical attempt;
3. determine whether the event belongs to the defined consumer and operation population;
4. apply narrow approved exclusions;
5. identify whether sufficient evidence exists;
6. classify valid events as good or bad.

If the team checks status codes before eligibility, a service defect can influence its own denominator.

## Invalid Requests

Malformed input is often excluded because the service cannot fulfill a request outside the published contract. That rule needs safeguards:

- the contract must be versioned and discoverable;
- validation must be correct;
- rejected requests should be sampled and audited;
- sudden growth in invalid classifications should trigger review;
- client and server contract versions must be reconciled.

If a deployment incorrectly rejects valid requests as malformed, those attempts are bad. Using the server's rejection label as the source of truth would hide the incident.

## Authentication and Authorization

Truly unauthorized attempts can be outside a functional-service SLI. Authentication-system failure is different. If an eligible user presents valid credentials and the identity dependency fails, the protected journey has failed.

Separate:

- invalid credentials, normally ineligible for successful authentication;
- expired credentials, treatment depends on the published behavior;
- valid credentials rejected by service failure, bad;
- attempts whose validity cannot be established because the identity source is unavailable, bad or unknown according to the approved model, never automatically excluded.

## Retries and Logical Events

Counting every transport request can reward or punish retry behavior rather than service outcomes.

Suppose one user action generates three requests:

- first request times out after the server commits the operation;
- second retry receives an ambiguous error;
- third retry returns the existing successful result.

Request-level measurement sees one success and two failures. User-intention measurement may see one successful but slow or ambiguous journey. Neither view is universally correct. The specification must state whether it protects individual request handling or logical user outcomes.

Use an idempotency key, job ID, event ID, or stable journey identifier. Document its lifetime and collision behavior.

## Client Cancellations

A cancellation can mean:

- the user deliberately abandoned the action;
- the client timeout was shorter than the service's useful-time threshold;
- the application closed because of a crash;
- an intermediate proxy cancelled the request;
- the user retried through a different path.

Do not exclude all client cancellations. Analyze timing and cause. If the service was too slow and the user gave up, exclusion would conceal latency failure.

## Planned Maintenance

Maintenance can be excluded from an SLA under explicit terms. It should not disappear automatically from an internal user-centered SLI. Users may still lose access, and product or engineering decisions need that evidence.

If an exclusion is permitted, record:

- authorized maintenance ID;
- start and end time;
- affected service and population;
- notice requirement;
- maximum duration;
- approval authority;
- actual excluded event count;
- whether users had a supported alternative.

An open-ended “maintenance” label is not a valid rule.

## Abuse, Attack, and Overload

Attack traffic can distort both capacity and availability. Eligibility depends on the service promise.

- Clearly identified traffic outside the accepted-use policy may be excluded.
- Legitimate users harmed by an attack remain part of the protected population.
- Rate-limited requests may be good only if rate limiting is documented and the consumer stayed outside the promised quota.
- Incorrect attack classification that blocks legitimate users is a service failure.

Report excluded attack volume separately because it explains operating conditions and can reveal classification risk.

## Synthetic, Administrative, and Internal Traffic

Synthetic probes are useful evidence but normally form their own population. Combining them with real traffic changes weighting and can inflate success when probes are simpler than actual journeys.

Administrative traffic may require its own SLI when it protects an important operator journey, such as emergency access or disaster recovery. Do not mix it casually with customer requests.

## Unknown Eligibility

Sometimes the team cannot determine whether an observed event was eligible because a field, join, or upstream record is missing. Classify it as unknown until resolved.

Define an uncertainty bound. If $U$ events are unknown, the best and worst possible SLI values are:

$$
SLI_{best} = \frac{G + U}{G + B + U}
$$

$$
SLI_{worst} = \frac{G}{G + B + U}
$$

If the SLO target lies between these bounds, compliance cannot be established without more evidence.

## Exclusion Governance

Every exclusion needs:

- stable reason code;
- precise predicate;
- user-impact statement;
- approving role;
- implementation test;
- separate volume trend;
- review or expiry condition.

Review exclusion ratios during incidents and near SLO boundaries. A rising exclusion rate can make the reported SLI improve while real service worsens.

## Worked Example

During one hour, checkout records show:

- 100,000 observed request records;
- 2,000 duplicate retry records representing 800 logical attempts;
- 3,000 genuinely malformed requests;
- 500 unauthorized attempts;
- 200 outcomes missing because a reconciliation feed failed;
- 95,000 classified logical eligible attempts after deduplication;
- 94,620 good and 380 bad eligible attempts.

The SLI is:

$$
\frac{94{,}620}{95{,}000} = 99.6\%
$$

The 200 unknown outcomes must be reported separately. If they may belong to the eligible population, compute uncertainty bounds before declaring compliance.

## Production Scenario

A team excludes every 4xx response. The service recently began returning 429 to valid customers because of an internal capacity problem. The exclusion converts a reliability failure into invisible traffic.

### Analysis Questions

1. Which user outcome is at risk?
2. What is the correct measurement population and boundary?
3. Which evidence is authoritative?
4. Which assumption could make the result misleading?
5. Who owns the indicator and decision?
6. What immediate correction is required?
7. How will the corrected design be verified?

---

## Practical Output: Valid-event and exclusion policy

Create a record containing:

- Observation type:
- Included population:
- Excluded population:
- Reason:
- Detection rule:
- Risk of misclassification:
- Unknown handling:
- Approval authority:
- Test cases:
- Version and review:

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

- Define which observations belong in the evaluated population without hiding genuine user harm or allowing denominator manipulation.
- A percentage without a precise population, calculation, window, and owner is not a trustworthy service level.
- User-visible outcomes take priority over convenient infrastructure signals.
- Unknown and excluded events require explicit treatment.
- Every service-level artifact needs validation and lifecycle control.

---

## Navigation

[Previous: Anatomy of an SLI Specification](./05-Anatomy-of-an-SLI-Specification.md)

[Next: Good, Bad, and Total Events](./07-Good-Bad-and-Total-Events.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)
