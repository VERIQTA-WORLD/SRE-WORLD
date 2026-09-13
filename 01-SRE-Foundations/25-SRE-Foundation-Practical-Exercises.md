# SRE Foundation Practical Exercises

> SRE knowledge becomes useful when an engineer can define a service, identify its users, express reliability as measurable behavior, reason about risk, operate through failure, reduce recurring work, assign ownership, and verify that improvement produced the intended outcome.

## Section Purpose

This section converts the concepts in Chapter 1 into practical work.

The exercises are designed for:

- Individual study
- SRE team training
- Engineering workshops
- Production-readiness preparation
- Reliability reviews
- Interview and onboarding practice
- Service-team and SRE collaboration

The exercises do not require a specific cloud provider, orchestration platform, monitoring product, or programming language. You may apply them to a real service, a safe test service, or the fictional service introduced in this section.

Every exercise includes:

- Objective
- Scenario or input
- Tasks
- Required deliverable
- Validation criteria
- Common mistakes
- Reflection questions

The work is progressive. Early exercises define the service and its users. Later exercises build SLIs, SLOs, risk decisions, incident practices, recovery plans, toil analysis, operating models, and success measurements. The final capstone combines the complete foundation.

Do not perform disruptive tests against production without explicit authorization, safeguards, rollback, monitoring, and a defined stop condition.

---

## Learning Objectives

After completing this section, you should be able to:

1. Create a service definition and ownership record.
2. Discover and prioritize Critical User Journeys.
3. Distinguish reliability, availability, resilience, and durability requirements.
4. Build meaningful SLIs and SLOs.
5. Calculate error budgets and interpret burn rate.
6. Construct reliability risk and failure models.
7. Design incident, recovery, and production-readiness artifacts.
8. Identify and measure toil.
9. Evaluate SRE need, readiness, and operating models.
10. Build a balanced SRE success scorecard.
11. Communicate reliability decisions to technical and business audiences.
12. Complete an end-to-end SRE foundation assessment.

---

## 1. How to Complete the Workbook

Use one of three modes.

### Real Service Mode

Apply the exercises to a service you own or understand. Remove secrets, personal information, credentials, and sensitive architecture from public submissions.

### Lab Service Mode

Use a safe service created for learning. It can be simple, but it must have users, dependencies, data, change, and failure modes.

### Fictional Service Mode

Use the SRE World Shop described below.

Complete exercises in order where possible. Later work reuses earlier artifacts.

---

## 2. Fictional Service: SRE World Shop

SRE World Shop is an online retail service with these capabilities:

- Browse products
- Search inventory
- Create an account
- Sign in
- Add products to a cart
- Pay
- Create an order
- Track delivery
- Cancel eligible orders
- Recover an account

Its major internal services are:

- Web and mobile clients
- Identity service
- Product catalog
- Search service
- Cart service
- Inventory service
- Payment service
- Order service
- Notification service
- Delivery integration
- Customer support portal

It uses an external payment provider and delivery partner. Orders and payment records are stored in separate data systems.

---

## 3. Fictional Service Constraints

Assume:

- Customers operate in three regions.
- Traffic increases five times during campaigns.
- Payment must occur exactly once.
- Confirmed orders must not disappear.
- Some product browsing can degrade safely.
- Account recovery is low volume but security critical.
- Customer support operates continuously.
- The engineering organization has twelve product teams.
- One central SRE team has eight engineers.

You may add assumptions, but record them explicitly.

---

## 4. Evidence Classification Template

Use this table during every exercise.

| Category | Meaning | Entry |
| --- | --- | --- |
| Fact | Supported by available evidence | |
| Hypothesis | Testable explanation | |
| Assumption | Unverified condition treated as true | |
| Decision | Chosen action and authority | |
| Unknown | Important missing information | |

Do not present assumptions as facts.

---

## 5. Exercise 1: Define SRE Without Tools

### Objective

Create a working definition of SRE that explains its purpose and boundaries.

### Tasks

1. Write a definition in no more than three sentences.
2. Do not mention any vendor, tool, cloud, or orchestrator.
3. Include service, users, reliability objectives, risk, engineering, and sustainable effort.
4. List five activities that may support SRE but do not define it.
5. List three responsibilities that SRE should not automatically own.

### Required Deliverable

A one-page SRE definition and boundary statement.

### Validation Criteria

- Begins with service outcomes
- Includes explicit reliability
- Includes engineering methods
- Includes acceptable risk
- Includes sustainable operations
- Avoids a tool list

### Common Mistakes

- Defining SRE as monitoring
- Calling SRE a DevOps replacement
- Treating on-call as the entire role
- Claiming SRE owns everything in production

### Reflection Questions

1. Which word in your definition carries the most responsibility?
2. Could the definition remain valid after the current tools change?

---

## 6. Exercise 2: Create a Service Definition

### Objective

Define the object whose reliability will be managed.

### Tasks

Document:

- Service name
- Purpose
- Users and dependent systems
- Start and end boundary
- Major capabilities
- Owners
- Dependencies
- Data
- Change mechanisms
- Support commitment
- Lifecycle state

Draw a high-level service boundary with no more than eight components.

### Required Deliverable

A service definition record and boundary diagram.

### Validation Criteria

- Describes an outcome, not only a repository or cluster
- Identifies users
- Separates internal components from external dependencies
- Names an accountable team
- States important unknowns

### Common Mistakes

- Defining the service as all production
- Listing technology without purpose
- Omitting dependent systems as users
- Assigning several equally accountable owners

### Reflection Questions

1. Could a new responder identify the service from this record?
2. Which boundary decision is uncertain?

---

## 7. Exercise 3: Identify Service Users

### Objective

Identify every meaningful human and system user without treating all users as identical.

### Tasks

Create user groups such as:

- Customer
- Employee
- Administrator
- Support engineer
- Partner
- API client
- Scheduled workload
- Downstream service

For each group, document its goal, usage period, failure consequence, and alternative path.

### Required Deliverable

A user inventory with at least five user groups.

### Validation Criteria

- Includes nonhuman users
- Distinguishes goals
- Records time sensitivity
- Identifies vulnerable or high-impact groups
- Avoids personal information

### Common Mistakes

- Calling every user customer
- Ignoring operators and recovery users
- Prioritizing only by traffic volume

### Reflection Questions

1. Which low-volume user has high criticality?
2. Which user lacks an alternative during failure?

---

## 8. Exercise 4: Discover Critical User Journeys

### Objective

Identify the user outcomes that deserve explicit reliability protection.

### Tasks

1. List at least ten user journeys.
2. Define each journey's user, intent, start, end, and success.
3. Score consequence across user harm, revenue, data, security, safety, legal obligation, and downstream impact.
4. Select three Critical User Journeys.
5. Explain why the remaining journeys are not currently critical.

### Required Deliverable

A prioritized CUJ inventory.

### Validation Criteria

- Journeys describe outcomes, not screens
- Criticality uses consequence evidence
- Low-volume critical journeys remain visible
- Each selected journey has an owner

### Common Mistakes

- Selecting every journey
- Using popularity as the only criterion
- Confusing endpoint, component, and journey

### Reflection Questions

1. Which journey would cause the greatest irreversible harm?
2. Which journey is most difficult to measure?

---

## 9. Exercise 5: Map a Critical User Journey

### Objective

Map the technical and organizational path behind one user outcome.

### Tasks

For one CUJ, document:

- Preconditions
- Trigger
- Required steps
- Allowed branches
- Dependencies
- Data changes
- Ownership at each step
- Failure modes
- Degraded alternatives
- Completion evidence

### Required Deliverable

A journey map and dependency table.

### Validation Criteria

- Shows end-to-end behavior
- Includes external and human dependencies
- Distinguishes required and optional steps
- Identifies ownership gaps
- States how success is verified

### Common Mistakes

- Mapping only the interface
- Omitting asynchronous work
- Treating HTTP success as business completion

### Reflection Questions

1. Which step creates the largest blast radius?
2. Which dependency is least observable?

---

## 10. Exercise 6: Separate Reliability Properties

### Objective

Distinguish reliability, availability, resilience, and durability requirements.

### Tasks

For one service, answer:

| Property | Requirement | Failure example | Evidence |
| --- | --- | --- | --- |
| Reliability | | | |
| Availability | | | |
| Resilience | | | |
| Durability | | | |

Add correctness, freshness, latency, and consistency where relevant.

### Required Deliverable

A reliability-properties assessment.

### Validation Criteria

- Properties are not used as synonyms
- Requirements describe user outcomes
- Data preservation includes retrievability and correctness
- Resilience includes recovery and adaptation

### Common Mistakes

- Calling a running process reliable
- Treating replicas as durability proof
- Treating redundancy as resilience proof

### Reflection Questions

1. Can the service be available but unreliable?
2. Which property has the weakest evidence?

---

## 11. Exercise 7: Define Success and Failure Events

### Objective

Create precise events for reliability measurement.

### Tasks

For a selected CUJ, define:

- Eligible event
- Good event
- Bad event
- Unknown event
- Exclusions
- Quality threshold
- Time threshold
- Measurement point

Test the definitions against five edge cases.

### Required Deliverable

An event-classification specification.

### Validation Criteria

- Good means useful completion
- Denominator does not hide failure
- Unknown events have an explicit policy
- Exclusions reflect the service promise
- Edge cases are resolved consistently

### Common Mistakes

- Using status code alone
- Excluding dependency failures
- Counting only requests that reached the backend

### Reflection Questions

1. Which exclusion could be abused?
2. What happens when telemetry is missing?

---

## 12. Exercise 8: Design an SLI

### Objective

Turn a user-centered specification into a measurable indicator.

### Tasks

1. Write the SLI specification.
2. Identify at least two possible implementations.
3. Compare accuracy, coverage, cost, freshness, and failure modes.
4. Select one implementation.
5. Define validation against an independent source.

### Required Deliverable

An SLI specification and implementation record.

### Validation Criteria

- Measures a relevant service behavior
- Defines numerator and denominator
- Identifies measurement limitations
- Includes segmentation
- Has a named owner

### Common Mistakes

- Calling every metric an SLI
- Selecting the cheapest data without assessing coverage
- Ignoring client-side failure

### Reflection Questions

1. Which user failure does the SLI miss?
2. How reliable must the measurement pipeline be?

---

## 13. Exercise 9: Propose an SLO

### Objective

Define a reliability target that supports decisions.

### Tasks

Write an SLO containing:

- SLI
- Population
- Target
- Window
- Owner
- Rationale
- Current baseline
- External commitments
- Review date

Provide three target options with cost and risk implications.

### Required Deliverable

An SLO proposal and decision record.

### Validation Criteria

- Target is below 100 percent unless exceptional evidence justifies otherwise
- User and business rationale is explicit
- Baseline does not automatically become the target
- Decision authority is named
- Refinement process exists

### Common Mistakes

- Copying the SLA
- Choosing the highest possible number
- Omitting the window
- Setting a target no one can influence

### Reflection Questions

1. What would another nine cost?
2. What user benefit would it create?

---

## 14. Exercise 10: Calculate an Error Budget

### Objective

Calculate and interpret allowed unreliability.

### Input

A service has:

- 99.9 percent SLO
- 8,000,000 eligible requests in 28 days
- 3,200 bad requests

### Tasks

Calculate:

1. Error-budget percentage.
2. Allowed bad requests.
3. Budget consumption.
4. Remaining budget.
5. Expected daily allowance if demand were uniform.

Then explain why uniform daily allowance may mislead.

### Required Deliverable

A calculation sheet with formulas and interpretation.

### Validation Criteria

- Allowed bad requests equal 8,000
- Consumption equals 40 percent
- Remaining budget equals 60 percent
- Interpretation includes demand variation

### Common Mistakes

- Treating budget as planned downtime
- Confusing remaining budget with burn rate
- Ignoring actual eligible volume

### Reflection Questions

1. Does remaining budget make every release safe?
2. What other evidence is required?

---

## 15. Exercise 11: Calculate Burn Rate

### Objective

Interpret how quickly a service is consuming its allowance.

### Input

The SLO allows a 0.1 percent error rate. During the last hour, the observed error rate is 2 percent.

### Tasks

1. Calculate burn rate.
2. Explain what a burn rate of 1 means.
3. Estimate how quickly a full-period budget would be consumed if the rate continued.
4. Propose short and long alert windows.
5. Define the required response.

### Required Deliverable

A burn-rate analysis and alert policy draft.

### Validation Criteria

- Burn rate equals 20
- Urgency reflects rapid consumption
- Policy avoids paging on minor fluctuations
- Action and owner are explicit

### Common Mistakes

- Looking only at remaining budget
- Paging on every bad event
- Defining a threshold without an action

### Reflection Questions

1. Why use more than one window?
2. Which rapid failures might still escape detection?

---

## 16. Exercise 12: Write an Error-Budget Policy

### Objective

Turn SLO performance into agreed operational decisions.

### Tasks

Define:

- Normal state
- Elevated burn state
- Budget-at-risk state
- Exhausted state
- Allowed changes
- Restricted changes
- Reliability priorities
- Exception authority
- Recovery conditions
- Communication
- Review frequency

### Required Deliverable

A one-page error-budget policy.

### Validation Criteria

- Policy is agreed across product, development, and SRE
- Responses are proportional to risk
- Security and urgent fixes remain possible
- Exceptions require authorized acceptance
- Policy is not punitive

### Common Mistakes

- Total feature freeze as the only response
- Letting SRE own every business tradeoff
- Treating unused budget as a requirement to take risk

### Reflection Questions

1. Who may override the policy?
2. What evidence returns the service to normal state?

---

## 17. Exercise 13: Build a Reliability Risk Statement

### Objective

Connect technical failure to user and business consequence.

### Tasks

Use this form:

> Because of [condition], there is a possibility that [service event] will prevent [user] from completing [journey], resulting in [consequence].

Write five risk statements. For each, record likelihood evidence, impact evidence, uncertainty, owner, controls, and residual risk.

### Required Deliverable

A reliability risk register with five entries.

### Validation Criteria

- Cause, event, and consequence are distinct
- User journey is named
- Technical severity is not confused with business severity
- Uncertainty is visible
- Risk owner has authority

### Common Mistakes

- Writing a defect instead of a risk
- Using unsupported numeric precision
- Assigning all risk acceptance to SRE

### Reflection Questions

1. Which risk has the greatest uncertainty?
2. Which control reduces consequence rather than likelihood?

---

## 18. Exercise 14: Define Risk Tolerance

### Objective

Translate organizational risk decisions into operational boundaries.

### Tasks

For one CUJ, define tolerance for:

- Failed events
- Maximum continuous outage
- Latency
- Incorrect results
- Data loss
- Recovery time
- Geographic impact
- Critical-period impact

Identify who approves each tolerance.

### Required Deliverable

A reliability tolerance statement.

### Validation Criteria

- Uses measurable boundaries
- Includes time and scope
- Separates appetite, tolerance, capacity, and acceptance
- Identifies authorized decision owners
- Connects to SLO, RTO, and RPO where relevant

### Common Mistakes

- Saying zero risk without evidence
- Using one percentage for every failure form
- Ignoring maximum outage duration

### Reflection Questions

1. Can monthly availability meet target while tolerance is violated?
2. Which tolerance is hardest to verify?

---

## 19. Exercise 15: Build a Failure Model

### Objective

Define the failures a service must prevent, tolerate, contain, or recover from.

### Tasks

Include at least:

- Process crash
- Host failure
- Zone failure
- Network partition
- Dependency slowdown
- Configuration error
- Bad deployment
- Capacity exhaustion
- Data corruption
- Credential loss
- Control-plane failure
- Human unavailability

For each, define expected behavior, detection, containment, recovery, and assumption.

### Required Deliverable

A failure-model table.

### Validation Criteria

- Failure scope is explicit
- Common-mode failure is considered
- Service behavior is defined
- Assumptions are visible
- Unsupported failures are recorded

### Common Mistakes

- Claiming fault tolerance without a fault model
- Listing only hardware failure
- Ignoring control planes and people

### Reflection Questions

1. Which failure is most likely to exceed the design?
2. Which assumption needs a test?

---

## 20. Exercise 16: Map Failure Domains

### Objective

Determine whether redundancy is genuinely independent.

### Tasks

Map components across:

- Process
- Host
- Rack or physical location
- Zone
- Region
- Network
- Control plane
- Identity
- Data
- Organization
- Vendor

Identify shared dependencies for every redundant path.

### Required Deliverable

A failure-domain map and common-mode risk list.

### Validation Criteria

- Redundant components are traced to shared dependencies
- Operator and access failure are included
- Data corruption is considered
- Each common-mode risk has an owner

### Common Mistakes

- Counting replicas without location
- Assuming multiple regions means independence
- Ignoring shared configuration and credentials

### Reflection Questions

1. Which single control plane can affect every region?
2. What evidence proves independence?

---

## 21. Exercise 17: Design Graceful Degradation

### Objective

Preserve critical value when full service cannot be delivered.

### Tasks

For SRE World Shop, classify capabilities as:

- Must continue
- May degrade
- May be disabled
- Must fail closed

Define trigger, user experience, data behavior, capacity benefit, security effect, recovery, and verification.

### Required Deliverable

A degradation policy and prioritized capability map.

### Validation Criteria

- Critical journeys remain protected
- Degraded behavior is honest to users
- Data integrity is preserved
- Security-sensitive actions fail safely
- Return to normal is tested

### Common Mistakes

- Treating degraded as hidden failure
- Disabling the highest-value journey first
- Ignoring stale or partial data risk

### Reflection Questions

1. Which feature releases the most capacity?
2. When should a service fail closed?

---

## 22. Exercise 18: Write a Recovery Plan

### Objective

Create a complete recovery plan for a defined disaster.

### Tasks

Document:

- Disaster declaration criteria
- Incident authority
- Recovery scope
- RTO and RPO
- Dependencies
- Access
- Data source
- Recovery sequence
- Communication
- Verification
- Failback
- Abort conditions

### Required Deliverable

A recovery plan for regional loss or destructive data failure.

### Validation Criteria

- More than infrastructure is restored
- Data is validated
- Access survives the disaster
- Dependencies are included
- Failback is explicit
- Business owner approves objectives

### Common Mistakes

- Calling backup a recovery plan
- Omitting verification
- Testing only failover and not failback

### Reflection Questions

1. Which step depends on the failed environment?
2. Who may declare the disaster?

---

## 23. Exercise 19: Design a Recovery Exercise

### Objective

Test recovery safely and produce credible evidence.

### Tasks

Define:

- Hypothesis
- Scope
- Preconditions
- Participants
- Safety controls
- Stop conditions
- Injected failure
- Expected observations
- Measurements
- Verification
- Cleanup
- Learning review

### Required Deliverable

A controlled recovery exercise plan.

### Validation Criteria

- Explicit authorization exists
- Blast radius is bounded
- User impact is prevented or accepted
- Observability covers the test
- Abort path is tested
- Evidence supports RTO and RPO claims

### Common Mistakes

- Randomly breaking production
- Testing only the happy path
- Declaring success when infrastructure starts

### Reflection Questions

1. What result would disprove recovery confidence?
2. How does the test remain representative?

---

## 24. Exercise 20: Create a Production Responsibility Matrix

### Objective

Assign accountability, responsibility, authority, and participation.

### Tasks

For these decisions, name the roles involved:

- SLO approval
- Release approval
- Emergency rollback
- Incident command
- External communication
- Capacity investment
- Security containment
- Disaster declaration
- Business risk acceptance
- Service retirement

### Required Deliverable

A responsibility and decision-rights matrix.

### Validation Criteria

- One accountable owner exists for each outcome
- Authority matches responsibility
- SRE does not own every decision
- Product and development remain involved
- Escalation is clear

### Common Mistakes

- Assigning several accountable owners
- Confusing participation with ownership
- Giving responsibility without production access

### Reflection Questions

1. Which decision has no available authority after hours?
2. Where can conflicting commands occur?

---

## 25. Exercise 21: Build a Service Ownership Record

### Objective

Create evidence of real service ownership.

### Tasks

Document:

- Accountable team
- Technical lead
- Product owner
- Service purpose
- CUJs
- SLOs
- Dependencies
- On-call
- Escalation
- Change path
- Data and security obligations
- Recovery
- Lifecycle state
- Review date

### Required Deliverable

A minimum viable service ownership record.

### Validation Criteria

- Current and discoverable
- Connected to operating capability
- Includes decision rights
- Covers transfer and retirement
- Verified by the named owner

### Common Mistakes

- Treating repository ownership as service ownership
- Listing a person without a team
- Omitting lifecycle and after-hours coverage

### Reflection Questions

1. What happens during reorganization?
2. How is ownership acceptance verified?

---

## 26. Exercise 22: Perform a Production Readiness Review

### Objective

Evaluate whether a service is ready for launch or SRE onboarding.

### Tasks

Review:

- Service definition
- Ownership
- CUJs and SLOs
- Architecture and failure modes
- Telemetry and alerts
- Capacity
- Change and rollback
- Security and access
- Incident response
- Recovery
- Toil and support model
- Known risks

Classify findings as blocker, required action, accepted risk, or improvement.

### Required Deliverable

A readiness decision record with evidence.

### Validation Criteria

- Review occurs before irreversible commitment
- Findings have owners
- Exceptions have authorized risk owners
- Readiness is not treated as a permanent guarantee
- SRE is not the only approver

### Common Mistakes

- Checklist completion without evidence
- Treating every finding as a blocker
- Ignoring product and business readiness

### Reflection Questions

1. Which blocker prevents safe launch?
2. Which gap can be controlled during limited release?

---

## 27. Exercise 23: Design an Incident Response Model

### Objective

Create a structured response system before an incident.

### Tasks

Define:

- Declaration criteria
- Severity levels
- Incident commander
- Operations lead
- Communications lead
- Documentation role
- Escalation
- Handoff
- Status update cadence
- Closure and verification
- Post-incident review criteria

### Required Deliverable

An incident-response policy and role card.

### Validation Criteria

- One clear command line exists
- Roles can expand and contract
- Declaration is easy
- User impact guides severity
- Handoff transfers authority explicitly
- Recovery requires verification

### Common Mistakes

- Letting every responder command
- Searching for root cause before mitigation
- Closing when dashboards turn green

### Reflection Questions

1. Who declares outside business hours?
2. Which role communicates uncertainty?

---

## 28. Exercise 24: Run a Tabletop Incident

### Objective

Practice coordination and decision-making without disrupting a real service.

### Scenario

During a campaign, checkout success falls from 99.9 percent to 65 percent. Payment authorization succeeds, order creation fails, retries increase, and customers report duplicate charges.

### Tasks

1. Assign roles.
2. Declare severity.
3. State facts, hypotheses, and unknowns.
4. Choose immediate mitigation.
5. Write two status updates.
6. Define recovery verification.
7. Record decisions and risks.

### Required Deliverable

An incident timeline, decision log, and recovery checklist.

### Validation Criteria

- User harm drives priority
- Duplicate processing is contained
- Evidence is preserved
- Communication is accurate
- Data reconciliation is included
- One incident commander remains clear

### Common Mistakes

- Restarting everything
- Increasing retries
- Declaring recovery before reconciliation

### Reflection Questions

1. Which action had the greatest secondary risk?
2. What evidence changed your diagnosis?

---

## 29. Exercise 25: Write a Learning Review

### Objective

Turn an incident into technical and organizational learning.

### Tasks

Include:

- Summary
- User impact
- Timeline
- Detection
- Response
- Contributing conditions
- What helped
- What made response harder
- Near misses
- Corrective actions
- Owners
- Verification

Avoid a single-person root-cause statement.

### Required Deliverable

A blameless learning review.

### Validation Criteria

- Explains why actions made sense at the time
- Identifies system and organizational conditions
- Separates learning from misconduct review
- Prioritizes actions by risk reduction
- Actions require closure evidence

### Common Mistakes

- Ending with human error
- Creating dozens of low-value actions
- Omitting successful controls

### Reflection Questions

1. Which condition made the incident possible?
2. Which action reduces recurrence most?

---

## 30. Exercise 26: Audit Alert Quality

### Objective

Determine whether paging supports urgent action.

### Tasks

Review at least 30 recent alerts. For each, record:

- Service
- User impact
- Urgency
- Required action
- Outcome
- Duplicate status
- Runbook
- Escalation
- Time of day

Calculate actionability and identify missing coverage.

### Required Deliverable

An alert-quality report and remediation backlog.

### Validation Criteria

- Precision and coverage are both considered
- Nonurgent work is rerouted
- Duplicate alerts are grouped
- Silent user failures are identified
- Removal has an owner and verification plan

### Common Mistakes

- Removing alerts only to improve volume
- Paging on warnings
- Assuming no page means no impact

### Reflection Questions

1. Which alert should never wake a person?
2. Which incident had no useful alert?

---

## 31. Exercise 27: Measure On-Call Sustainability

### Objective

Evaluate whether the response model is safe and sustainable.

### Tasks

Measure twelve weeks of:

- Pages per shift
- After-hours pages
- Actionability
- Incident duration
- Escalations
- Consecutive sleep interruptions
- Rotation size
- Coverage gaps
- Recovery time
- Responder feedback

### Required Deliverable

An on-call health assessment.

### Validation Criteria

- Distribution is visible
- Individual privacy is protected
- Averages do not hide peak harm
- Staffing and service commitments are connected
- Corrective actions address system design

### Common Mistakes

- Ranking individual responders
- Measuring acknowledgment only
- Treating burnout as personal weakness

### Reflection Questions

1. Which shift pattern is unsafe?
2. Should coverage change before staffing improves?

---

## 32. Exercise 28: Identify and Measure Toil

### Objective

Separate toil from necessary operations and engineering work.

### Tasks

For four weeks, classify work by:

- Manual effort
- Repetition
- Automation potential
- Tactical nature
- Service relation
- Growth
- Enduring value
- Risk
- Interruption

Calculate volume, percentage, rate, and distribution.

### Required Deliverable

A toil inventory and prioritized reduction plan.

### Validation Criteria

- Not all operational work is labeled toil
- Denominator is defined
- Cross-team movement is considered
- Highest-priority work reflects risk and total cost
- Accepted toil is explicit

### Common Mistakes

- Calling disliked work toil
- Setting zero toil as the goal
- Assigning all repetitive work to junior engineers

### Reflection Questions

1. Which toil source grows fastest?
2. Which should be accepted rather than automated?

---

## 33. Exercise 29: Evaluate an Automation Proposal

### Objective

Decide whether automation is the correct response.

### Tasks

Document:

- Current task and cost
- User or operational outcome
- Trigger
- Preconditions
- Permissions
- Maximum scope
- Failure modes
- Observability
- Stop control
- Rollback
- Verification
- Owner
- Maintenance cost

Compare automation with elimination, simplification, self-service, transfer, and accepted manual work.

### Required Deliverable

An automation decision record.

### Validation Criteria

- Benefit exceeds lifecycle cost
- Blast radius is bounded
- Permissions follow least privilege
- Failure is observable
- Human approval remains where judgment is required
- Outcome verification exists

### Common Mistakes

- Automating a broken process
- Granting fleet-wide authority
- Counting script completion as impact

### Reflection Questions

1. How could automation make the failure faster?
2. What is the safest fallback?

---

## 34. Exercise 30: Separate Engineering and Operational Work

### Objective

Evaluate whether the team can create lasting improvement.

### Tasks

Classify one quarter of work as:

- Software engineering
- Systems engineering
- Operational work
- Toil
- Incident response
- Support
- Product development
- Organizational overhead

Identify which work creates enduring value and which work displaces it.

### Required Deliverable

A work-mix report with capacity recommendations.

### Validation Criteria

- Categories have definitions
- Toil remains a subset of operations
- Meetings are not automatically classified as toil
- Engineering completion requires production verification
- Recommended allocation fits the operating model

### Common Mistakes

- Treating code as the only engineering work
- Treating operations as low skill
- Ignoring interruptions

### Reflection Questions

1. Can the team make tomorrow better than today?
2. Which responsibility should move or stop?

---

## 35. Exercise 31: Compare SRE With Adjacent Disciplines

### Objective

Define clear relationships without dismissing other engineering functions.

### Tasks

Compare SRE with:

- DevOps
- Traditional operations
- Platform engineering
- Production engineering
- Cloud engineering
- Security engineering

For each, document primary purpose, unit of concern, typical responsibilities, overlap, and boundary.

### Required Deliverable

A comparison matrix and collaboration model.

### Validation Criteria

- SRE is not defined by superiority
- Overlap and difference are both visible
- Team names are not assumed to prove practice
- Ownership interfaces are clear

### Common Mistakes

- Treating DevOps as one team type
- Calling platform engineering SRE
- Declaring traditional operations obsolete

### Reflection Questions

1. Which boundary is most ambiguous in your organization?
2. What work is currently misrouted?

---

## 36. Exercise 32: Write an SRE Responsibility Charter

### Objective

Define what an SRE team will and will not do.

### Tasks

Write:

- Mission
- Service scope
- User outcomes
- Responsibilities
- Exclusions
- Decision authority
- On-call model
- Engineering commitment
- Toil limit
- Engagement lifecycle
- Success measures
- Escalation

### Required Deliverable

A two-page SRE team charter.

### Validation Criteria

- Scope is bounded
- Responsibility matches authority
- Product teams remain accountable
- Engineering capacity is protected
- Handback and exit exist
- Success uses service outcomes

### Common Mistakes

- Mission states ensure everything is reliable
- No exclusions
- Pager ownership begins immediately

### Reflection Questions

1. Which excluded work will face the most pressure to enter?
2. Who protects the charter?

---

## 37. Exercise 33: Select an SRE Operating Model

### Objective

Choose an organizational arrangement based on evidence.

### Tasks

Compare at least three models:

- Centralized
- Product-aligned
- Infrastructure
- Platform-aligned
- Embedded
- Consulting
- Federated
- Reliability champions

Evaluate service fit, staffing, authority, knowledge, on-call, cost, scale, and failure modes.

### Required Deliverable

An operating-model decision record.

### Validation Criteria

- Model follows the reliability problem
- Hybrid components are explicit
- Staffing is credible
- Workload can be regulated
- Migration and review are planned

### Common Mistakes

- Copying a large company structure
- Selecting the most complex model
- Treating the organization chart as the outcome

### Reflection Questions

1. What breaks if the organization doubles in size?
2. Which model failure is most likely?

---

## 38. Exercise 34: Design Service Tiers

### Objective

Allocate reliability and SRE capacity according to service risk.

### Tasks

Define three or four tiers using:

- User harm
- Revenue or operational dependence
- Safety
- Security
- Data integrity
- Regulatory obligation
- Time sensitivity
- Alternatives
- Downstream blast radius

For each tier, define SLO, support, recovery, readiness, and review expectations.

### Required Deliverable

A tier policy and sample classification of ten services.

### Validation Criteria

- Criteria are evidence-based
- Highest tier is scarce
- Internal and low-volume services can qualify
- Costs and obligations are visible
- Exception authority exists

### Common Mistakes

- Allowing every team to choose the highest tier
- Using revenue alone
- Creating tiers with names but no different commitments

### Reflection Questions

1. Which service classification was disputed?
2. What incentive could create tier inflation?

---

## 39. Exercise 35: Assess Whether SRE Is Needed

### Objective

Determine whether a service needs SRE practices, temporary help, or dedicated capacity.

### Tasks

Assess:

- Service criticality
- Reliability performance
- Incident recurrence
- Change risk
- Operational load
- Recovery confidence
- Dependency complexity
- Human sustainability
- Engineering leverage
- Existing team capability

### Required Deliverable

An SRE need assessment with a recommended response.

### Validation Criteria

- Need starts with service outcomes
- Multiple evidence types are used
- Need for practices is separated from need for a team
- Alternative functions are considered
- Cost of doing nothing is stated

### Common Mistakes

- Using company size as the decision
- Claiming Kubernetes creates the need
- Hiring SRE for one temporary incident

### Reflection Questions

1. What is the smallest credible intervention?
2. Which evidence could change the decision?

---

## 40. Exercise 36: Assess SRE Readiness

### Objective

Determine whether the organization can support SRE correctly.

### Tasks

Evaluate:

- Service definition
- Accountable owner
- Product participation
- SLO consequences
- Production authority
- Safe access
- Staffing
- On-call sustainability
- Engineering capacity
- Workload control
- Leadership sponsorship
- Funding
- Pause and handback

### Required Deliverable

A readiness decision of ready, conditionally ready, not ready, or unsafe.

### Validation Criteria

- Need and readiness are separate
- Hard blockers are identified
- Conditional gaps have safeguards
- Exceptions have risk owners and deadlines
- Decision includes reassessment date

### Common Mistakes

- Waiting for perfection
- Ignoring responsibility without authority
- Starting with immediate pager transfer

### Reflection Questions

1. Which blocker must be solved first?
2. What reliability work can begin safely now?

---

## 41. Exercise 37: Audit SRE Misunderstandings

### Objective

Identify beliefs that distort SRE implementation.

### Tasks

Interview representatives from leadership, product, development, operations, platform, and SRE. Ask each to define:

- SRE
- Reliability
- Error budget
- Toil
- Service ownership
- SRE success

Compare definitions and observed behavior.

### Required Deliverable

A misconception register with corrective actions.

### Validation Criteria

- Records the valid concern behind each belief
- Explains production consequence
- Corrects behavior, not only words
- Avoids dismissing adjacent disciplines
- Defines verification

### Common Mistakes

- Treating disagreement as ignorance
- Correcting terminology without operating change
- Assuming SRE has the only valid perspective

### Reflection Questions

1. Which misunderstanding creates the most risk?
2. What behavior proves correction?

---

## 42. Exercise 38: Build an SRE Success Scorecard

### Objective

Measure SRE through a balanced evidence system.

### Tasks

Select no more than two primary measures for each:

- User reliability
- Risk and resilience
- Incidents and recovery
- Change and capacity
- Engineering impact
- Toil and on-call
- Ownership and engagement

For each, define state, trend, confidence, owner, target, and decision.

### Required Deliverable

A one-page SRE scorecard with metric contracts.

### Validation Criteria

- Begins with user outcomes
- Separates performance from confidence
- Includes leading and lagging indicators
- Avoids individual ranking
- Contains anti-gaming measures
- Drives a named decision

### Common Mistakes

- Counting dashboards and scripts
- Using one success metric
- Comparing unlike services directly

### Reflection Questions

1. Which number can improve while the system worsens?
2. Which metric should be retired?

---

## 43. Exercise 39: Write an Executive Reliability Brief

### Objective

Communicate reliability to a decision-making audience.

### Tasks

Write a one-page brief containing:

- Critical service outcome
- Current reliability state
- User and business consequence
- Material risks
- Recovery confidence
- Reliability investment options
- Recommendation
- Residual risk
- Required decision

### Required Deliverable

A one-page executive reliability brief.

### Validation Criteria

- Uses plain language
- Includes evidence and uncertainty
- Avoids unnecessary infrastructure detail
- Identifies decision owner
- Presents tradeoffs, not a predetermined demand

### Common Mistakes

- Reporting dashboard colors only
- Converting every consequence into uncertain revenue
- Hiding risk behind technical vocabulary

### Reflection Questions

1. What decision should the reader make?
2. Which uncertainty must remain visible?

---

## 44. Exercise 40: Run a Reliability Review

### Objective

Turn service evidence into decisions and owned action.

### Tasks

Create an agenda covering:

1. CUJ and SLO state.
2. Error-budget burn.
3. Incidents and recurrence.
4. Capacity and dependency risk.
5. Recovery evidence.
6. Toil and on-call health.
7. Reliability projects.
8. Decisions.

Record owners, dates, and verification.

### Required Deliverable

A completed reliability review record.

### Validation Criteria

- Decision makers attend
- Evidence confidence is visible
- Discussion distinguishes facts and hypotheses
- Actions connect to risk
- Meeting produces decisions or learning

### Common Mistakes

- Reading dashboards without action
- Inviting everyone without clear roles
- Repeating unresolved risks every month

### Reflection Questions

1. Which agenda item produced no value?
2. Which decision lacked authority?

---

## 45. Exercise 41: Capstone, Complete SRE Foundation Assessment

### Objective

Combine the complete Chapter 1 foundation into one service assessment.

### Tasks

Produce:

1. SRE definition and scope.
2. Service definition.
3. User and CUJ inventory.
4. Journey and dependency map.
5. Reliability-property requirements.
6. SLI specifications.
7. SLO proposals.
8. Error-budget policy.
9. Reliability risk register.
10. Failure-domain model.
11. Degradation strategy.
12. Recovery plan and exercise.
13. Production ownership matrix.
14. Incident-response model.
15. Alert, on-call, and toil assessment.
16. Engineering roadmap.
17. SRE need and readiness decision.
18. Operating-model recommendation.
19. Success scorecard.
20. Executive brief.

### Required Deliverable

An SRE Foundation Service Dossier.

### Validation Criteria

- Every artifact refers to the same defined service
- User outcomes remain the top-level concern
- Metrics support decisions
- Authority matches responsibility
- Recovery is testable
- Workload is sustainable
- Engineering priorities trace to risk
- Unknowns and assumptions are visible

### Common Mistakes

- Producing unrelated templates
- Starting with tools
- Declaring the service ready without evidence
- Omitting human sustainability

### Reflection Questions

1. Which artifact changed your view of the service most?
2. Which unresolved risk needs formal acceptance?
3. Is dedicated SRE support justified?

---

## 46. Capstone Dossier Structure

Use this folder structure if you save the capstone as separate files:

Create `sre-foundation-dossier/` with these files:

- `01-service-definition.md`
- `02-users-and-cujs.md`
- `03-journey-and-dependencies.md`
- `04-reliability-properties.md`
- `05-slis-and-slos.md`
- `06-error-budget-policy.md`
- `07-risk-register.md`
- `08-failure-model.md`
- `09-degradation-and-recovery.md`
- `10-ownership-and-incidents.md`
- `11-toil-and-on-call.md`
- `12-engineering-roadmap.md`
- `13-sre-need-and-readiness.md`
- `14-operating-model.md`
- `15-success-scorecard.md`
- `16-executive-brief.md`

Do not include credentials, secrets, personal information, or sensitive production data.

---

## 47. Capstone Engineering Roadmap

Prioritize proposed work by:

- User harm reduced
- Risk likelihood reduced
- Blast radius reduced
- Recovery improved
- Toil removed
- Engineering effort
- Dependency
- Reversibility
- Confidence

Separate:

- Immediate risk controls
- Near-term reliability work
- Long-term architecture
- Accepted risk
- Work requiring business decision

---

## 48. Capstone Review Panel

A useful review panel may include:

- Service owner
- Product representative
- Application engineer
- SRE
- Platform or infrastructure engineer
- Security representative
- Data owner
- Business risk owner

Use only roles relevant to the service. Each reviewer should state approval, concern, required action, or accepted risk within their authority.

---

## 49. Capstone Evaluation Rubric

Score each area from 0 to 4.

| Score | Meaning |
| --- | --- |
| 0 | Missing |
| 1 | Present but unsupported |
| 2 | Partially defined |
| 3 | Complete and evidence-based |
| 4 | Verified through use or testing |

Evaluate:

- Service and user definition
- CUJs
- Reliability properties
- SLIs and SLOs
- Risk decisions
- Failure model
- Recovery
- Ownership and authority
- Incident readiness
- Toil and sustainability
- Engineering plan
- Operating model
- Measurement quality
- Communication

A total score should not override a severe hard blocker.

---

## 50. Peer Review Guide

When reviewing another learner's work:

1. Identify one strong decision.
2. Identify one unsupported assumption.
3. Find one missing user or journey.
4. Challenge one metric definition.
5. Test one recovery claim.
6. Identify one ownership gap.
7. Check one sustainability risk.
8. Recommend one high-value improvement.

Critique the artifact and reasoning, not the person.

---

## 51. Facilitator Guide

For a team workshop:

- Use a service familiar to participants.
- Provide evidence in stages.
- Assign different organizational roles.
- Introduce time and budget constraints.
- Require explicit decisions.
- Ask what would disprove each hypothesis.
- Include a handoff or escalation.
- End with verification and learning.

Reward safe reasoning, not fast guessing.

---

## 52. Evidence Standards

A strong submission distinguishes:

- Observed production data
- User reports
- Incident records
- Tested capability
- Expert judgment
- Assumptions
- Unknowns

For every important claim, state:

- Source
- Time period
- Population
- Definition
- Limitation
- Confidence

Do not invent precision where evidence is weak.

---

## 53. Safety Standards

Before any live exercise:

- Obtain authorization
- Define scope
- Protect personal and sensitive data
- Use least privilege
- Establish stop conditions
- Confirm rollback
- Monitor user impact
- Assign incident authority
- Preserve evidence
- Clean up safely

Prefer tabletop, simulation, staging, or isolated tests when production risk is unnecessary.

---

## 54. Documentation Standards

Every artifact should include:

- Title
- Service
- Owner
- Status
- Created date
- Last reviewed date
- Scope
- Assumptions
- Evidence
- Decision
- Next review

Keep documents actionable. A long artifact that no one can use during a decision is incomplete.

---

## 55. Exercise Completion Tracker

| Stage | Exercises | Status |
| --- | --- | --- |
| SRE and service definition | 1 to 6 | Not started |
| Measurement and objectives | 7 to 12 | Not started |
| Risk, resilience, and recovery | 13 to 19 | Not started |
| Ownership and production operation | 20 to 27 | Not started |
| Toil and engineering work | 28 to 30 | Not started |
| Organization and operating models | 31 to 37 | Not started |
| Measurement and communication | 38 to 40 | Not started |
| Capstone | 41 | Not started |

Update status with Not started, In progress, Needs review, or Complete.

---

## 56. Foundation Practical Skills Checklist

### Service and User Understanding

- [ ] I can define a service by its outcome.
- [ ] I can identify human and system users.
- [ ] I can discover and prioritize CUJs.
- [ ] I can map dependencies and ownership.

### Reliability and Risk

- [ ] I can distinguish reliability properties.
- [ ] I can write good and eligible event definitions.
- [ ] I can design an SLI.
- [ ] I can propose an SLO.
- [ ] I can calculate an error budget and burn rate.
- [ ] I can write a reliability risk statement.
- [ ] I can define risk tolerance.

### Resilience and Recovery

- [ ] I can create a failure model.
- [ ] I can map common failure domains.
- [ ] I can design graceful degradation.
- [ ] I can define RTO and RPO requirements.
- [ ] I can write and test a recovery plan.

### Production Responsibility

- [ ] I can distinguish accountability, responsibility, authority, and participation.
- [ ] I can create a service ownership record.
- [ ] I can conduct a production-readiness review.
- [ ] I can design incident roles and escalation.
- [ ] I can write a learning review.

### Sustainable Operations

- [ ] I can audit alert quality.
- [ ] I can assess on-call sustainability.
- [ ] I can identify and measure toil.
- [ ] I can evaluate automation risk.
- [ ] I can separate engineering and operational work.

### Organization

- [ ] I can distinguish SRE from adjacent disciplines.
- [ ] I can write an SRE charter.
- [ ] I can select an operating model.
- [ ] I can design service tiers.
- [ ] I can evaluate SRE need and readiness.
- [ ] I can identify SRE misunderstandings.

### Measurement and Communication

- [ ] I can build a balanced SRE scorecard.
- [ ] I can identify metric gaming risk.
- [ ] I can run a reliability review.
- [ ] I can communicate reliability to leaders.
- [ ] I can state uncertainty honestly.

---

## 57. Reflection Questions

1. Which exercise was hardest, and why?
2. Which artifact exposed the most hidden risk?
3. Which existing metric failed to represent users?
4. Which assumption needs immediate testing?
5. Which operational task should be eliminated rather than automated?
6. Which responsibility lacks authority?
7. Which recovery claim lacks evidence?
8. Is on-call sustainable under realistic staffing?
9. Does the organization need SRE, and is it ready?
10. Which operating model fits the service?
11. Which success metric could be gamed?
12. What will you change in the next 30 days?

---

## 58. Knowledge Check

1. Why should the exercises begin with service and user definition?
2. What distinguishes a CUJ from a component or screen?
3. What is the difference between an SLI specification and implementation?
4. What does burn rate measure?
5. Why should risk tolerance include more than availability percentage?
6. What makes redundancy independent?
7. What must be verified after recovery?
8. Why must authority match responsibility?
9. What distinguishes toil from all operational work?
10. Why is automation completion not proof of success?
11. What is the difference between SRE need and readiness?
12. Why should a capstone score not override a hard blocker?

---

## 59. Knowledge Check Answers

1. SRE exists to protect defined service outcomes for users. Starting with components or tools can direct work away from actual value.
2. A CUJ is a bounded, measurable path through which a defined user achieves an important outcome. It may cross many screens, components, and teams.
3. The specification describes the service behavior that matters. The implementation describes how that behavior is measured in practice.
4. Burn rate measures the observed error rate relative to the error rate allowed by the SLO.
5. The same availability percentage can hide unacceptable continuous outage, data loss, incorrect results, or failure during a critical period.
6. Redundant paths must not share the failure conditions they are intended to survive, and their independence must be tested.
7. Critical user journeys, data correctness, dependencies, capacity, security posture, backlogs, and stable operation.
8. A team cannot own an outcome if it cannot make or influence the decisions and actions required to produce it.
9. Toil is commonly manual, repetitive, automatable, tactical, service-related, and growing. Operational work can also provide judgment, learning, and enduring value.
10. Automation may not be adopted, may move work, may introduce risk, or may fail to change the intended outcome.
11. Need asks whether reliability risk justifies focused engineering. Readiness asks whether the organization provides the conditions required for that work to succeed.
12. A severe ownership, authority, access, staffing, or recovery blocker can make the service unsafe regardless of the average score.

---

## 60. Key Takeaways

- Practical SRE begins with a defined service, users, and Critical User Journeys.
- Every reliability measure needs precise good and eligible event definitions.
- SLOs must support decisions, not only dashboards.
- Error-budget percentage, remaining budget, and burn rate answer different questions.
- Risk statements connect technical conditions to user and business consequence.
- Fault tolerance requires an explicit failure model and independent failure domains.
- Recovery must include data, dependencies, access, verification, and failback.
- Production responsibility requires clear accountability and decision authority.
- Structured incident response prioritizes mitigation, communication, control, and learning.
- Toil is a subset of operational work and must be measured before improvement.
- Automation needs bounded authority, observability, rollback, and verified impact.
- SRE operating models should follow service risk and organizational conditions.
- Need and readiness must be assessed separately.
- SRE success requires balanced service, risk, engineering, human, and organizational evidence.
- The capstone dossier should form one coherent service reliability system.

---

## 61. Authoritative Resources

### Service Levels and Risk

- [Google SRE Workbook: Implementing SLOs](https://sre.google/workbook/implementing-slos/)
- [Google SRE Workbook: Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/)
- [Google SRE Book: Embracing Risk](https://sre.google/sre-book/embracing-risk/)
- [Google SRE Book: Service Level Objectives](https://sre.google/sre-book/service-level-objectives/)

### Incidents, Toil, and On-Call

- [Google SRE Workbook: Incident Response](https://sre.google/workbook/incident-response/)
- [Google SRE Workbook: Postmortem Culture](https://sre.google/workbook/postmortem-culture/)
- [Google SRE Workbook: Eliminating Toil](https://sre.google/workbook/eliminating-toil/)
- [Google SRE Workbook: On-Call](https://sre.google/workbook/on-call/)

### Production Readiness and Engagement

- [Google SRE Book: Production Readiness Review](https://sre.google/sre-book/evolving-sre-engagement-model/)
- [Google SRE Workbook: SRE Engagement Model](https://sre.google/workbook/engagement-model/)
- [Google SRE Workbook: SRE Team Lifecycles](https://sre.google/workbook/team-lifecycles/)

### Reliability Design

- [Google SRE Workbook: Identifying and Recovering From Overload](https://sre.google/workbook/managing-load/)
- [Google SRE Workbook: Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/)
- [Google SRE Book: Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/)

### Source Interpretation

These resources explain SRE principles and practices. Adapt every exercise to the service's real users, risk, technology, authority, and safety requirements. Do not copy example targets or procedures into production without validation.

---

## 62. Related SRE World Sections

- [What Is SRE?](./01-What-Is-SRE.md)
- [The SRE Mindset](./03-The-SRE-Mindset.md)
- [Reliability as a Product Feature](./04-Reliability-as-a-Product-Feature.md)
- [Reliability and Business Risk](./05-Reliability-and-Business-Risk.md)
- [Reliability, Availability, Resilience, and Durability](./06-Reliability-Availability-Resilience-and-Durability.md)
- [Fault Tolerance and Disaster Recovery](./07-Fault-Tolerance-and-Disaster-Recovery.md)
- [Production Responsibility](./08-Production-Responsibility.md)
- [Service Ownership](./09-Service-Ownership.md)
- [Critical User Journeys](./10-Critical-User-Journeys.md)
- [Risk Tolerance](./11-Risk-Tolerance.md)
- [Engineering Work and Operational Work](./12-Engineering-Work-and-Operational-Work.md)
- [Toil](./13-Toil.md)
- [SRE and DevOps](./14-SRE-and-DevOps.md)
- [SRE and Traditional Operations](./15-SRE-and-Traditional-Operations.md)
- [SRE and Platform Engineering](./16-SRE-and-Platform-Engineering.md)
- [SRE and Production Engineering](./17-SRE-and-Production-Engineering.md)
- [SRE Responsibilities](./18-SRE-Responsibilities.md)
- [SRE Operating Models](./19-SRE-Operating-Models.md)
- [When an Organization Needs SRE](./20-When-an-Organization-Needs-SRE.md)
- [When an Organization Is Not Ready for SRE](./21-When-an-Organization-Is-Not-Ready-for-SRE.md)
- [Common SRE Misunderstandings](./22-Common-SRE-Misunderstandings.md)
- [Measuring SRE Success](./23-Measuring-SRE-Success.md)
- [SRE Foundation Production Scenarios](./24-SRE-Foundation-Production-Scenarios.md)
- [SRE Foundations](./README.md)

---

## Next Section

[Section 26: SRE Foundation Resources](./26-SRE-Foundation-Resources.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> A completed exercise is not only a document. It is evidence that an engineer can connect users, service behavior, risk, production action, ownership, recovery, and sustainable improvement.
