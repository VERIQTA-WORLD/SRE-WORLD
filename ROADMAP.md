# SRE World Roadmap

> A production-focused roadmap for engineers who want to measure, operate, protect, restore, and improve the reliability of modern services.

## Purpose

This roadmap develops Site Reliability Engineering capability through reliability principles, production responsibility, operational decision-making, failure analysis, and practical engineering work.

It is not a beginner DevOps tool roadmap. It does not prescribe a sequence of products to install or certifications to collect. Technologies appear only where they help solve a defined reliability problem.

The roadmap progresses through 12 phases:

1. Understand reliability
2. Define and measure reliability
3. Build production visibility
4. Operate production services
5. Troubleshoot production systems
6. Learn from failure
7. Reduce operational risk
8. Engineer for scale
9. Understand distributed failure
10. Build resilient systems
11. Apply reliability by domain
12. Lead reliability programs

---

## How to Use This Roadmap

The phases are ordered intentionally, but the roadmap is not a rigid course.

- Start with Phases 1 and 2 if SRE concepts are new to you.
- Start with Phase 3 or 4 if you already operate production services.
- Use Phases 5 through 10 to deepen production engineering capability.
- Use Phase 11 to apply the principles to your operating environment.
- Use Phase 12 when you are responsible for reliability across teams or services.
- Complete the practical work. Reading alone does not build operational judgment.
- Record assumptions, evidence, decisions, risks, and verification steps in every exercise.
- Return to earlier phases when incidents expose gaps in service ownership, measurement, alerting, or readiness.

### Recommended Evidence of Completion

Maintain a reliability portfolio containing:

- One service ownership record
- One critical user journey map
- Three SLI specifications
- Two complete SLOs
- One error budget policy
- One burn-rate calculation
- One service health dashboard design
- Five reviewed alerts
- One on-call handover
- Two incident timelines
- Two troubleshooting investigations
- One blameless postmortem
- One toil inventory
- One production readiness review
- One capacity model
- One load-test report
- One failure-mode analysis
- One resilience experiment
- One disaster recovery exercise
- One reliability improvement proposal

---

# Phase 1: Understand Reliability

## Objective

Build a precise understanding of Site Reliability Engineering, production responsibility, service ownership, and reliability as a product and business decision.

## Study

1. Site Reliability Engineering foundations
2. What SRE is and what it is not
3. Reliability, availability, resilience, and durability
4. Reliability as a product feature
5. Reliability as a business decision
6. Service ownership
7. Critical user journeys
8. Risk tolerance
9. Production responsibility
10. Engineering work versus operational work
11. SRE versus DevOps
12. SRE versus traditional operations
13. SRE versus platform engineering
14. SRE versus production engineering
15. Centralized, embedded, and consulting SRE models

## Questions You Should Be Able to Answer

- What does reliable mean for a specific service and its users?
- Why is maximum possible availability not always the correct target?
- Who owns a service during normal operation and during an incident?
- Which user journeys matter most to the business?
- What is the difference between a resilient system and an available system?
- Which work requires engineering, and which work is repetitive operational activity?
- When is an SRE team appropriate for an organization?

## Practical Work

- Select one production-style service and write its purpose, users, owner, dependencies, and criticality.
- Identify three critical user journeys.
- Describe what failure looks like from the user’s perspective.
- Classify the service as critical, important, or non-critical and justify the decision.
- Compare the business cost of downtime with the engineering cost of higher reliability.
- Write a one-page SRE engagement proposal for the service.

## Production Scenario

A business demands 99.999 percent availability for an internal reporting service. The service is used only during business hours, has no defined owner, and has never measured user-visible availability. Decide what questions must be answered before accepting the target.

## Completion Outcome

You can explain SRE without reducing it to monitoring, automation, or tool ownership. You can connect service reliability to users, business outcomes, ownership, and risk.

## Repository Sections

- [SRE Foundations](./01-SRE-Foundations/)
- [Service Ownership](./02-Service-Ownership/)
- [SRE Organizations and Culture](./26-SRE-Organizations-and-Culture/)

---

# Phase 2: Define and Measure Reliability

## Objective

Translate user expectations into measurable indicators, objectives, error budgets, and operational policies.

## Study

16. Service Level Indicators
17. Service Level Objectives
18. Service Level Agreements
19. Critical user journeys and SLI selection
20. Good events and valid events
21. Request-based and window-based measurement
22. Availability, latency, correctness, freshness, durability, and coverage SLIs
23. Measurement windows
24. Percentiles and tail latency
25. Composite and dependency SLOs
26. SLOs for APIs and interactive services
27. SLOs for batch and asynchronous systems
28. SLOs for data pipelines and internal platforms
29. Error budget calculation
30. Error budget consumption
31. Burn rates
32. Multi-window burn-rate alerting
33. Error budget policies
34. Availability mathematics
35. Reliability reporting

## Questions You Should Be Able to Answer

- Does the SLI represent what users actually experience?
- Which events belong in the denominator?
- What does a 99.9 percent objective permit during a measurement window?
- How quickly is the service consuming its error budget?
- What action should follow budget exhaustion?
- When does an SLA create a contractual consequence?
- Can a service meet its SLO while an important customer journey still fails?

## Practical Work

- Write three SLI specifications for availability, latency, and correctness.
- Calculate the allowed failure for 99 percent, 99.9 percent, 99.95 percent, and 99.99 percent objectives.
- Design a 28-day SLO for a user-facing API.
- Calculate the remaining error budget from sample service data.
- Compare fast-burn and slow-burn conditions.
- Draft an error budget policy defining release, escalation, and improvement actions.
- Review a misleading infrastructure metric and replace it with a user-centered indicator.

## Production Scenario

An API reports 99.95 percent server availability, but payment completion has fallen to 97 percent because a dependency returns invalid responses. Determine whether the current SLI is sufficient and redesign the measurement.

## Completion Outcome

You can design defensible SLIs and SLOs, calculate error budgets, recognize misleading reliability measurements, and connect measurement to operational decisions.

## Repository Sections

- [SLIs, SLOs, and SLAs](./03-SLIs-SLOs-and-SLAs/)
- [Error Budgets](./04-Error-Budgets/)
- [Reliability Measurement](./05-Reliability-Measurement/)
- [SLO Examples](./SLO-Examples/)

---

# Phase 3: Build Production Visibility

## Objective

Design telemetry, dashboards, and alerts that reveal user impact, service behavior, and actionable production risk.

## Study

36. Monitoring versus observability
37. Metrics, logs, traces, and events
38. Telemetry design
39. Golden signals
40. RED method
41. USE method
42. Structured logging
43. Trace context and correlation identifiers
44. Metric cardinality
45. Sampling and retention
46. Instrumentation quality
47. Service health dashboards
48. Business-level observability
49. Symptom-based and cause-based alerting
50. SLO-based alerting
51. Paging versus ticketing
52. Alert severity and routing
53. Alert grouping, deduplication, and inhibition
54. Alert fatigue
55. Alert testing and lifecycle management

## Questions You Should Be Able to Answer

- What user-impact question does each signal answer?
- Can an engineer move from an alert to relevant evidence quickly?
- Is the alert actionable, urgent, and owned?
- Should the condition page someone, create a ticket, or remain on a dashboard?
- What happens when telemetry is missing?
- Can the monitoring system distinguish full failure from partial degradation?
- Does the dashboard support diagnosis or merely display activity?

## Practical Work

- Design a telemetry plan for one service.
- Map metrics, logs, traces, and events to three critical user journeys.
- Design a service health dashboard on paper before choosing a product.
- Review five sample alerts and classify each as page, ticket, dashboard, or remove.
- Write an SLO-based alert using fast-burn and slow-burn conditions.
- Create an alert runbook containing impact, validation, mitigation, escalation, and verification.
- Identify cardinality, privacy, retention, and cost risks in a telemetry design.

## Production Scenario

All infrastructure dashboards are green, but users report that checkout requests remain pending for several minutes. Determine what telemetry is missing and how the alerting strategy should change.

## Completion Outcome

You can design production visibility around service behavior and user impact. You can separate useful telemetry from noise and distinguish an informative signal from a page-worthy condition.

## Repository Sections

- [Observability Engineering](./06-Observability-Engineering/)
- [Alerting Engineering](./07-Alerting-Engineering/)
- [Runbooks](./Runbooks/)

---

# Phase 4: Operate Production Services

## Objective

Develop the judgment, process, communication, and coordination required to operate services and respond to incidents safely.

## Study

56. On-call readiness
57. Primary and secondary rotations
58. Escalation paths
59. On-call handover
60. Shadow rotations and training
61. Sustainable on-call
62. Page acknowledgement and triage
63. Incident declaration
64. Incident severity
65. Incident command structure
66. Incident commander responsibilities
67. Operations and communications roles
68. Decision logs and incident timelines
69. Internal and external communication
70. Containment, mitigation, and recovery
71. Mitigation versus resolution
72. Recovery verification
73. Multiple and long-running incidents
74. Third-party incidents
75. Incident closure and handover

## Questions You Should Be Able to Answer

- When should an engineer declare an incident?
- Who has decision authority during the response?
- What is the immediate customer impact?
- Which mitigation has the lowest additional risk?
- What information belongs in a stakeholder update?
- How do you verify that recovery is real and sustained?
- When should the incident remain open after metrics recover?

## Practical Work

- Create an on-call readiness checklist.
- Draft a weekly handover containing active incidents, risky changes, known issues, and escalation contacts.
- Build a severity matrix based on customer and business impact.
- Run a tabletop incident with an incident commander, operations lead, and communications lead.
- Produce three incident updates for technical, executive, and customer audiences.
- Create a decision log showing time, evidence, decision, owner, and result.
- Write recovery criteria before simulating service restoration.

## Production Scenario

A critical service is failing intermittently. Rolling back may restore availability but could create data inconsistency. Customer impact is increasing, and two teams disagree about the cause. Establish command, decide how to evaluate mitigation options, and communicate the risk.

## Completion Outcome

You can participate in an on-call rotation, declare and structure an incident, coordinate response work, communicate clearly, and verify recovery without confusing temporary metric improvement with resolution.

## Repository Sections

- [On-Call Engineering](./08-On-Call-Engineering/)
- [Incident Management](./09-Incident-Management/)
- [Playbooks](./Playbooks/)
- [Incident Library](./Incident-Library/)

---

# Phase 5: Troubleshoot Production Systems

## Objective

Investigate complex production failures through evidence, timelines, hypotheses, safe testing, and customer-impact reduction.

## Study

76. Establishing impact and scope
77. Timeline construction
78. Recent-change analysis
79. Evidence collection
80. Hypothesis-driven debugging
81. Differential diagnosis
82. Dependency analysis
83. Resource saturation
84. Queue buildup and connection exhaustion
85. CPU, memory, disk, and I/O failure
86. DNS, routing, TLS, and timeout failure
87. Retry amplification
88. Partial and cascading failure
89. Intermittent and gray failure
90. Configuration drift
91. Safe production testing
92. Mitigation under uncertainty
93. Evidence preservation
94. Recovery verification
95. Unknown and misleading signals

## Investigation Method

```text
Understand impact
       ↓
Establish scope and timeline
       ↓
Identify recent changes and dependencies
       ↓
Collect evidence
       ↓
Form and rank hypotheses
       ↓
Test safely
       ↓
Reduce customer impact
       ↓
Verify sustained recovery
       ↓
Preserve evidence and follow-up work
```

## Questions You Should Be Able to Answer

- What is known, assumed, and still unknown?
- When did impact begin, and what changed before it?
- Is the failure global, regional, tenant-specific, or request-specific?
- Which observation would disprove the leading hypothesis?
- Could the diagnostic action increase the blast radius?
- Has the customer journey recovered, not only the component metric?

## Practical Work

- Investigate a latency increase where CPU remains normal.
- Investigate an error spike after a deployment.
- Trace a customer request across multiple dependencies.
- Build a hypothesis table containing evidence for, evidence against, risk, and next test.
- Separate mitigation steps from root-cause investigation.
- Write explicit recovery checks for an intermittent failure.
- Document one failed hypothesis and explain why it was reasonable.

## Production Scenario

Only customers in one region experience timeouts. Application error rates appear normal, database capacity is healthy, and no deployment occurred. Construct the investigation without assuming the application is the cause.

## Completion Outcome

You can investigate production failure methodically, avoid premature conclusions, test hypotheses safely, and prioritize customer recovery while preserving evidence for deeper analysis.

## Repository Sections

- [Troubleshooting and Debugging](./10-Troubleshooting-and-Debugging/)
- [Production Failure Library](./Production-Failure-Library/)
- [Failure Labs](./Failure-Labs/)

---

# Phase 6: Learn From Failure

## Objective

Convert incidents and near misses into durable improvements without reducing complex system failure to blame or a single root cause.

## Study

96. Blameless postmortems
97. Accountability without blame
98. Timeline reconstruction
99. Contributing conditions
100. Trigger versus cause
101. Root cause analysis limitations
102. Five Whys limitations
103. Causal graphs
104. Human and organizational factors
105. Detection, response, and recovery gaps
106. Corrective and preventive actions
107. Action ownership and prioritization
108. Near-miss analysis
109. Incident recurrence
110. Reliability debt
111. Learning reviews
112. Sharing lessons across teams
113. Measuring postmortem effectiveness

## Questions You Should Be Able to Answer

- Why did the system permit this failure to reach users?
- Which conditions made the incident more likely or more damaging?
- Why did each action make sense to the people involved at the time?
- Which controls failed, were missing, or worked successfully?
- Does each corrective action reduce a demonstrated risk?
- Who owns the action, and how will completion be verified?
- What can other teams learn from this event?

## Practical Work

- Reconstruct an incident timeline from incomplete evidence.
- Write a blameless postmortem.
- Replace a simplistic root cause with a set of contributing conditions.
- Classify corrective actions as detect, prevent, contain, recover, or learn.
- Reject weak actions such as “be more careful” and “add monitoring” without specifications.
- Review a public incident and identify transferable lessons.
- Perform a near-miss analysis for a failure that did not reach customers.

## Production Scenario

An engineer applied a valid configuration change that caused a region-wide outage. The change passed review and automated checks. Analyze why the system depended on the engineer avoiding an error that the organization’s controls did not detect.

## Completion Outcome

You can produce evidence-based postmortems, identify interacting technical and organizational conditions, and design corrective work that measurably reduces recurrence or impact.

## Repository Sections

- [Postmortems and Learning](./11-Postmortems-and-Learning/)
- [SRE Case Studies](./29-SRE-Case-Studies/)
- [Production Incidents](./30-Production-Incidents/)
- [Incident Library](./Incident-Library/)

---

# Phase 7: Reduce Operational Risk

## Objective

Reduce repetitive work, control change risk, automate safely, and verify that services are ready for production ownership.

## Study

114. Toil identification
115. Toil measurement
116. Toil budgets
117. Automation opportunities
118. Automation risk
119. Idempotency and bounded execution
120. Guardrails, approvals, and kill switches
121. Automated remediation
122. Remediation loops and automation failure
123. Change as a reliability risk
124. Change risk classification
125. Small and reversible changes
126. Progressive delivery
127. Canary analysis
128. Rollback versus roll-forward
129. Feature flags and controlled exposure
130. Configuration and schema-change safety
131. Production readiness reviews
132. Operational readiness reviews
133. Launch criteria and reliability sign-off

## Questions You Should Be Able to Answer

- Does this work qualify as toil?
- Is automation safer than the manual process it replaces?
- What prevents automation from acting repeatedly or too broadly?
- Can a production change be limited, observed, stopped, and reversed?
- Is rollback safe for application, configuration, and data changes?
- Does the service have ownership, SLOs, alerts, runbooks, capacity, and recovery plans?
- Which risks must block launch?

## Practical Work

- Create a toil inventory and quantify frequency, duration, growth, and interruption cost.
- Prioritize one automation opportunity using benefit, complexity, and risk.
- Design an automated remediation with rate limits, success criteria, and a kill switch.
- Classify five changes by blast radius and reversibility.
- Write rollback and roll-forward criteria for a database-backed service.
- Conduct a production readiness review.
- Produce a launch decision with accepted risks, owners, and deadlines.

## Production Scenario

A team wants to automate restarts whenever memory crosses a threshold. Restarts temporarily recover the service but erase evidence and may create a dependency overload. Decide whether automation is appropriate and define necessary safeguards.

## Completion Outcome

You can distinguish valuable engineering from toil, design bounded automation, reduce change risk, and make evidence-based production readiness decisions.

## Repository Sections

- [Toil and Automation](./12-Toil-and-Automation/)
- [Production Readiness](./13-Production-Readiness/)
- [Change and Release Reliability](./14-Change-and-Release-Reliability/)
- [Templates](./Templates/)
- [Checklists](./Checklists/)

---

# Phase 8: Engineer for Scale

## Objective

Predict demand, find limits, validate performance, and design controlled behavior when capacity becomes constrained.

## Study

134. Demand forecasting
135. Capacity models
136. Organic, seasonal, and event-driven growth
137. Peak-to-average ratios
138. Capacity headroom
139. Failover capacity
140. Bottleneck analysis
141. Utilization and saturation
142. Latency distributions and tail latency
143. Throughput and concurrency
144. Queueing theory
145. Little’s Law
146. Load, stress, spike, and soak testing
147. Coordinated omission
148. Performance regression
149. Load shedding
150. Graceful degradation
151. Cost and reliability tradeoffs

## Questions You Should Be Able to Answer

- What resource becomes limiting first?
- How much usable headroom remains under normal and failover conditions?
- Does the test reproduce production traffic shape and dependency behavior?
- What happens when demand exceeds capacity?
- Which work should the system reject first?
- Can the service preserve critical journeys during overload?
- What capacity must exist before a regional failover?

## Practical Work

- Build a simple capacity model from traffic, concurrency, latency, and resource limits.
- Forecast demand under normal growth and a major event.
- Define warning, action, and exhaustion thresholds.
- Design load, stress, spike, and soak tests for one service.
- Identify coordinated omission in a misleading test result.
- Create a load-shedding policy based on request priority.
- Define graceful degradation for three non-critical features.

## Production Scenario

A service has enough capacity for normal regional traffic, but its secondary region cannot absorb full failover demand. A major traffic event begins in 48 hours. Decide which mitigations and business tradeoffs should be considered.

## Completion Outcome

You can model service capacity, design realistic tests, identify bottlenecks, and plan controlled behavior under overload instead of relying only on reactive scaling.

## Repository Sections

- [Capacity Planning](./15-Capacity-Planning/)
- [Performance and Load](./16-Performance-and-Load/)
- [Worksheets](./Worksheets/)

---

# Phase 9: Understand Distributed Failure

## Objective

Understand how local failures, delays, retries, coordination, and dependencies produce system-wide instability.

## Study

152. Partial failure
153. Timeouts and deadlines
154. Retries
155. Exponential backoff and jitter
156. Retry budgets
157. Idempotency and deduplication
158. Circuit breakers
159. Bulkheads
160. Backpressure
161. Rate limiting
162. Request hedging
163. Queue buffering
164. Poison messages and dead-letter handling
165. Replication and consistency models
166. Quorums and consensus
167. Leader election
168. Network partitions and split brain
169. Thundering herds and cache stampedes
170. Cascading failure
171. Metastable failure
172. Clock and ordering problems

## Questions You Should Be Able to Answer

- Is a retry safe, useful, and bounded?
- Which layer owns the timeout?
- Can duplicate execution corrupt state?
- What happens when every client retries simultaneously?
- How does the system behave during a network partition?
- Which consistency guarantee does the user journey require?
- Can the system remain trapped in failure after the original trigger disappears?

## Practical Work

- Design a timeout budget across three dependent services.
- Compare fixed retries with exponential backoff and jitter.
- Create a retry budget and define exhaustion behavior.
- Make a non-idempotent operation safe against duplicate requests.
- Diagram a cascading failure caused by retry amplification.
- Analyze a queue containing poison messages.
- Explain how a system can enter and remain in a metastable state.

## Production Scenario

A dependency slows down but does not fail completely. Client timeouts, retries, thread exhaustion, and queue buildup spread the degradation across otherwise healthy services. Identify the feedback loops and propose containment controls.

## Completion Outcome

You can reason about distributed failure, recognize dangerous feedback loops, and apply patterns that bound failure without treating them as universal solutions.

## Repository Sections

- [Distributed Systems Reliability](./17-Distributed-Systems-Reliability/)
- [Reliability Patterns](./Reliability-Patterns/)
- [Decision Records](./Decision-Records/)

---

# Phase 10: Build Resilient Systems

## Objective

Design systems and recovery processes that contain disruption, preserve critical functions, and recover within defined business requirements.

## Study

173. Failure domains
174. Fault isolation
175. Blast-radius reduction
176. Redundancy and diversity
177. Common-mode failure
178. Static stability
179. Cell-based architecture
180. Graceful degradation
181. Chaos engineering
182. Game days
183. Fault injection
184. Safe experimentation
185. Business continuity versus disaster recovery
186. Recovery Time Objective
187. Recovery Point Objective
188. Backup and restore
189. Active-active and active-passive recovery
190. Regional failover and failback
191. Dependency recovery order
192. Recovery testing

## Questions You Should Be Able to Answer

- Which failures share the same failure domain?
- Can redundancy fail through a shared dependency or configuration?
- How far can failure spread before isolation stops it?
- Can the system remain stable without immediate control-plane action?
- What critical function must remain available during degradation?
- Have backups been restored successfully under realistic conditions?
- Can the organization meet its stated RTO and RPO?

## Practical Work

- Create a failure-mode and effects analysis for one service.
- Map shared dependencies and common-mode risks.
- Propose blast-radius boundaries.
- Design one safe fault-injection experiment.
- Run a tabletop game day.
- Write a regional failover and failback plan.
- Test a backup restoration and record actual RTO and RPO performance.

## Production Scenario

A primary region becomes unavailable. The recovery environment exists, but credentials, DNS changes, dependency capacity, and the latest backup have never been tested together. Determine whether failover should proceed and how risk should be controlled.

## Completion Outcome

You can analyze failure domains, design containment, conduct safe resilience experiments, and validate recovery capability instead of trusting untested redundancy.

## Repository Sections

- [Resilience Engineering](./18-Resilience-Engineering/)
- [Disaster Recovery](./19-Disaster-Recovery/)
- [Reliability Architecture](./25-Reliability-Architecture/)
- [Failure Labs](./Failure-Labs/)

---

# Phase 11: Apply Reliability by Domain

## Objective

Apply SRE principles to specific production domains while preserving a consistent focus on user impact, failure behavior, and recovery.

## Study

193. Data reliability
194. Database connection, replication, locking, and storage failure
195. Network reliability
196. DNS, routing, load balancing, and TLS failure
197. Cloud reliability
198. Region, zone, identity, quota, and control-plane failure
199. Kubernetes reliability
200. Control plane, node, scheduling, networking, and stateful workload failure
201. Messaging and queue reliability
202. Storage reliability
203. Batch and data-pipeline reliability
204. Security and reliability interaction
205. Third-party dependency reliability
206. Domain-specific SLI and SLO design

## Domain Study Method

For every domain, answer:

1. What user journey depends on it?
2. What are its main failure modes?
3. What signals reveal user impact?
4. What capacity or quota can become exhausted?
5. What dependencies can create common-mode failure?
6. What changes carry the greatest risk?
7. How is failure contained?
8. How is service restored?
9. How is recovery verified?
10. Which risks remain accepted?

## Practical Work

- Choose two domains relevant to your environment.
- Build a dependency and failure map for each.
- Define domain-specific SLIs and operational signals.
- Investigate one realistic failure scenario per domain.
- Create a runbook for a high-impact failure.
- Design a recovery test.
- Compare a product-specific response with a transferable reliability principle.

## Production Scenario

A managed platform reports healthy infrastructure, but application requests fail because of quota exhaustion, DNS caching, and an unavailable third-party identity service. Separate the provider, platform, application, and dependency responsibilities.

## Completion Outcome

You can apply consistent reliability reasoning across different technologies without reducing SRE to product administration or general tool tutorials.

## Repository Sections

- [Data Reliability](./20-Data-Reliability/)
- [Network Reliability](./21-Network-Reliability/)
- [Cloud Reliability](./22-Cloud-Reliability/)
- [Kubernetes Reliability](./23-Kubernetes-Reliability/)
- [Security and Reliability](./24-Security-and-Reliability/)

---

# Phase 12: Lead Reliability Programs

## Objective

Move from operating individual services to improving reliability across teams, portfolios, and organizations.

## Study

207. SRE operating models
208. Centralized, embedded, platform, and consulting SRE
209. SRE engagement and disengagement models
210. Service adoption criteria
211. Sustainable on-call design
212. Staffing and operational load
213. Reliability maturity models
214. Reliability governance
215. Organization-wide SLO programs
216. Error budget governance
217. Reliability reviews and scorecards
218. Reliability investment prioritization
219. Reliability debt management
220. Executive reporting
221. Stakeholder negotiation
222. Reliability strategy and roadmaps
223. Cross-team incident learning
224. SRE leadership and mentoring
225. Measuring SRE program effectiveness

## Questions You Should Be Able to Answer

- Which services should receive SRE support?
- Is the team spending enough time on engineering work?
- Is the on-call rotation sustainable?
- How should reliability investment compete with feature delivery?
- Which reliability risks require executive attention?
- Are teams using SLOs to make decisions or only to produce reports?
- Has the SRE program improved customer outcomes and operational health?

## Practical Work

- Assess an organization using a reliability maturity model.
- Design an SRE engagement model for three service tiers.
- Build a reliability scorecard without collapsing everything into one misleading number.
- Create an error budget governance process.
- Prioritize a portfolio of reliability risks.
- Write an executive reliability report.
- Create a 12-month reliability strategy with measurable outcomes.

## Production Scenario

Several teams want SRE support, but the SRE group has limited capacity. Some services lack ownership and operational readiness, while one revenue-critical service has repeated incidents. Define adoption criteria, engagement priorities, and exit conditions.

## Completion Outcome

You can design and evaluate SRE programs, guide reliability investment, establish governance without unnecessary bureaucracy, and communicate production risk to technical and business leaders.

## Repository Sections

- [SRE Organizations and Culture](./26-SRE-Organizations-and-Culture/)
- [SRE Maturity and Governance](./27-SRE-Maturity-and-Governance/)
- [SRE Leadership](./28-SRE-Leadership/)
- [SRE Career Development](./35-SRE-Career-Development/)

---

# Role-Based Paths

## SRE Practitioner Path

Complete Phases 1 through 10 in order, then select the relevant domains from Phase 11.

**Expected result:** You can own service reliability, define objectives, respond to incidents, troubleshoot failures, reduce toil, evaluate readiness, and improve resilience.

## Senior SRE Path

Prioritize:

- Advanced SLO and error budget design
- Complex incident leadership
- Distributed systems failure
- Capacity and performance modelling
- Resilience and disaster recovery
- Reliability architecture
- Cross-team risk management
- SRE maturity and governance

**Expected result:** You can lead ambiguous investigations and reliability improvements across services and teams.

## Incident Commander Path

Prioritize Phases 3, 4, 5, and 6.

**Expected result:** You can establish command, control response risk, coordinate specialists, communicate impact, verify recovery, and lead post-incident learning.

## SLO and Reliability Measurement Path

Prioritize Phases 1, 2, 3, and 12.

**Expected result:** You can create user-centered reliability measures, establish error budget policies, design burn-rate alerts, and operate an organization-wide SLO program.

## Resilience Engineer Path

Prioritize Phases 5, 8, 9, 10, and 11.

**Expected result:** You can identify failure modes, model overload, bound cascading failure, design containment, and validate recovery.

## SRE Leader Path

Complete Phases 1, 2, 4, 6, 7, and 12, then review the remaining phases at practitioner depth.

**Expected result:** You can build a sustainable SRE function, prioritize reliability work, govern risk, and communicate reliability decisions across the organization.

---

# Roadmap Completion Standard

Completing the roadmap does not mean reading every link or memorizing every term.

You should be able to demonstrate the following capabilities:

## Define

- Identify critical user journeys.
- Define service ownership and criticality.
- Design meaningful SLIs and SLOs.
- Establish error budget and escalation policies.

## Detect

- Design telemetry around user impact.
- Build useful service health views.
- Create actionable alerts.
- Recognize observability gaps and misleading signals.

## Respond

- Participate effectively in on-call.
- Declare, classify, and coordinate incidents.
- Communicate clearly under pressure.
- Mitigate impact and verify recovery.

## Diagnose

- Construct timelines.
- Collect and evaluate evidence.
- Form and test hypotheses safely.
- Investigate partial, cascading, and intermittent failures.

## Improve

- Write useful postmortems.
- Design measurable corrective actions.
- Reduce toil through safe engineering.
- Improve production readiness and change safety.

## Scale

- Forecast demand and evaluate headroom.
- Design realistic performance tests.
- Apply load shedding and graceful degradation.
- Reason about distributed systems failure.

## Recover

- Identify failure domains and shared risks.
- Design containment and resilience tests.
- Define RTO and RPO.
- Validate backup, restore, failover, and failback procedures.

## Lead

- Prioritize reliability investment.
- Design sustainable SRE operating models.
- Assess reliability maturity.
- Communicate technical risk to decision-makers.

---

# Recommended Next Step

Begin with:

1. [01-SRE-Foundations](./01-SRE-Foundations/)
2. [02-Service-Ownership](./02-Service-Ownership/)
3. [03-SLIs-SLOs-and-SLAs](./03-SLIs-SLOs-and-SLAs/)
4. [04-Error-Budgets](./04-Error-Budgets/)
5. [05-Reliability-Measurement](./05-Reliability-Measurement/)

Do not rush into tools. First learn to identify what must remain reliable, how users experience failure, what level of risk is acceptable, and how reliability will be measured.

---

## Contributing

Resources, corrections, production scenarios, public incident reports, and practical SRE material are welcome when they meet the repository’s quality requirements.

Before contributing, read:

- [Contribution Guide](./CONTRIBUTING.md)
- [Resource Standard](./RESOURCE-STANDARD.md)
- [Code of Conduct](./CODE_OF_CONDUCT.md)

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> Reliability is not the absence of failure. It is the ability to anticipate, detect, withstand, recover from, and learn from failure.
