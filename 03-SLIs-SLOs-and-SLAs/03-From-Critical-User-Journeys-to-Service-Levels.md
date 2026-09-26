# From Critical User Journeys to Service Levels

> Translate important user outcomes into a small set of reliability dimensions that can be measured and governed.

## Section Purpose

Translate important user outcomes into a small set of reliability dimensions that can be measured and governed.

The definition and discovery of Critical User Journeys belong to SRE Foundations. This section begins with an approved journey and derives service-level requirements.

The practical output is a **Critical User Journey to service-level map**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain the role of begin with the outcome in a service-level system.
2. Explain the role of identify the user in a service-level system.
3. Explain the role of define success and failure in a service-level system.
4. Explain the role of derive dimensions in a service-level system.
5. Explain the role of prioritize critical journeys in a service-level system.
6. Explain the role of separate reliability from product analytics in a service-level system.
7. Explain the role of map harm to evidence in a service-level system.
8. Explain the role of avoid endpoint-first design in a service-level system.

---

## Begin with the outcome

A journey should state what a defined user must accomplish. “POST /orders returns 200” is an interface event. “A customer submits an eligible order and receives durable confirmation exactly once” is an outcome.

---

## Identify the user

Users may be customers, employees, operators, API clients, scheduled workloads, or downstream services. Different users may have different expectations, harm, traffic, and measurement points.

---

## Define success and failure

Success includes the required result, not merely technical completion. Failure can include rejection, delay, duplication, stale data, corruption, incomplete output, or an unrecoverable intermediate state.

---

## Derive dimensions

Ask whether the journey must be available, timely, correct, fresh, durable, complete, or usable under degradation. Select only dimensions that materially affect the outcome.

---

## Prioritize critical journeys

Popularity is not the only criterion. A low-volume emergency recovery path, payroll run, or regulatory submission can deserve stronger protection than a high-volume cosmetic action.

---

## Separate reliability from product analytics

Conversion, engagement, and revenue can explain importance, but they do not directly prove service reliability. A user may abandon a journey for reasons unrelated to system failure.

---

## Map harm to evidence

For each failure, state who is harmed, how quickly harm appears, whether it is reversible, and which observation could detect it. This creates candidate SLIs without prematurely choosing telemetry.

---

## Avoid endpoint-first design

Endpoint metrics often miss client failure, multi-step journeys, semantic correctness, and dependency behavior. Start with the journey, then identify which technical events can represent it.

---

## Record assumptions

Journey definitions often contain uncertainty about user segments, retries, completion, and delayed outcomes. Record these assumptions and assign validation rather than hiding them in a denominator.


---

## Detailed Method: Translating a Journey into Service Levels

The translation should move from meaning to evidence. Starting with an endpoint or an available metric reverses the process and usually creates a technically convenient indicator that does not protect the complete outcome.

### Step 1: State the Consumer and Intent

Name the consumer precisely. “User” may mean a customer, internal analyst, scheduled workload, mobile client, downstream API, or emergency operator. Different consumers can use the same service with different reliability needs.

Then state the intent as an outcome, not an interface action.

Weak statement:

> The customer clicks Pay.

Stronger statement:

> An eligible customer submits an order and receives durable confirmation that the correct order was accepted exactly once.

The stronger statement survives interface changes and reveals correctness, latency, durability, and duplicate-processing requirements.

### Step 2: Establish Preconditions

Preconditions determine which attempts can reasonably enter the measurement population. Examples include:

- the account is authorized to perform the operation;
- the request satisfies the published contract;
- the requested item is eligible for purchase;
- the service is offered in the consumer's location;
- the attempt reaches the defined entry boundary.

Preconditions should not be written to remove inconvenient failures. If the service incorrectly reports an eligible customer as ineligible, that is normally a service failure, not a reason to remove the event.

### Step 3: Define a Successful Terminal State

A journey needs a stable end condition. For a synchronous request, the end may be a validated response. For asynchronous work, the end may occur minutes or hours later when the promised effect becomes visible.

Ask:

- What state must exist when the journey succeeds?
- Must the result be persisted?
- Must the consumer receive confirmation?
- Must the operation happen exactly once?
- Can a degraded result still be useful?
- What deadline makes the result valuable?

A terminal state prevents a local acknowledgement from being mistaken for end-to-end completion.

### Step 4: Enumerate User-Visible Failure Classes

Do not begin with status codes. Begin with ways the consumer can fail to obtain the outcome:

| Failure class | Example | Likely dimension |
| --- | --- | --- |
| Rejection | Valid payment is refused | Availability |
| Delay | Result arrives after the decision deadline | Latency or timeliness |
| Incorrect result | Wrong price or balance is returned | Correctness |
| Duplicate effect | Customer is charged twice | Correctness |
| Lost state | Confirmed record cannot later be retrieved | Durability |
| Stale state | Old inventory is presented as current | Freshness |
| Reduced usefulness | Video connects without intelligible audio | Quality |
| Ambiguous outcome | Customer cannot tell whether an order succeeded | Availability and correctness |

This inventory is the bridge between a CUJ and candidate SLIs.

### Step 5: Separate Dimensions That Need Different Decisions

One composite objective may conceal severe harm. Suppose checkout is 99.99 percent reachable but 0.3 percent of orders use the wrong currency conversion. Averaging availability and correctness produces a number with no clear meaning.

Use separate SLIs when:

- the dimensions have different failure modes;
- different teams or controls influence them;
- one dimension can pass while another causes serious harm;
- different decisions follow from each result;
- combining them would allow high performance in one dimension to compensate for unacceptable performance in another.

Combine conditions within a single good event only when the user outcome genuinely requires all of them and the resulting event can be measured reliably.

### Step 6: Choose Observable Proxies

The ideal user outcome may not be directly observable. A proxy is acceptable when its relationship to the outcome is understood and tested.

For example, server response success may proxy client success. It misses failures before the request reaches the server and failures after the response leaves it. The design record should state that limitation and identify corroborating client or edge evidence.

Evaluate every proxy against four questions:

1. Which real failures does it detect?
2. Which real failures does it miss?
3. Can it report failure when users actually succeed?
4. What change could weaken its relationship to the outcome?

### Step 7: Map the Outcome to Decisions

An indicator deserves SLO status when it supports a production decision. Possible decisions include:

- prioritize a correctness defect over feature work;
- change a release plan;
- revise architecture or dependency protections;
- change a product fallback;
- renegotiate an unsupported commitment;
- invest in better measurement;
- accept a documented level of residual risk.

If no decision changes, keep the measure as diagnostic telemetry until its purpose is clear.

## Worked Example: Password Recovery

### Journey

An authorized account holder requests recovery, receives a usable recovery challenge through an approved channel, proves control, sets a new password, and can authenticate without exposing the account to takeover.

### Candidate Dimensions

| Dimension | Good-event interpretation |
| --- | --- |
| Availability | Eligible recovery attempts reach a valid terminal state. |
| Latency | Challenge delivery and completion occur within useful thresholds. |
| Correctness | The intended account is recovered and unauthorized attempts are rejected. |
| Security quality | Recovery does not bypass required controls. |
| Freshness | Old or replaced recovery tokens become unusable promptly. |

Security failures must not be averaged away by successful legitimate attempts. A recovery system can be highly available and dangerously incorrect.

### Candidate Measures

- proportion of eligible recovery attempts completed within 10 minutes;
- proportion of issued challenges delivered within 60 seconds;
- proportion of completed recoveries followed by successful authentication;
- number and rate of confirmed unauthorized recoveries, reported as a separate intolerable event class.

### Boundary Limitation

Server logs cannot prove that an email or SMS reached the account holder. Delivery-provider evidence or controlled end-to-end testing may be required. The map must expose this gap.

## Journey Changes and Versioning

CUJs evolve. A new payment method, mobile client, regional requirement, or asynchronous step can alter the meaning of success. Review the mapping when:

- a journey adds or removes a step;
- the consumer population changes;
- a synchronous operation becomes asynchronous;
- a fallback or degraded mode is introduced;
- a dependency becomes critical;
- a new contractual segment appears;
- incident evidence reveals an unmeasured failure class.

Do not silently change an SLI to follow the new journey. Version the map, assess comparability, and set an effective date.

## Production Scenario

All checkout endpoints meet local success targets, but successful payment events are rejected before order creation. A journey-based service level must measure durable order confirmation, not isolated HTTP success.

### Analysis Questions

1. Which user outcome is at risk?
2. What is the correct measurement population and boundary?
3. Which evidence is authoritative?
4. Which assumption could make the result misleading?
5. Who owns the indicator and decision?
6. What immediate correction is required?
7. How will the corrected design be verified?

---

## Practical Output: Critical User Journey to service-level map

Create a record containing:

- Journey:
- User:
- Start and end:
- Success criteria:
- Failure modes:
- Reliability dimensions:
- User harm:
- Candidate observations:
- Owner:
- Unknowns:

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

- Translate important user outcomes into a small set of reliability dimensions that can be measured and governed.
- A percentage without a precise population, calculation, window, and owner is not a trustworthy service level.
- User-visible outcomes take priority over convenient infrastructure signals.
- Unknown and excluded events require explicit treatment.
- Every service-level artifact needs validation and lifecycle control.

---

## Navigation

[Previous: SLI, SLO, and SLA Terminology](./02-SLI-SLO-and-SLA-Terminology.md)

[Next: Service Boundaries and Measurement Boundaries](./04-Service-Boundaries-and-Measurement-Boundaries.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)
