# SRE Foundation Completion Assessment

> This assessment determines whether a learner can explain SRE foundations, apply them to production situations, make defensible reliability decisions, and communicate those decisions with evidence.

## Section Purpose

Completing the reading in Chapter 1 does not prove that a learner understands SRE.

Foundation competence requires the ability to:

- Define SRE without reducing it to tools
- Connect reliability to users and business risk
- Distinguish related reliability concepts precisely
- Identify ownership and production responsibilities
- Separate engineering work, operational work, toil, and overhead
- Evaluate SRE operating models in context
- Recognize when an organization needs SRE
- Recognize when an organization is not ready for an SRE team
- Reason through production failure under uncertainty
- Produce useful reliability artifacts
- Explain and defend decisions

This final section assesses those abilities across all 26 preceding sections.

It is designed for:

- Independent learners
- Internal SRE training programs
- Engineering onboarding
- Study groups
- Mentors and reviewers
- Organizations evaluating foundation readiness

The assessment is tool-neutral. A learner should not need a particular cloud provider, orchestration platform, monitoring product, or programming language to complete it.

---

## Learning Outcomes

After completing this assessment successfully, you should be able to demonstrate that you can:

1. Explain the purpose and boundaries of SRE.
2. Apply an SRE mindset to ambiguous production problems.
3. Define reliability from the user's perspective.
4. Connect service failure to business consequences.
5. Distinguish reliability, availability, resilience, durability, fault tolerance, and disaster recovery.
6. Identify Critical User Journeys and meaningful service boundaries.
7. Describe risk tolerance using explicit assumptions and decision authority.
8. Classify engineering work, operational work, toil, and overhead.
9. Define production responsibility and service ownership.
10. Compare SRE with DevOps, traditional operations, platform engineering, and production engineering.
11. Select an SRE operating model that fits organizational conditions.
12. Identify whether an organization needs SRE and whether it is ready to support it.
13. Correct common SRE misunderstandings.
14. Select evidence that measures SRE success.
15. Analyze realistic production scenarios.
16. Create practical foundation artifacts.
17. Use authoritative resources to justify a reliability decision.

---

## 1. Assessment Structure

The assessment contains five parts.

| Part | Focus | Points |
| --- | --- | ---: |
| A | Foundation knowledge and distinctions | 20 |
| B | Applied service and risk analysis | 20 |
| C | Production scenario judgment | 25 |
| D | Practical reliability portfolio | 25 |
| E | Review, defense, and reflection | 10 |
| **Total** |  | **100** |

The assessment measures more than recall.

| Competency level | What the learner demonstrates |
| --- | --- |
| Recall | States a concept accurately |
| Explanation | Describes why the concept matters |
| Application | Uses the concept in a realistic service context |
| Analysis | Connects evidence, uncertainty, risk, and consequences |
| Judgment | Selects and defends an appropriate action |
| Creation | Produces an artifact another engineer could use |

---

## 2. Completion Rules

Use the following rules unless an instructor defines stricter requirements.

1. Complete Parts A through E.
2. Use your own words.
3. State assumptions when information is incomplete.
4. Separate facts, hypotheses, decisions, and unknowns.
5. Explain user impact before component impact.
6. Do not name a tool as a substitute for an engineering decision.
7. Cite sources used to support important claims.
8. Do not include confidential production data.
9. Redact service names, customer information, credentials, and security-sensitive details.
10. Preserve evidence of practical work.

Recommended assessment conditions:

- Part A: Closed notes
- Parts B and C: Open notes
- Part D: Open resources
- Part E: Reviewer discussion or written defense

Suggested time:

| Part | Suggested time |
| --- | ---: |
| A | 45 minutes |
| B | 75 minutes |
| C | 90 minutes |
| D | 4 to 8 hours |
| E | 30 to 45 minutes |

The portfolio may be completed over several days.

---

## 3. Passing Standard

Recommended result bands:

| Score | Result | Meaning |
| ---: | --- | --- |
| 90 to 100 | Distinction | Strong foundation reasoning and practical evidence |
| 80 to 89 | Proficient | Ready to continue to deeper SRE study |
| 70 to 79 | Developing | Core understanding is present, but important gaps remain |
| Below 70 | Not yet complete | Review weak areas and repeat the relevant parts |

A total score alone is not sufficient.

To complete Chapter 1, the learner must also meet all competency gates:

- Score at least 14 of 20 in Part A.
- Score at least 14 of 20 in Part B.
- Score at least 17 of 25 in Part C.
- Score at least 17 of 25 in Part D.
- Score at least 7 of 10 in Part E.
- Avoid every automatic-review condition listed below.

### Automatic Review Conditions

A submission requires revision when it:

- Defines SRE mainly as a toolset
- Treats 100 percent reliability as the default goal
- Uses infrastructure health as proof of user success
- Confuses an SLO with an SLA
- Confuses replication with backup or disaster recovery
- Assigns accountability to a team without authority
- Treats all operational work as toil
- Treats automation as the answer without analyzing the work
- Recommends an SRE team without evaluating organizational readiness
- Uses activity metrics as the only evidence of SRE success
- Proposes a production action without verification or rollback thinking
- Ignores security, data integrity, or human sustainability where relevant

---

## 4. Required Submission Package

Create one assessment directory.

```text
sre-foundation-assessment/
├── README.md
├── part-a-foundation-knowledge.md
├── part-b-service-analysis.md
├── part-c-production-scenarios.md
├── part-d-practical-portfolio.md
├── part-e-defense-and-reflection.md
├── artifacts/
│   ├── service-brief.md
│   ├── critical-user-journey.md
│   ├── reliability-risk-record.md
│   ├── ownership-record.md
│   ├── work-classification.md
│   └── measurement-plan.md
└── evidence/
    ├── references.md
    └── verification-notes.md
```

The assessment `README.md` should contain:

- Learner name or identifier
- Assessment date
- Selected service
- Service type
- Whether the service is real, fictional, or anonymized
- Assumptions
- File index
- Self-assessed score
- Known limitations

---

## 5. Selecting a Service

Parts B and D require one service that remains consistent throughout the assessment.

You may use:

- A real service you own
- An anonymized production service
- A personal project with real users
- An internal platform capability
- A fictional service based on a realistic production context

Suitable examples include:

- Payment authorization service
- Identity and authentication service
- Payroll submission service
- Online checkout journey
- Document storage service
- Messaging service
- Internal deployment platform
- Data-processing pipeline
- Patient-record retrieval service
- Emergency notification service

The service must have:

- A defined user or dependent system
- A valuable outcome
- At least one Critical User Journey
- Multiple dependencies
- Meaningful failure consequences
- An owner
- A change mechanism
- A recovery requirement

Avoid using a single server, repository, cluster, dashboard, or database as the complete service definition unless that item itself provides the user outcome.

---

# Part A: Foundation Knowledge and Distinctions

## 6. Part A Instructions

Answer all 20 questions.

Each question is worth one point.

A complete answer must be accurate, direct, and relevant. One or two paragraphs are usually sufficient for short-response questions.

---

## 7. Foundation Questions

### Question 1

Define Site Reliability Engineering without referring to a specific tool, cloud provider, or job title.

### Question 2

Why is the service, rather than the server or cluster, the primary unit of SRE?

### Question 3

Explain why reliability is a product feature.

### Question 4

Describe the chain from a technical failure to a business consequence.

### Question 5

Distinguish reliability from availability.

### Question 6

Distinguish resilience from fault tolerance.

### Question 7

Distinguish durability from availability.

### Question 8

Explain why replication does not by itself provide disaster recovery.

### Question 9

Define production responsibility.

### Question 10

What capabilities must exist for service ownership to be real?

### Question 11

Define a Critical User Journey and explain why it matters to SRE.

### Question 12

Distinguish risk appetite, risk tolerance, and risk acceptance.

### Question 13

Distinguish engineering work, operational work, toil, and overhead.

### Question 14

Why is repetitive work not automatically toil?

### Question 15

Explain the relationship between SRE and DevOps.

### Question 16

State one important difference between SRE and traditional operations.

### Question 17

State one important difference between SRE and platform engineering.

### Question 18

Why can SRE and production engineering overlap without being identical?

### Question 19

Name three valid SRE operating models and one condition that influences model selection.

### Question 20

Why should SRE success be measured through outcomes, capability, and sustainability rather than activity alone?

---

## 8. Part A Answer Guide

Use this guide after completing the questions.

### Answer 1

SRE applies software and systems engineering methods to production operations so that services meet explicit reliability objectives with controlled risk and sustainable human effort.

### Answer 2

Users consume service outcomes. A service may span many repositories, systems, teams, and infrastructure components. Component health matters only in relation to the service behavior it supports.

### Answer 3

A capability produces value only when users can access it, complete it correctly, trust the result, and recover safely from disruption. Reliability is therefore part of the product experience.

### Answer 4

A failure condition causes service degradation, which affects a user journey, disrupts a business process, and creates a business consequence. The connection must be traced rather than assumed.

### Answer 5

Reliability describes whether a system performs its intended function consistently under defined conditions. Availability describes whether the required function is usable when needed. A service can be available but incorrect, slow, or unsafe.

### Answer 6

Fault tolerance is the ability to continue required operation through faults included in a defined fault model. Resilience is broader. It includes preparation, absorption, adaptation, degraded operation, recovery, and learning.

### Answer 7

Availability concerns whether a service or function can be used. Durability concerns whether committed data remains correct, preserved, and retrievable over time.

### Answer 8

Replication can copy deletion, corruption, or malicious changes. Replicas may share failure domains or credentials. Disaster recovery also requires recovery objectives, independent protection, access, procedures, validation, and tested restoration.

### Answer 9

Production responsibility is the continuing obligation and authority to maintain a service's intended outcome within agreed reliability, security, cost, and risk boundaries throughout its lifecycle.

### Answer 10

Real ownership requires a named accountable team, service knowledge, decision authority, operational capacity, measurable obligations, incident participation, and lifecycle continuity.

### Answer 11

A Critical User Journey is a bounded, measurable path through which a defined user achieves an important outcome. It guides SLIs, SLOs, alerting, incident severity, recovery, and reliability investment.

### Answer 12

Risk appetite is the broad amount and type of risk an organization is willing to pursue or retain. Risk tolerance defines acceptable variation or limits for a specific context. Risk acceptance is an authorized decision to retain a known residual risk.

### Answer 13

Engineering work creates lasting system or capability improvements. Operational work runs and supports the service. Toil is operational work that is manual, repetitive, automatable, tactical, lacks enduring value, and grows with service demand. Overhead is necessary coordination or administration that may not directly change the service.

### Answer 14

Repetition alone does not establish toil. Work may require judgment, produce learning, remain low-volume, or create enduring value. The complete characteristics and context must be evaluated.

### Answer 15

DevOps describes broad principles for collaboration, flow, automation, measurement, and shared responsibility. SRE is a more specific engineering discipline and operating model that implements compatible principles through mechanisms such as SLOs, error budgets, toil control, and production ownership.

### Answer 16

SRE explicitly limits operational load and protects engineering capacity for lasting improvements. Traditional operations may rely more heavily on manual processes, handoffs, and work that scales with service growth. Actual organizations vary.

### Answer 17

SRE is accountable for reliability outcomes and production risk. Platform engineering creates shared capabilities and interfaces that help teams build and operate services. A platform is a means, not proof of reliability.

### Answer 18

Both disciplines may engineer and operate complex production systems. Titles and boundaries vary. Production engineering may place different emphasis on system performance, infrastructure, architecture, or product-specific operation, while SRE is defined more explicitly by reliability objectives and operating principles.

### Answer 19

Valid models include embedded SRE, centralized SRE, consulting SRE, shared service SRE, and distributed reliability ownership. Selection depends on factors such as service criticality, organizational maturity, team size, architecture, authority, and operational load.

### Answer 20

Activity metrics show that work occurred, not that users received a more reliable service. Success evidence must show service outcomes, risk reduction, recovery capability, sustainable operations, and lasting engineering improvement.

---

# Part B: Applied Service and Risk Analysis

## 9. Part B Instructions

Use the service selected in Section 5.

Complete all five tasks. Each task is worth four points.

Support important decisions with evidence, assumptions, or clearly stated reasoning.

---

## 10. Task B1: Define the Service

Create a concise service definition that includes:

- Service name
- Purpose
- Primary users
- Dependent systems
- Valuable outcome
- Service boundary
- Major components
- Important dependencies
- Owning team
- Production support model
- Change mechanism
- Data handled
- Known constraints

Then answer:

1. Why is this a service rather than only a component?
2. Which internal components are outside the user's concern?
3. Which external conditions are part of the reliability promise?
4. Where could ownership become ambiguous?

### Scoring

| Points | Evidence |
| ---: | --- |
| 4 | Clear user-centered boundary, ownership, dependencies, data, and operating context |
| 3 | Mostly complete, with minor ambiguity |
| 2 | Component-centered or missing important operational context |
| 1 | Minimal description with unclear users or outcome |
| 0 | No usable service definition |

---

## 11. Task B2: Define a Critical User Journey

Document one Critical User Journey.

Include:

- User
- Intent
- Trigger
- Preconditions
- Start point
- Required steps
- Allowed branches
- End point
- Success criteria
- Failure criteria
- Timeliness requirement
- Correctness requirement
- Dependencies
- Owner
- Candidate reliability measurements

Explain why this journey is critical using at least two impact dimensions:

- User harm
- Revenue
- Safety
- Security
- Compliance
- Data integrity
- Operational continuity
- Downstream dependency impact

### Scoring

| Points | Evidence |
| ---: | --- |
| 4 | Bounded, measurable, outcome-centered journey with justified criticality |
| 3 | Useful journey with one missing or weak element |
| 2 | Mostly a feature, endpoint, or click path |
| 1 | Vague journey without measurable success |
| 0 | No Critical User Journey |

---

## 12. Task B3: Build a Reliability Risk Record

Write one risk statement in this form:

> Because of [condition or cause], there is a possibility that [service event] will occur, resulting in [user and business consequences].

Record:

- Risk owner
- Affected Critical User Journey
- Triggering conditions
- Existing controls
- Control limitations
- Likelihood estimate
- Impact estimate
- Uncertainty
- Residual risk
- Proposed treatment
- Decision authority
- Review date or trigger
- Evidence required for closure

Distinguish:

- Risk tolerance
- Current exposure
- Residual risk
- Formal acceptance, if required

### Scoring

| Points | Evidence |
| ---: | --- |
| 4 | Complete cause-event-consequence chain with uncertainty, authority, and treatment |
| 3 | Sound analysis with minor gaps |
| 2 | Technical risk with weak user or business connection |
| 1 | Unqualified severity label or unsupported score |
| 0 | No usable risk analysis |

---

## 13. Task B4: Analyze Reliability Properties

Evaluate the selected service across these properties:

| Property | Required analysis |
| --- | --- |
| Reliability | Intended function and defined operating conditions |
| Availability | Conditions under which users can use the function |
| Resilience | How disruption is absorbed, contained, and recovered from |
| Durability | How committed data remains correct and retrievable |
| Fault tolerance | Specific faults tolerated without losing required service |
| Disaster recovery | Severe disruptions that require extraordinary recovery |

For each property:

1. State the requirement.
2. Identify one failure mode.
3. Identify one control.
4. State how the control is verified.
5. State one remaining limitation.

### Scoring

| Points | Evidence |
| ---: | --- |
| 4 | All properties are distinguished and connected to testable controls |
| 3 | Mostly correct with minor gaps |
| 2 | Several concepts are confused or unsupported |
| 1 | Generic claims without a failure model |
| 0 | No meaningful analysis |

---

## 14. Task B5: Define Ownership and Responsibility

Create an ownership record that identifies:

- Accountable service-owning team
- SRE responsibility, if any
- Software engineering responsibility
- Platform responsibility
- Security responsibility
- Product or business responsibility
- Incident authority
- Change authority
- Risk-acceptance authority
- Escalation path
- After-hours support
- Dependency owners
- Transfer requirements
- Retirement owner

Then explain:

1. Whether accountability matches authority.
2. Which responsibilities are shared.
3. Which responsibilities must not be transferred to SRE.
4. How ownership will remain current during organizational change.

### Scoring

| Points | Evidence |
| ---: | --- |
| 4 | Clear accountability, authority, participation, escalation, and lifecycle ownership |
| 3 | Workable model with minor ambiguity |
| 2 | Roles exist, but authority or boundaries are unclear |
| 1 | SRE is treated as a general production support queue |
| 0 | No ownership model |

---

# Part C: Production Scenario Judgment

## 15. Part C Instructions

Complete all five scenarios.

Each scenario is worth five points.

For every scenario, write:

1. Known facts
2. Important unknowns
3. Working hypotheses
4. Immediate user-protection action
5. Evidence to collect
6. Decision owner
7. Verification method
8. Longer-term engineering response

Do not assume that the most visible technical symptom is the cause.

---

## 16. Scenario C1: Green Infrastructure, Failed Journey

An online retailer reports normal CPU, memory, pod health, load-balancer health, and database availability. No infrastructure alert is firing.

Customers report that payments succeed, but order confirmations do not appear. Some customers retry and may be charged more than once. Support tickets are increasing.

Answer:

1. What is the affected Critical User Journey?
2. Why do green component metrics not establish reliability?
3. Which correctness and timeliness signals matter?
4. What immediate action could reduce user harm?
5. What evidence would distinguish delayed processing from lost, rejected, or duplicated events?
6. How should incident severity be determined?
7. Which owners must participate?
8. What follow-up engineering work may be required?

### Strong Response Indicators

A strong answer:

- Defines the paid-order outcome, not only the payment endpoint
- Treats duplicate charging as a correctness and safety concern
- Investigates end-to-end state and event processing
- Considers idempotency, reconciliation, queue lag, schema failure, and confirmation latency
- Protects users before completing root-cause analysis
- Verifies both payment and durable order state

---

## 17. Scenario C2: Exhausted Error Budget

A customer-facing API has a 99.9 percent monthly availability SLO. The service has consumed its complete error budget halfway through the window.

A product team wants to launch a major feature before a public campaign. Tests pass, but the release changes a critical request path and rollback has not been rehearsed.

Answer:

1. What does the exhausted error budget indicate?
2. What does it not prove?
3. Which policy should govern the release decision?
4. Who should participate in the decision?
5. Which evidence could justify an exception?
6. Who may accept the residual business risk?
7. Which safeguards would reduce change risk?
8. What should happen after the decision?

### Strong Response Indicators

A strong answer:

- Uses the error budget as a decision mechanism
- Does not claim that all change must always stop
- Considers user impact, campaign risk, rollback, canarying, observability, and decision authority
- Requires documented exception and verification when policy permits one
- Avoids making SRE the sole owner of business risk acceptance

---

## 18. Scenario C3: The Toil Trap

An SRE team spends 65 percent of its time processing access requests, restarting a fragile service, clearing disk space, and preparing weekly availability reports manually.

Management proposes hiring three more SREs because the ticket queue is growing.

Answer:

1. Which work may be toil?
2. What evidence is required before classifying it?
3. Which work might be necessary overhead or valuable operational work?
4. Why might hiring alone fail?
5. Which work should be eliminated, redesigned, automated, or transferred?
6. Which risks could unsafe automation introduce?
7. How should the team protect engineering capacity?
8. Which measures would prove improvement?

### Strong Response Indicators

A strong answer:

- Classifies each work type separately
- Measures frequency, time, growth, interruption, and enduring value
- Finds causes before automating symptoms
- Challenges linear staffing as the only response
- Includes ownership, self-service, safety controls, and verification
- Measures reduced demand and restored engineering capacity

---

## 19. Scenario C4: Disaster Recovery Confidence

A service owner states that the service is disaster-ready because the database replicates to another region and nightly backups are enabled.

No one has restored a full backup in twelve months. The secondary region depends on the same identity tenant, deployment control plane, and secrets system as the primary region. The documented recovery time objective is two hours.

Answer:

1. Why is the disaster-readiness claim weak?
2. Which shared failure domains exist?
3. How could replication fail to protect data?
4. Which recovery dependencies must be tested?
5. How should RTO and RPO be validated?
6. What evidence would establish recoverability?
7. What is the role of people and access?
8. Which residual risks require an authorized decision?

### Strong Response Indicators

A strong answer:

- Separates replication, backup, failover, restoration, and disaster recovery
- Identifies common control-plane and credential dependencies
- Considers corruption, deletion, compromise, stale replicas, and inaccessible backups
- Requires timed restoration and service-level validation
- Tests return to normal operation, not only failover

---

## 20. Scenario C5: SRE Before Readiness

An organization has frequent incidents, no service catalog, inconsistent ownership, no defined Critical User Journeys, weak telemetry, no rollback standard, and several unsupported legacy services.

Leadership wants to create a central SRE team and make it accountable for all production reliability within 60 days.

Answer:

1. Does the organization need reliability improvement?
2. Is it ready for the proposed SRE model?
3. Which conditions would cause the team to become a support queue?
4. What should leadership establish first?
5. Which initial operating model is safer?
6. What responsibilities must remain with service teams?
7. Which readiness evidence should be collected?
8. What would justify expanding SRE engagement?

### Strong Response Indicators

A strong answer:

- Distinguishes need from readiness
- Rejects organization-wide accountability without authority or ownership
- Establishes service inventory, accountable owners, critical journeys, telemetry, incident process, and change safety
- Considers consulting or enablement before broad operational ownership
- Defines entry criteria for deeper SRE engagement

---

## 21. Part C Scoring Rubric

Score each scenario from zero to five.

| Points | Evidence |
| ---: | --- |
| 5 | Connects users, evidence, uncertainty, risk, authority, mitigation, verification, and lasting improvement |
| 4 | Strong judgment with one notable gap |
| 3 | Reasonable response, but limited systems or organizational analysis |
| 2 | Mostly reactive technical actions with weak user or risk reasoning |
| 1 | Tool-first, blame-focused, or unsupported response |
| 0 | No usable response or unsafe recommendation |

---

# Part D: Practical Reliability Portfolio

## 22. Part D Instructions

Create all six artifacts for the service selected in Section 5.

The portfolio is worth 25 points.

The artifacts should form one coherent service model. Do not create six unrelated examples.

---

## 23. Artifact D1: Service Brief

Create `artifacts/service-brief.md`.

Include:

- Service purpose
- Users and dependents
- Valuable outcomes
- Service boundary
- Criticality
- Major dependencies
- Data classification
- Change path
- Owners
- Support commitment
- Known risks
- Reliability assumptions
- Out-of-scope behavior

Maximum score: 4 points.

---

## 24. Artifact D2: Critical User Journey Record

Create `artifacts/critical-user-journey.md`.

Include:

- Journey name
- User
- Intended outcome
- Start and end boundaries
- Preconditions
- Required steps
- Dependencies
- Success criteria
- Failure criteria
- Correctness criteria
- Timeliness criteria
- Candidate SLIs
- Candidate SLO
- Measurement limitations
- Accountable owner

Maximum score: 4 points.

The SLO is a draft for reasoning purposes. A defensible draft with stated uncertainty is better than false precision.

---

## 25. Artifact D3: Reliability Risk Record

Create `artifacts/reliability-risk-record.md`.

Include at least three risks. At least one must involve:

- A technical failure mode
- A dependency or common-mode failure
- A human, process, or organizational condition

For every risk, record:

- Cause
- Event
- Consequence
- Existing controls
- Control evidence
- Uncertainty
- Residual exposure
- Treatment
- Owner
- Decision authority
- Review trigger

Maximum score: 5 points.

---

## 26. Artifact D4: Service Ownership Record

Create `artifacts/ownership-record.md`.

Include:

- Accountable team
- Technical lead
- Product or business owner
- On-call owner
- Incident commander authority
- Change and rollback authority
- Risk-acceptance authority
- Dependency owners
- Escalation paths
- Support hours
- Documentation owner
- Transfer criteria
- Retirement responsibility
- Last verification date

Maximum score: 4 points.

Do not place one person's private contact details in a public repository.

---

## 27. Artifact D5: Work Classification and Toil Review

Create `artifacts/work-classification.md`.

List at least eight recurring team activities.

For each activity, record:

- Description
- Frequency
- Time consumed
- Trigger
- Work classification
- Human judgment required
- Growth relationship
- Enduring value
- Risk if removed
- Proposed action
- Verification measure

Use these proposed actions where appropriate:

- Retain
- Simplify
- Eliminate
- Automate
- Make self-service
- Transfer with acceptance
- Redesign the service

Maximum score: 4 points.

---

## 28. Artifact D6: SRE Success Measurement Plan

Create `artifacts/measurement-plan.md`.

Define at least one measure in each category:

| Category | Example focus |
| --- | --- |
| User outcome | Critical journey success, latency, correctness |
| Reliability control | Error-budget consumption, recovery verification |
| Incident capability | Detection, mitigation, recovery, recurrence |
| Engineering improvement | Failure removed, risk reduced, safe change |
| Operational sustainability | Toil, interruptions, on-call load, burnout risk |
| Ownership | Coverage, authority, documentation freshness |

For every measure, document:

- Decision supported
- Definition
- Numerator and denominator, if applicable
- Data source
- Owner
- Frequency
- Segmentation
- Known limitations
- Threshold or review trigger
- Expected action

Maximum score: 4 points.

---

## 29. Part D Portfolio Rubric

| Criterion | Points |
| --- | ---: |
| Service brief is complete and user-centered | 4 |
| Critical User Journey is bounded and measurable | 4 |
| Risk record connects causes, events, consequences, controls, and authority | 5 |
| Ownership record aligns accountability with authority | 4 |
| Work classification uses the complete toil model | 4 |
| Measurement plan supports decisions and sustainability | 4 |
| **Total** | **25** |

### Portfolio Quality Test

Ask whether another engineer could use the portfolio to:

- Understand the service
- Identify what matters to users
- Recognize important risks
- Find accountable owners
- Make an initial incident decision
- Evaluate recurring operational work
- Understand how success will be measured

If the answer is no, revise the relevant artifact.

---

# Part E: Review, Defense, and Reflection

## 30. Part E Instructions

Complete a reviewer discussion or a written defense.

The defense is worth ten points.

The reviewer should challenge assumptions, not search for exact wording from Chapter 1.

---

## 31. Defense Questions

Answer at least ten of the following questions. Questions 1 through 5 are required.

1. Why did you define the service boundary this way?
2. Why is the selected user journey critical?
3. What evidence would cause you to change the proposed reliability target?
4. Who has authority to accept the largest residual risk?
5. Which assumption creates the greatest uncertainty?
6. Which green component metric could hide user failure?
7. Which failure can the service tolerate, and which can it only recover from?
8. What data-loss condition would violate the service promise?
9. Where could a shared dependency create correlated failure?
10. Which operational activity is most likely to become toil?
11. Which automation proposal would be unsafe without guardrails?
12. What responsibility should remain with the development team?
13. What should SRE refuse to own in this context?
14. Would a platform capability reduce reliability risk here?
15. Which SRE operating model fits this organization, and why?
16. What evidence shows that the organization is ready for SRE engagement?
17. Which metric in your plan could be gamed?
18. How could your proposed metric hide minority-user harm?
19. Which incident action requires verification before closure?
20. What would you change after receiving new production evidence?

---

## 32. Defense Scoring

| Criterion | Points |
| --- | ---: |
| Explains decisions clearly | 2 |
| States uncertainty and assumptions honestly | 2 |
| Connects technical choices to users and risk | 2 |
| Distinguishes responsibility from decision authority | 2 |
| Revises a position when stronger evidence appears | 2 |
| **Total** | **10** |

A learner does not lose credit merely for changing an answer. Updating a decision when new evidence appears demonstrates sound engineering judgment.

---

## 33. Reflection

Complete these prompts after the assessment:

1. Which foundation concept did you understand least before Chapter 1?
2. Which concept changed how you think about production?
3. Which answer relied on an unsupported assumption?
4. Which artifact would be useful to a real service team today?
5. Which artifact needs more production evidence?
6. Where did you confuse component health with service reliability?
7. Which risk did you initially underestimate?
8. Which responsibility boundary remains unclear?
9. Which operational activity deserves deeper toil analysis?
10. Which resource should you study next?
11. What will you verify in a real system?
12. What is your next reliability learning objective?

---

# Assessment Review

## 34. Reviewer Guidance

Review reasoning and evidence, not vocabulary alone.

A strong learner may use different words from the answer guide while demonstrating the correct concept.

The reviewer should:

- Ask for the user outcome
- Challenge hidden assumptions
- Request evidence for strong claims
- Test whether authority matches responsibility
- Look for missing failure domains
- Check whether data integrity is considered
- Challenge tool-first answers
- Check whether immediate mitigation protects users
- Require verification after action
- Distinguish local improvement from system improvement
- Examine human workload and sustainability
- Identify metrics that may encourage harmful behavior

The reviewer should not:

- Reward unnecessary jargon
- Require Google-specific structures in every organization
- Treat one vendor architecture as the correct answer
- Assume every service needs a dedicated SRE team
- Penalize a learner for documenting uncertainty
- Accept confident claims without evidence

---

## 35. Evidence Quality Levels

| Level | Description |
| --- | --- |
| 0 | No evidence or unsupported assertion |
| 1 | Personal opinion or generic claim |
| 2 | Plausible reasoning with explicit assumptions |
| 3 | Service-specific data, test result, incident evidence, or authoritative source |
| 4 | Multiple consistent forms of evidence with limitations documented |

Not every answer needs Level 4 evidence. Higher-risk decisions require stronger evidence.

---

## 36. Common Weak Submission Patterns

### Tool Substitution

Weak response:

> We will install a monitoring platform to make the service reliable.

Problem:

- The response does not define the user outcome, indicator, decision, or action.

### Availability Substitution

Weak response:

> The server was running, so the service was available.

Problem:

- A running server does not prove that users could complete the required journey.

### Automation Substitution

Weak response:

> Automate every manual task.

Problem:

- The response ignores judgment, risk, demand elimination, failure modes, and automation maintenance.

### Ownership Without Authority

Weak response:

> SRE owns uptime, but product teams decide what ships.

Problem:

- Accountability and decision authority are misaligned.

### Metric Without Decision

Weak response:

> Track the number of dashboards and alerts.

Problem:

- Activity does not establish user reliability or risk reduction.

### Recovery Without Verification

Weak response:

> Fail over to the backup region.

Problem:

- The response does not validate service behavior, data correctness, dependencies, or safe failback.

---

## 37. Remediation Rules

A learner who does not meet the completion standard should not repeat the complete chapter automatically.

Use the results to select focused remediation.

| Weak area | Review sections | Required remediation |
| --- | --- | --- |
| Definition and mindset | 1 to 3 | Rewrite the SRE definition and reasoning loop using a real service |
| Product and business context | 4, 5, 10, 11 | Rebuild the CUJ and risk record |
| Reliability properties | 6 and 7 | Create a failure-model comparison and recovery test plan |
| Ownership | 8, 9, 18, 19 | Revise accountability, authority, and escalation boundaries |
| Work and toil | 12 and 13 | Reclassify recurring work using measured evidence |
| Discipline boundaries | 14 to 17 | Produce a responsibility comparison based on outcomes |
| Organizational adoption | 19 to 22 | Reassess need, readiness, and operating model |
| Success measurement | 23 | Replace activity metrics with decision-linked outcome measures |
| Production judgment | 24 | Analyze two additional scenarios |
| Practical capability | 25 | Repeat the weak artifact with reviewer feedback |
| Resource use | 26 | Replace weak sources and add verification notes |

Repeat only the failed assessment parts after completing remediation.

---

## 38. Assessment Integrity

This assessment may be completed with assistance, but the learner must be able to explain every submitted decision.

Acceptable assistance includes:

- Reviewing Chapter 1
- Reading authoritative sources
- Asking an engineer for feedback
- Using a template
- Using software to check spelling or formatting
- Discussing alternative approaches

Unacceptable completion includes:

- Submitting an artifact the learner cannot explain
- Copying another service's risk record without adapting it
- Inventing production evidence
- Hiding uncertainty
- Claiming tests that were not performed
- Including confidential or restricted information without permission

If generative AI is used, record:

- What it helped produce
- Which claims were independently verified
- Which decisions were made by the learner
- Which errors or unsupported assumptions were corrected

The learner remains responsible for accuracy.

---

## 39. Completion Record Template

```markdown
# SRE Foundation Completion Record

## Learner

- Name or identifier:
- Assessment date:
- Reviewer:
- Selected service:

## Scores

| Part | Score | Maximum |
| --- | ---: | ---: |
| A: Foundation knowledge |  | 20 |
| B: Applied analysis |  | 20 |
| C: Production scenarios |  | 25 |
| D: Practical portfolio |  | 25 |
| E: Defense and reflection |  | 10 |
| Total |  | 100 |

## Competency Gates

- [ ] Part A minimum met
- [ ] Part B minimum met
- [ ] Part C minimum met
- [ ] Part D minimum met
- [ ] Part E minimum met
- [ ] No automatic-review condition remains

## Result

- [ ] Distinction
- [ ] Proficient
- [ ] Developing
- [ ] Not yet complete

## Strongest Evidence


## Gaps Requiring Remediation


## Required Follow-Up


## Reviewer Decision

- [ ] Chapter 1 complete
- [ ] Revision required

## Review Date


## Notes
```

---

## 40. Chapter 1 Coverage Matrix

Use this matrix to confirm that the assessment covers every section.

| Chapter 1 section | Primary assessment evidence |
| --- | --- |
| 01. What Is SRE | Part A, Questions 1 and 2 |
| 02. History and Evolution of SRE | Part A, Question 1; Part E defense |
| 03. The SRE Mindset | Parts B and C reasoning method |
| 04. Reliability as a Product Feature | Part A, Question 3; Task B2 |
| 05. Reliability and Business Risk | Part A, Question 4; Task B3 |
| 06. Reliability, Availability, Resilience, and Durability | Part A, Questions 5 to 7; Task B4 |
| 07. Fault Tolerance and Disaster Recovery | Part A, Question 8; Scenario C4 |
| 08. Production Responsibility | Part A, Question 9; Task B5 |
| 09. Service Ownership | Part A, Question 10; Artifact D4 |
| 10. Critical User Journeys | Part A, Question 11; Task B2 |
| 11. Risk Tolerance | Part A, Question 12; Task B3 |
| 12. Engineering Work and Operational Work | Part A, Question 13; Artifact D5 |
| 13. Toil | Part A, Question 14; Scenario C3 |
| 14. SRE and DevOps | Part A, Question 15 |
| 15. SRE and Traditional Operations | Part A, Question 16 |
| 16. SRE and Platform Engineering | Part A, Question 17 |
| 17. SRE and Production Engineering | Part A, Question 18 |
| 18. SRE Responsibilities | Task B5; Artifact D4 |
| 19. SRE Operating Models | Part A, Question 19; Scenario C5 |
| 20. When an Organization Needs SRE | Scenario C5 |
| 21. When an Organization Is Not Ready for SRE | Scenario C5 |
| 22. Common SRE Misunderstandings | Automatic review conditions and weak patterns |
| 23. Measuring SRE Success | Part A, Question 20; Artifact D6 |
| 24. SRE Foundation Production Scenarios | Part C |
| 25. SRE Foundation Practical Exercises | Part D |
| 26. SRE Foundation Resources | Evidence notes and source verification |

---

## 41. Final Completion Checklist

### Knowledge

- [ ] I can define SRE without naming tools.
- [ ] I can explain the SRE mindset.
- [ ] I can distinguish the major reliability properties.
- [ ] I can distinguish SRE from adjacent disciplines.
- [ ] I can explain toil precisely.

### Service Reasoning

- [ ] I can define a service around a valuable outcome.
- [ ] I can identify a Critical User Journey.
- [ ] I can connect component failure to user and business impact.
- [ ] I can state risk and uncertainty clearly.
- [ ] I can identify accountable owners and decision authorities.

### Production Judgment

- [ ] I separate facts, hypotheses, unknowns, and decisions.
- [ ] I protect users before pursuing complete diagnosis.
- [ ] I consider correctness, latency, availability, and data integrity.
- [ ] I design for verification and rollback.
- [ ] I treat incidents as sources of learning.

### Organizational Judgment

- [ ] I can identify whether an organization needs reliability improvement.
- [ ] I can evaluate whether the organization is ready for SRE.
- [ ] I can select an operating model based on context.
- [ ] I do not transfer all production responsibility to SRE.
- [ ] I consider sustainable on-call and engineering capacity.

### Evidence

- [ ] My important claims have evidence or stated assumptions.
- [ ] My measures support decisions.
- [ ] My resources are authoritative and verified.
- [ ] My artifacts can be used by another engineer.
- [ ] I documented limitations and unresolved questions.

---

## 42. Chapter 1 Completion Standard

Chapter 1 is complete when the learner can move from this question:

> Which SRE tools should we use?

To these questions:

- Which service outcome must be protected?
- Who depends on it?
- What level of failure is tolerable?
- How will success and failure be measured?
- What can fail?
- How will the service behave during failure?
- Who owns the outcome?
- Who has authority to act?
- Which operational work is sustainable?
- Which work should be engineered out?
- What evidence supports the decision?
- How will the result be verified?
- What will the organization learn?

That change in reasoning is the central outcome of SRE Foundations.

---

## 43. Key Takeaways

- Foundation competence requires explanation, application, analysis, judgment, and creation.
- Memorized definitions do not prove production readiness.
- Reliability begins with users, service outcomes, and explicit risk.
- Infrastructure health is supporting evidence, not the final outcome.
- Ownership requires knowledge, capacity, accountability, and authority.
- Toil must be measured and analyzed before it is automated.
- SRE operating models must fit organizational maturity and service risk.
- Success measures must support decisions and show lasting improvement.
- Production actions require verification.
- Strong engineers state uncertainty and revise decisions when evidence changes.

---

## 44. Chapter 1 Sections

- [SRE Foundations](./README.md)
- [What Is SRE?](./01-What-Is-SRE.md)
- [History and Evolution of SRE](./02-History-and-Evolution-of-SRE.md)
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
- [SRE Foundation Practical Exercises](./25-SRE-Foundation-Practical-Exercises.md)
- [SRE Foundation Resources](./26-SRE-Foundation-Resources.md)

---

## Chapter 1 Complete

You have reached the end of `01-SRE-Foundations`.

The next stage should deepen the mechanisms introduced here, including service-level indicators, service-level objectives, error budgets, measurement windows, and reliability decision policies.

Do not continue because every answer was easy. Continue when you can identify your weak areas, explain your assumptions, and use evidence to improve your decisions.

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> SRE foundations are complete when reliability language becomes production judgment, and production judgment produces safer, measurable, and sustainable service outcomes.
