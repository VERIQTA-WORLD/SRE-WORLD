# SRE Foundation Resources

> This resource collection supports the SRE foundations in Chapter 1 through authoritative books, standards, research, engineering guidance, talks, and case studies. It favors sources that explain durable principles, provide production evidence, and disclose their context.

## Section Purpose

The internet contains thousands of pages labeled SRE. Many repeat definitions, promote tools, copy one company's practices without context, or describe general operations under an SRE title.

This section is intentionally curated. It does not attempt to list everything.

Resources are selected because they provide one or more of the following:

- A primary or authoritative explanation
- A durable SRE principle
- Production experience
- A clear operating model
- Evidence-based reliability guidance
- A useful counterpoint to mainstream SRE practice
- A practical method that can be adapted safely
- Historical importance to the discipline

Each collection explains what the resource covers, why it matters, the recommended audience, and which Chapter 1 sections it supports.

This section is not a substitute for official documentation for a specific technology. Chapter 1 concerns the discipline, reasoning, responsibilities, and organizational foundation of SRE.

---

## Learning Objectives

After completing this section, you should be able to:

1. Select SRE resources according to a learning objective.
2. Distinguish primary sources from summaries and commentary.
3. Build a foundation reading path without collecting random links.
4. Interpret company-specific practices in context.
5. Combine SRE, resilience, distributed-systems, human-factors, and risk sources.
6. Evaluate whether a resource is current, credible, and relevant.
7. Record verification and maintenance information.
8. Use resources to produce practical work rather than passive notes.

---

## 1. How to Use This Resource Collection

Do not read every resource in sequence.

Use this process:

1. Identify the Chapter 1 concept you need.
2. Begin with one primary foundation source.
3. Read one practical implementation source.
4. Compare one different organizational perspective where available.
5. Apply the concept through [Section 25](./25-SRE-Foundation-Practical-Exercises.md).
6. Record what changed in your service model or decision.

Reading becomes valuable when it changes analysis, design, operation, or risk decisions.

---

## 2. Resource Classification

| Type | Purpose |
| --- | --- |
| Primary book | Establishes concepts from authors or organizations that developed the practice |
| Official guidance | Describes current first-party engineering or architecture guidance |
| Standard | Provides a structured vocabulary, control, or risk framework |
| Research paper | Presents evidence, theory, or a technical result |
| Case study | Shows how principles behaved in a specific production context |
| Talk | Provides practitioner explanation and production experience |
| Community collection | Supports continued learning across organizations |

Company practice is evidence from one context, not a universal rule.

---

## 3. Difficulty Levels

| Level | Meaning |
| --- | --- |
| Foundation | Suitable for a first serious study of the concept |
| Intermediate | Assumes basic SRE and production knowledge |
| Advanced | Requires distributed-systems, organizational, or mathematical depth |
| Reference | Best used when solving a specific problem |

Difficulty does not measure quality. A short foundation resource may be more useful than an advanced paper for the current decision.

---

## 4. Resource Evaluation Standard

Before adding a source, ask:

- Who created it?
- Is it a primary source?
- Which claim or skill does it support?
- Does it disclose organizational context?
- Does it explain tradeoffs and failure modes?
- Is the material maintained?
- Is the link stable?
- Is access free, paid, or restricted?
- Does it duplicate an existing stronger source?
- Can a learner produce practical work from it?

Popularity alone is not a quality standard.

---

## 5. Core Collection: Site Reliability Engineering

### [Site Reliability Engineering](https://sre.google/sre-book/table-of-contents/)

- Publisher: O'Reilly Media
- Editors: Betsy Beyer, Chris Jones, Jennifer Petoff, and Niall Richard Murphy
- Access: Free online edition
- Level: Foundation to advanced
- Best for: The original public description of Google SRE principles and practice
- Key topics: Risk, SLOs, toil, monitoring, automation, release engineering, overload, cascading failure, incident management, and organizational practice
- Chapter 1 connection: Sections 1 through 23

Read the book as a detailed account of one influential implementation. Separate its durable principles from Google's scale, technology, and organizational context.

---

## 6. Core Collection: The Site Reliability Workbook

### [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/)

- Publisher: O'Reilly Media
- Editors: Betsy Beyer, Niall Richard Murphy, David K. Rensin, Kent Kawahara, and Stephen Thorne
- Access: Free online edition
- Level: Foundation to intermediate
- Best for: Applying SRE concepts through practical methods and case studies
- Key topics: SLO implementation, alerting, toil, on-call, incidents, postmortems, overload, configuration, canaries, engagement, and organizational change
- Chapter 1 connection: Sections 3, 8 through 13, and 18 through 25

Use the workbook after or alongside the first SRE book. It provides more implementation detail and examples from organizations outside Google.

---

## 7. Core Collection: Building Secure and Reliable Systems

### [Building Secure and Reliable Systems](https://google.github.io/building-secure-and-reliable-systems/)

- Publisher: O'Reilly Media
- Access: Free online edition
- Level: Intermediate to advanced
- Best for: Treating security and reliability as connected design concerns
- Key topics: Design principles, least privilege, resilience, recovery, monitoring, incident response, and organizational culture
- Chapter 1 connection: Sections 5 through 8, 18, 23, and 24

This book is especially useful when availability goals, emergency access, data integrity, and security controls appear to conflict.

---

## 8. Core Collection: SRE Fundamentals Hub

### [Google Site Reliability Engineering](https://sre.google/)

- Source: Google SRE
- Access: Free
- Level: All levels
- Best for: Official books, practices, talks, and updates in one place
- Chapter 1 connection: All sections

Use this hub to locate the canonical version of Google SRE material instead of relying on copied excerpts.

---

## 9. Start Here: What SRE Means

### [Introduction to Site Reliability Engineering](https://sre.google/sre-book/introduction/)

- Source: Site Reliability Engineering
- Level: Foundation
- Learn: The engineering approach to operations and the original Google framing
- Apply: Rewrite your SRE definition without tools
- Chapter 1 connection: Sections 1, 2, 3, 18, and 22

### [How SRE Relates to DevOps](https://sre.google/workbook/how-sre-relates/)

- Source: The Site Reliability Workbook
- Level: Foundation
- Learn: Similarities and differences between SRE and DevOps
- Apply: Create a comparison based on principles and mechanisms
- Chapter 1 connection: Section 14

---

## 10. History and Evolution

### [SRE at Google](https://sre.google/)

- Source: Google SRE
- Level: Foundation
- Learn: The published lineage, books, and public practice collection
- Chapter 1 connection: Section 2

### [USENIX SREcon](https://www.usenix.org/conferences/byname/925)

- Source: USENIX
- Access: Many talk pages and recordings are free
- Level: Intermediate to advanced
- Learn: How SRE practice has evolved across companies and technical domains
- Apply: Compare two talks from different years on the same problem
- Chapter 1 connection: Sections 2, 19, 22, and 23

Conference talks vary in scope and evidence. Prefer sessions that disclose service context, failure, tradeoffs, and measurable outcomes.

---

## 11. SRE Mindset and Risk

### [Embracing Risk](https://sre.google/sre-book/embracing-risk/)

- Source: Site Reliability Engineering
- Level: Foundation
- Learn: Why reliability is a risk-management problem and why 100 percent is usually the wrong target
- Apply: Write a reliability risk and target decision
- Chapter 1 connection: Sections 3, 5, 11, 20, and 22

### [Google Cloud Reliability Pillar](https://cloud.google.com/architecture/framework/reliability)

- Source: Google Cloud Well-Architected Framework
- Level: Intermediate
- Learn: How reliability principles, risk, recovery, observability, and operational readiness influence architecture and engineering priorities
- Apply: Compare two reliability investments by expected risk reduction
- Chapter 1 connection: Sections 5, 11, and 23

---

## 12. Service-Level Objectives

### [Service Level Objectives](https://sre.google/sre-book/service-level-objectives/)

- Source: Site Reliability Engineering
- Level: Foundation
- Learn: SLI, SLO, SLA, target selection, and service measurement
- Apply: Draft one user-centered SLI and SLO
- Chapter 1 connection: Sections 1, 4, 5, 10, 11, and 23

### [Implementing SLOs](https://sre.google/workbook/implementing-slos/)

- Source: The Site Reliability Workbook
- Level: Foundation to intermediate
- Learn: A practical process for creating, adopting, and refining SLOs
- Apply: Create an SLO document and error-budget policy
- Chapter 1 connection: Sections 10, 11, 20, 21, and 23

### [SLO Engineering Case Studies](https://sre.google/workbook/slo-engineering-case-studies/)

- Source: The Site Reliability Workbook
- Level: Intermediate
- Learn: How organizations adapted SLO practice to their environments
- Apply: Identify which decisions required local adaptation
- Chapter 1 connection: Sections 19, 22, and 23

---

## 13. Error Budgets and Alerting

### [Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/)

- Source: The Site Reliability Workbook
- Level: Intermediate
- Learn: Error-budget burn, multiple alert windows, precision, recall, and operational response
- Apply: Calculate burn rate and design a page policy
- Chapter 1 connection: Sections 11, 18, 23, and 25

### [Example Error Budget Policy](https://sre.google/workbook/error-budget-policy/)

- Source: The Site Reliability Workbook
- Level: Foundation
- Learn: How reliability performance can change release and prioritization decisions
- Apply: Adapt the policy to a fictional service, then identify what cannot be copied safely
- Chapter 1 connection: Sections 11, 20, 21, and 23

---

## 14. Product-Focused Reliability

### [Product-Focused Reliability for SRE](https://sre.google/resources/practices-and-processes/product-focused-reliability-for-sre/)

- Source: Google SRE resources
- Level: Foundation
- Learn: Connecting reliability to user goals and Critical User Journeys
- Apply: Identify product journeys before selecting indicators
- Chapter 1 connection: Sections 4 and 10

### [Art of SLOs](https://sre.google/resources/practices-and-processes/art-of-slos/)

- Source: Google SRE resources
- Level: Foundation to intermediate
- Learn: Practical SLO reasoning and communication
- Apply: Review whether an objective represents what users care about
- Chapter 1 connection: Sections 4, 10, 11, and 23

---

## 15. Monitoring and Observability Foundations

### [Monitoring Distributed Systems](https://sre.google/sre-book/monitoring-distributed-systems/)

- Source: Site Reliability Engineering
- Level: Foundation to intermediate
- Learn: Symptoms, causes, the four golden signals, and human-oriented monitoring
- Apply: Separate paging signals from diagnostic telemetry
- Chapter 1 connection: Sections 1, 3, 10, 18, 22, and 23

### [Monitoring](https://sre.google/workbook/monitoring/)

- Source: The Site Reliability Workbook
- Level: Intermediate
- Learn: Monitoring strategy in changing production systems
- Apply: Audit whether current monitoring detects failed user journeys
- Chapter 1 connection: Sections 8, 10, 18, and 24

Monitoring chapters should be read with the SLO material. Collecting signals without a service decision creates telemetry without a reliability model.

---

## 16. Toil

### [Eliminating Toil](https://sre.google/sre-book/eliminating-toil/)

- Source: Site Reliability Engineering
- Level: Foundation
- Learn: The defining characteristics of toil and the need to protect engineering time
- Apply: Classify one month of work
- Chapter 1 connection: Sections 12, 13, 18, 19, and 23

### [Eliminating Toil in Practice](https://sre.google/workbook/eliminating-toil/)

- Source: The Site Reliability Workbook
- Level: Foundation to intermediate
- Learn: Toil identification, measurement, prioritization, and reduction methods
- Apply: Build a toil inventory and business case
- Chapter 1 connection: Sections 13, 19, 21, 23, and 25

---

## 17. On-Call

### [Being On-Call](https://sre.google/sre-book/being-on-call/)

- Source: Site Reliability Engineering
- Level: Foundation
- Learn: On-call design, staffing, operational load, and engineering expectations
- Apply: Assess whether a rotation can be sustained
- Chapter 1 connection: Sections 8, 12, 13, 18, and 23

### [On-Call](https://sre.google/workbook/on-call/)

- Source: The Site Reliability Workbook
- Level: Foundation to intermediate
- Learn: Practical preparation, response, balance, and team health
- Apply: Audit twelve weeks of pages and after-hours impact
- Chapter 1 connection: Sections 8, 18, 19, 21, 23, and 25

---

## 18. Incident Response

### [Managing Incidents](https://sre.google/sre-book/managing-incidents/)

- Source: Site Reliability Engineering
- Level: Foundation
- Learn: Incident command, roles, communication, and control
- Apply: Create an incident role card and escalation path
- Chapter 1 connection: Sections 3, 8, 18, 23, and 24

### [Incident Response](https://sre.google/workbook/incident-response/)

- Source: The Site Reliability Workbook
- Level: Foundation to intermediate
- Learn: Practical incident frameworks and case studies
- Apply: Run a tabletop scenario with staged evidence
- Chapter 1 connection: Sections 8, 18, 23, 24, and 25

---

## 19. Post-Incident Learning

### [Postmortem Culture: Learning From Failure](https://sre.google/workbook/postmortem-culture/)

- Source: The Site Reliability Workbook
- Level: Foundation to intermediate
- Learn: Learning reviews, psychological safety, review criteria, and action quality
- Apply: Rewrite an incident conclusion that ends with human error
- Chapter 1 connection: Sections 3, 8, 22, 23, and 25

### [Postmortem Culture](https://sre.google/sre-book/postmortem-culture/)

- Source: Site Reliability Engineering
- Level: Foundation
- Learn: The role of blameless postmortems in organizational learning
- Apply: Define postmortem triggers and publication policy
- Chapter 1 connection: Sections 3, 8, 18, and 23

---

## 20. Overload and Cascading Failure

### [Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/)

- Source: Site Reliability Engineering
- Level: Advanced
- Learn: Positive feedback, retries, queue growth, overload, and recovery hazards
- Apply: Model retry amplification across a service graph
- Chapter 1 connection: Sections 6, 7, 18, and 24

### [Identifying and Recovering From Overload](https://sre.google/workbook/managing-load/)

- Source: The Site Reliability Workbook
- Level: Intermediate
- Learn: Load balancing, overload detection, and safe recovery
- Apply: Define overload signals and protected degraded behavior
- Chapter 1 connection: Sections 6, 7, 18, 23, and 25

### [Handling Overload](https://sre.google/sre-book/handling-overload/)

- Source: Site Reliability Engineering
- Level: Advanced
- Learn: Admission control, load shedding, and service protection
- Apply: Prioritize requests during constrained capacity
- Chapter 1 connection: Sections 6, 7, and 24

---

## 21. Distributed Systems Foundations

### [Time, Clocks, and the Ordering of Events in a Distributed System](https://www.microsoft.com/en-us/research/publication/time-clocks-ordering-events-distributed-system/)

- Author: Leslie Lamport
- Source: Microsoft Research publication page
- Level: Advanced
- Learn: Logical time, event ordering, and distributed-system reasoning
- Apply: Analyze ordering assumptions in incident timelines and replication
- Chapter 1 connection: Sections 6, 7, and 24

### [The Byzantine Generals Problem](https://www.microsoft.com/en-us/research/publication/byzantine-generals-problem/)

- Authors: Leslie Lamport, Robert Shostak, and Marshall Pease
- Source: Microsoft Research publication page
- Level: Advanced
- Learn: Agreement under faulty or malicious behavior
- Apply: Explain why replication alone does not guarantee correct agreement
- Chapter 1 connection: Sections 6 and 7

### [In Search of an Understandable Consensus Algorithm](https://raft.github.io/raft.pdf)

- Authors: Diego Ongaro and John Ousterhout
- Source: Raft project paper
- Level: Advanced
- Learn: Consensus, leader election, log replication, and safety
- Apply: Map split-brain and failover assumptions
- Chapter 1 connection: Sections 6, 7, and 24

---

## 22. Failure and Resilience Thinking

### [How Complex Systems Fail](https://how.complexsystems.fail/)

- Author: Richard I. Cook
- Level: Foundation to intermediate
- Learn: Multiple contributing conditions, defenses, latent failure, and operator adaptation
- Apply: Review an incident without searching for one root cause
- Chapter 1 connection: Sections 3, 6, 7, 8, and 22

### [STELLA Report](https://snafucatchers.github.io/)

- Source: SNAFUcatchers
- Level: Intermediate
- Learn: Resilience engineering, adaptive capacity, and incident analysis in software systems
- Apply: Identify how responders adapted beyond documented procedure
- Chapter 1 connection: Sections 3, 6, 8, 22, and 24

These resources extend SRE beyond component failure and help explain why reliable production depends on adaptation, context, and human expertise.

---

## 23. Human Factors and Learning From Incidents

### [Learning From Incidents](https://www.learningfromincidents.io/)

- Source: Learning From Incidents community
- Level: Intermediate
- Learn: Modern incident analysis, human factors, and organizational learning
- Apply: Compare learning-focused review with root-cause-only review
- Chapter 1 connection: Sections 3, 8, 22, 23, and 24

### [Resilience Engineering Association](https://www.resilience-engineering-association.org/)

- Source: Resilience Engineering Association
- Level: Intermediate to advanced
- Learn: Research and community material on resilience, adaptation, and complex sociotechnical systems
- Apply: Add human and organizational conditions to a failure model
- Chapter 1 connection: Sections 3, 6, 7, and 8

---

## 24. Disaster Recovery and Continuity

### [Google Cloud Architecture Framework: Disaster Recovery Planning Guide](https://cloud.google.com/architecture/dr-scenarios-planning-guide)

- Source: Google Cloud Architecture Center
- Level: Intermediate
- Learn: Business impact, RTO, RPO, recovery patterns, and testing
- Apply: Compare recovery strategies by cost and recovery objectives
- Chapter 1 connection: Sections 5, 6, 7, and 24

### [AWS Disaster Recovery of Workloads on AWS](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html)

- Source: AWS whitepaper
- Level: Intermediate
- Learn: Backup and restore, pilot light, warm standby, multi-site, RTO, and RPO
- Apply: Select a strategy based on business requirements
- Chapter 1 connection: Sections 5 and 7

### [Azure Well-Architected Framework: Disaster Recovery](https://learn.microsoft.com/en-us/azure/well-architected/reliability/disaster-recovery)

- Source: Microsoft Learn
- Level: Intermediate
- Learn: Recovery requirements, design, testing, and operations
- Apply: Build a complete recovery plan beyond infrastructure failover
- Chapter 1 connection: Sections 5, 6, and 7

Cloud-specific guidance should be adapted to the complete service and its users. Provider architecture does not replace business continuity, application recovery, access, data validation, or failback.

---

## 25. Cloud Reliability Frameworks

### [Google Cloud Architecture Framework: Reliability](https://cloud.google.com/architecture/framework/reliability)

- Source: Google Cloud
- Level: Foundation to intermediate
- Learn: Reliability principles across design, operation, recovery, and change
- Apply: Compare recommendations with the service failure model
- Chapter 1 connection: Sections 4 through 7 and 23

### [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html)

- Source: AWS
- Level: Foundation to intermediate
- Learn: Foundations, architecture, change, and failure management
- Apply: Review a workload without treating framework compliance as proof
- Chapter 1 connection: Sections 5 through 8 and 23

### [Azure Well-Architected Framework: Reliability](https://learn.microsoft.com/en-us/azure/well-architected/reliability/)

- Source: Microsoft Learn
- Level: Foundation to intermediate
- Learn: Reliability design principles, requirements, resilience, recovery, and operations
- Apply: Map recommendations to explicit CUJs and SLOs
- Chapter 1 connection: Sections 4 through 8 and 23

---

## 26. Security and Reliability

### [NIST SP 800-160 Volume 2 Revision 1](https://csrc.nist.gov/pubs/sp/800/160/v2/r1/final)

- Source: National Institute of Standards and Technology
- Title: Developing Cyber-Resilient Systems
- Level: Advanced reference
- Learn: Cyber resiliency objectives, techniques, and system engineering considerations
- Apply: Extend a failure model to malicious and destructive conditions
- Chapter 1 connection: Sections 5 through 8 and 24

### [NIST Cybersecurity Framework 2.0](https://www.nist.gov/cyberframework)

- Source: National Institute of Standards and Technology
- Level: Reference
- Learn: Governance, identification, protection, detection, response, and recovery outcomes
- Apply: Map security and reliability ownership without combining them vaguely
- Chapter 1 connection: Sections 5, 8, 9, and 18

---

## 27. Service Ownership and Production Responsibility

### [SRE Engagement Model](https://sre.google/workbook/engagement-model/)

- Source: The Site Reliability Workbook
- Level: Intermediate
- Learn: Engagement through service lifecycle, shared goals, onboarding, and handback
- Apply: Write an engagement charter and lifecycle
- Chapter 1 connection: Sections 8, 9, 18, 19, 20, and 21

### [Evolving SRE Engagement Model](https://sre.google/sre-book/evolving-sre-engagement-model/)

- Source: Site Reliability Engineering
- Level: Intermediate
- Learn: Production readiness, service engagement, and organizational evolution
- Apply: Build onboarding criteria and a Production Readiness Review
- Chapter 1 connection: Sections 8, 9, 18, 19, and 25

---

## 28. SRE Operating Models

### [SRE Team Lifecycles](https://sre.google/workbook/team-lifecycles/)

- Source: The Site Reliability Workbook
- Level: Intermediate
- Learn: Principles that SRE organizations must preserve as they form and change
- Apply: Assess whether the team can regulate workload and retain engineering time
- Chapter 1 connection: Sections 19 through 21

### [How SRE Teams Are Organized and How to Get Started](https://cloud.google.com/blog/products/devops-sre/how-sre-teams-are-organized-and-how-to-get-started)

- Source: Google Cloud blog
- Level: Foundation
- Learn: Kitchen-sink, infrastructure, tools, product, embedded, and consulting models
- Apply: Compare strengths and risks for three models
- Chapter 1 connection: Section 19

### [Organizational Change Management in SRE](https://sre.google/workbook/organizational-change/)

- Source: The Site Reliability Workbook
- Level: Intermediate
- Learn: Introducing reliability practice through organizational change
- Apply: Build a stakeholder and adoption plan
- Chapter 1 connection: Sections 19, 20, and 21

---

## 29. SRE Beyond a Dedicated Team

### [SRE: Reaching Beyond Your Walls](https://sre.google/workbook/reaching-beyond/)

- Source: The Site Reliability Workbook
- Level: Intermediate
- Learn: Extending reliability practice through consulting, education, and influence
- Apply: Design a reliability enablement model for teams without SRE coverage
- Chapter 1 connection: Sections 18 through 21

This resource helps prevent the assumption that every service requires permanent SRE pager ownership.

---

## 30. Large-System Design

### [Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/)

- Source: The Site Reliability Workbook
- Level: Advanced
- Learn: Turning requirements into concrete large-system design under constraints
- Apply: Build capacity, component, and failure calculations for a service
- Chapter 1 connection: Sections 3, 5 through 7, 18, and 25

### [Reliable Product Launches at Scale](https://sre.google/sre-book/reliable-product-launches/)

- Source: Site Reliability Engineering
- Level: Intermediate
- Learn: Launch coordination, review, capacity, and operational readiness
- Apply: Create launch criteria and ownership
- Chapter 1 connection: Sections 4, 8, 18, and 19

---

## 31. Release Engineering and Safe Change

### [Release Engineering](https://sre.google/sre-book/release-engineering/)

- Source: Site Reliability Engineering
- Level: Intermediate
- Learn: Reproducibility, automation, hermeticity, and release process
- Apply: Assess whether a service can change safely
- Chapter 1 connection: Sections 3, 8, 12, 18, and 23

### [Canarying Releases](https://sre.google/workbook/canarying-releases/)

- Source: The Site Reliability Workbook
- Level: Intermediate
- Learn: Limited exposure, control populations, analysis, and rollout decisions
- Apply: Define promotion and abort criteria tied to service outcomes
- Chapter 1 connection: Sections 8, 18, 23, and 24

---

## 32. Configuration Reliability

### [Configuration Design and Best Practices](https://sre.google/workbook/configuration-design/)

- Source: The Site Reliability Workbook
- Level: Intermediate
- Learn: Configuration interfaces, validation, defaults, and operational safety
- Apply: Review one high-risk production configuration
- Chapter 1 connection: Sections 7, 8, 12, and 18

### [Configuration Specifics](https://sre.google/workbook/configuration-specifics/)

- Source: The Site Reliability Workbook
- Level: Advanced
- Learn: Concrete configuration failure modes and design considerations
- Apply: Create a safe configuration change standard
- Chapter 1 connection: Sections 7, 8, 18, and 24

---

## 33. Capacity Planning

### [Software Engineering in SRE](https://sre.google/sre-book/software-engineering-in-sre/)

- Source: Site Reliability Engineering
- Level: Intermediate
- Learn: Engineering approaches, project selection, and production improvement
- Apply: Turn a recurring capacity task into an engineering project
- Chapter 1 connection: Sections 3, 12, 13, and 18

### [Data Integrity: What You Read Is What You Wrote](https://sre.google/sre-book/data-integrity/)

- Source: Site Reliability Engineering
- Level: Intermediate
- Learn: Availability, durability, backup, restoration, and data integrity
- Apply: Define evidence for a successful restore
- Chapter 1 connection: Sections 6 and 7

Use the overload and large-system design resources in Sections 20 and 30 of this collection for deeper capacity work.

---

## 34. Testing Reliability

### [Testing for Reliability](https://sre.google/sre-book/testing-reliability/)

- Source: Site Reliability Engineering
- Level: Intermediate
- Learn: Test strategy, failure testing, and confidence in production systems
- Apply: Build a test plan from a failure model
- Chapter 1 connection: Sections 6 through 8 and 24

### [Load Testing](https://sre.google/sre-book/load-testing/)

- Source: Site Reliability Engineering
- Level: Intermediate
- Learn: Load assumptions, capacity, test design, and limitations
- Apply: Design a representative capacity test with stop conditions
- Chapter 1 connection: Sections 6, 7, 18, and 24

---

## 35. Simplicity

### [Simplicity](https://sre.google/workbook/simplicity/)

- Source: The Site Reliability Workbook
- Level: Foundation to intermediate
- Learn: Why unnecessary complexity increases operational risk and cognitive demand
- Apply: Identify one system capability that can be removed or simplified
- Chapter 1 connection: Sections 3, 12, 13, and 23

### [Simplicity](https://sre.google/sre-book/simplicity/)

- Source: Site Reliability Engineering
- Level: Intermediate
- Learn: Managing complexity and preserving system understandability
- Apply: Review the operational cost of one architecture decision
- Chapter 1 connection: Sections 3, 6, 12, and 18

---

## 36. Communication and Collaboration

### [Communication and Collaboration in SRE](https://sre.google/sre-book/communication-and-collaboration/)

- Source: Site Reliability Engineering
- Level: Foundation to intermediate
- Learn: Cross-team relationships, documentation, consulting, and coordination
- Apply: Map one recurring product-SRE conflict to goals and decision rights
- Chapter 1 connection: Sections 8, 9, 14 through 19

### [Operational Overload](https://sre.google/sre-book/operational-overload/)

- Source: Site Reliability Engineering
- Level: Intermediate
- Learn: How excess operational work damages service and team performance
- Apply: Establish workload controls and escalation
- Chapter 1 connection: Sections 12, 13, 18, 19, and 21

---

## 37. Reliability Standards and Vocabulary

### [NIST Systems Security Engineering Publications](https://csrc.nist.gov/projects/systems-security-engineering/publications)

- Source: NIST Computer Security Resource Center
- Level: Advanced reference
- Learn: System lifecycle, assurance, resilience, and engineering vocabulary
- Apply: Compare SRE service reasoning with formal system-engineering controls
- Chapter 1 connection: Sections 5 through 9

### [IETF RFC Index](https://www.rfc-editor.org/)

- Source: RFC Editor
- Level: Reference
- Learn: Primary protocol specifications and internet standards
- Apply: Verify protocol behavior before making reliability assumptions
- Chapter 1 connection: Sections 6, 7, and 24

Standards can improve precision. They should not be used as a substitute for testing the actual service.

---

## 38. Reliability Engineering Outside Software

### [NASA Systems Engineering Handbook](https://www.nasa.gov/reference/systems-engineering-handbook/)

- Source: NASA
- Level: Advanced reference
- Learn: Requirements, verification, validation, risk, interfaces, and lifecycle reasoning
- Apply: Strengthen traceability between reliability requirements and evidence
- Chapter 1 connection: Sections 5 through 9 and 23

The language and constraints differ from internet-service SRE. Use the handbook to broaden systems reasoning, not to copy process mechanically.

---

## 39. Video and Talk Collection

### [Google SRE Resources](https://sre.google/resources/)

- Source: Google SRE
- Access: Free
- Level: All levels
- Best for: Curated practices, talks, and explanations
- Chapter 1 connection: All sections

### [USENIX SREcon Video Archive](https://www.usenix.org/conferences/byname/925)

- Source: USENIX
- Access: Varies by conference and session
- Level: Intermediate to advanced
- Best for: Production case studies and evolving practice
- Chapter 1 connection: Sections 2, 18, 19, 22, 23, and 24

### [CNCF YouTube Channel](https://www.youtube.com/@cncf)

- Source: Cloud Native Computing Foundation
- Access: Free
- Level: All levels
- Best for: Conference sessions on cloud-native reliability, observability, platforms, and incidents
- Chapter 1 connection: Sections 14, 16, 18, 22, and 24

Choose individual talks based on speaker experience, disclosed context, technical depth, and relevance. A channel link is a discovery source, not an endorsement of every session.

---

## 40. Community and Continued Learning

### [USENIX SREcon](https://www.usenix.org/srecon)

- Best for: Practitioner conferences focused on reliability and production engineering
- Use: Follow current programs and review archived sessions

### [Cloud Native Computing Foundation](https://www.cncf.io/)

- Best for: Cloud-native project communities and technical events
- Use: Study relevant reliability material without equating cloud-native tools with SRE

### [Learning From Incidents Community](https://www.learningfromincidents.io/)

- Best for: Incident learning, human factors, and resilience practice
- Use: Extend postmortem practice beyond simple root-cause analysis

Community participation is not evidence of competence by itself. Apply, test, and document what you learn.

---

## 41. Recommended Foundation Reading Path

### Stage 1: Meaning and Mindset

1. [Introduction to Site Reliability Engineering](https://sre.google/sre-book/introduction/)
2. [Embracing Risk](https://sre.google/sre-book/embracing-risk/)
3. [How SRE Relates to DevOps](https://sre.google/workbook/how-sre-relates/)
4. [How Complex Systems Fail](https://how.complexsystems.fail/)

### Stage 2: Users and Objectives

1. [Product-Focused Reliability for SRE](https://sre.google/resources/practices-and-processes/product-focused-reliability-for-sre/)
2. [Service Level Objectives](https://sre.google/sre-book/service-level-objectives/)
3. [Implementing SLOs](https://sre.google/workbook/implementing-slos/)
4. [Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/)

### Stage 3: Production Work

1. [Monitoring Distributed Systems](https://sre.google/sre-book/monitoring-distributed-systems/)
2. [Eliminating Toil](https://sre.google/workbook/eliminating-toil/)
3. [On-Call](https://sre.google/workbook/on-call/)
4. [Incident Response](https://sre.google/workbook/incident-response/)
5. [Postmortem Culture](https://sre.google/workbook/postmortem-culture/)

### Stage 4: Resilience and Recovery

1. [Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/)
2. [Identifying and Recovering From Overload](https://sre.google/workbook/managing-load/)
3. [Testing for Reliability](https://sre.google/sre-book/testing-reliability/)
4. [Building Secure and Reliable Systems](https://google.github.io/building-secure-and-reliable-systems/)

### Stage 5: Organization

1. [SRE Engagement Model](https://sre.google/workbook/engagement-model/)
2. [SRE Team Lifecycles](https://sre.google/workbook/team-lifecycles/)
3. [SRE: Reaching Beyond Your Walls](https://sre.google/workbook/reaching-beyond/)
4. [Organizational Change Management in SRE](https://sre.google/workbook/organizational-change/)

---

## 42. Four-Week Foundation Study Plan

### Week 1: Service and Risk

- Read the Introduction and Embracing Risk chapters.
- Complete Exercises 1 through 6 in Section 25.
- Produce a service definition, user inventory, and CUJ map.

### Week 2: SLOs and Measurement

- Read Service Level Objectives, Implementing SLOs, and Alerting on SLOs.
- Complete Exercises 7 through 12.
- Produce an SLI, SLO, error budget, and policy.

### Week 3: Operations and Failure

- Read the toil, on-call, incident, postmortem, overload, and testing resources.
- Complete Exercises 13 through 30.
- Produce a failure model, recovery plan, incident model, and toil assessment.

### Week 4: Organization and Success

- Read the engagement, lifecycle, and organizational change resources.
- Complete Exercises 31 through 41.
- Produce an operating-model decision and capstone dossier.

---

## 43. Eight-Week Team Study Plan

| Week | Theme | Primary output |
| --- | --- | --- |
| 1 | SRE meaning and history | Team definition and boundaries |
| 2 | Users and product reliability | CUJ inventory |
| 3 | SLOs and risk tolerance | SLO proposal and policy |
| 4 | Resilience and recovery | Failure model and recovery plan |
| 5 | Production ownership | Responsibility matrix |
| 6 | Toil and on-call | Sustainability assessment |
| 7 | Operating models | Team charter and engagement model |
| 8 | Measurement and review | SRE scorecard and capstone review |

Use one real service throughout the program where access and confidentiality permit.

---

## 44. Reading Record Template

For every completed resource, record:

- Resource title
- Author or organization
- Date accessed
- Learning objective
- Three important claims
- Context and assumptions
- One point of disagreement or uncertainty
- One production application
- One artifact changed
- Follow-up source

Avoid copying long quotations. Summarize the reasoning and link to the source.

---

## 45. Case Study Review Template

When reading a company case study, document:

- Organization type
- Service scale
- User consequence
- Technical environment
- Team structure
- Reliability problem
- Intervention
- Tradeoffs
- Outcome evidence
- Conditions that may not transfer
- Safe experiment for your context

Do not copy a practice without its assumptions.

---

## 46. Talk Review Template

Record:

- Speaker and organization
- Event and year
- Service context
- Problem
- Evidence
- Decision
- Outcome
- Uncertainty
- Commercial interest where relevant
- One follow-up primary source

A confident presentation is not proof. Look for disclosed failure, limits, and measurable outcomes.

---

## 47. Research Paper Review Template

Record:

- Research question
- Authors and affiliation
- Publication venue
- Method
- Population or system
- Main result
- Limitations
- Replication or later evidence
- Relevance to the service
- Risk of incorrect transfer

Read the paper, not only the abstract or a social summary.

---

## 48. Resource Comparison Method

When sources disagree:

1. Compare definitions.
2. Compare service context.
3. Compare evidence.
4. Compare publication date.
5. Identify different objectives.
6. Separate principle from implementation.
7. Record uncertainty.
8. Test the smallest safe hypothesis.

Disagreement can reveal hidden assumptions.

---

## 49. Primary Sources Versus Commentary

Prefer primary sources for:

- Standards
- Protocol behavior
- Official service limits
- Research claims
- Product guarantees
- Company case studies

Use commentary for:

- Explanation
- Comparison
- Critique
- Teaching
- Cross-industry interpretation

Commentary should link back to the evidence it interprets.

---

## 50. Vendor Content

Vendor material can be technically strong, especially when it explains the vendor's own service or product.

Evaluate:

- Product marketing interest
- Portability of the method
- Omitted alternatives
- Evidence quality
- Version and date
- Whether the source explains failure modes

Do not reject a source only because it comes from a vendor. Do not accept it without context.

---

## 51. Books and Paid Resources

A paid book can be valuable, but SRE World should remain useful without requiring purchase.

When adding a paid resource:

- Label it clearly
- Link to the publisher or author
- Explain its unique value
- Avoid affiliate links
- Include a free alternative where practical
- Do not reproduce protected content

The three Google-edited books listed in this section have official free online editions.

---

## 52. Resource Quality Warning Signs

Treat a source cautiously when it:

- Defines SRE only through tools
- Claims universal best practices without context
- Promises perfect reliability
- Confuses SLI, SLO, and SLA
- Treats error budget as outage permission
- Calls all operations toil
- Describes incident blame as accountability
- Provides no author or date
- Copies another source without attribution
- Uses broken or unverifiable claims
- Exists mainly to sell an unrelated product

One weakness does not always invalidate the complete source. Record the limitation.

---

## 53. Avoid Resource Hoarding

A large unread bookmark collection does not build SRE capability.

Use a simple rule:

1. Read one source.
2. Produce one artifact.
3. Apply one change or decision.
4. Verify one result.
5. Then add the next source.

Depth and application matter more than link volume.

---

## 54. Resource-to-Section Map

| Chapter 1 section | Start with |
| --- | --- |
| What Is SRE | Introduction to Site Reliability Engineering |
| History and Evolution | Google SRE hub and SREcon archive |
| SRE Mindset | Embracing Risk and How Complex Systems Fail |
| Reliability as Product | Product-Focused Reliability for SRE |
| Business Risk | Embracing Risk and Managing Risk |
| Reliability Properties | Cloud reliability frameworks and Data Integrity |
| Fault Tolerance and DR | DR guidance and distributed-systems papers |
| Production Responsibility | Evolving SRE Engagement Model |
| Service Ownership | SRE Engagement Model |
| Critical User Journeys | Product-Focused Reliability for SRE |
| Risk Tolerance | Implementing SLOs and Embracing Risk |
| Engineering and Operations | Software Engineering in SRE |
| Toil | Both Eliminating Toil chapters |
| SRE and DevOps | How SRE Relates to DevOps |
| Adjacent Disciplines | SRE books plus official discipline guidance |
| SRE Responsibilities | SRE book and workbook collections |
| Operating Models | Team Lifecycles and organization article |
| Need and Readiness | Engagement Model and Organizational Change |
| Misunderstandings | Introduction, SLOs, Toil, and DevOps relationship |
| Measuring Success | SLOs, alerting, incidents, toil, and on-call |
| Production Scenarios | Incident Response, overload, and cascading failures |
| Practical Exercises | Workbook chapters and Chapter 1 artifacts |

---

## 55. Minimum Foundation Library

If you can use only ten resources, choose:

1. [Introduction to Site Reliability Engineering](https://sre.google/sre-book/introduction/)
2. [Embracing Risk](https://sre.google/sre-book/embracing-risk/)
3. [Service Level Objectives](https://sre.google/sre-book/service-level-objectives/)
4. [Implementing SLOs](https://sre.google/workbook/implementing-slos/)
5. [Monitoring Distributed Systems](https://sre.google/sre-book/monitoring-distributed-systems/)
6. [Eliminating Toil](https://sre.google/workbook/eliminating-toil/)
7. [On-Call](https://sre.google/workbook/on-call/)
8. [Incident Response](https://sre.google/workbook/incident-response/)
9. [SRE Engagement Model](https://sre.google/workbook/engagement-model/)
10. [How Complex Systems Fail](https://how.complexsystems.fail/)

This collection covers the discipline, risk, objectives, monitoring, toil, response, ownership, organization, and systems thinking.

---

## 56. Advanced Foundation Library

After the minimum collection, add:

1. [Building Secure and Reliable Systems](https://google.github.io/building-secure-and-reliable-systems/)
2. [Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/)
3. [Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/)
4. [Time, Clocks, and the Ordering of Events](https://www.microsoft.com/en-us/research/publication/time-clocks-ordering-events-distributed-system/)
5. [The Byzantine Generals Problem](https://www.microsoft.com/en-us/research/publication/byzantine-generals-problem/)
6. [In Search of an Understandable Consensus Algorithm](https://raft.github.io/raft.pdf)
7. [NIST SP 800-160 Volume 2 Revision 1](https://csrc.nist.gov/pubs/sp/800/160/v2/r1/final)
8. [STELLA Report](https://snafucatchers.github.io/)

Use these sources to deepen reasoning about distributed agreement, complex failure, security, large-system design, and resilience.

---

## 57. Practical Output Requirements

After completing the foundation resources, a learner should be able to produce:

- Service definition
- CUJ map
- SLI and SLO
- Error-budget policy
- Reliability risk register
- Failure model
- Recovery plan
- Incident model
- Toil assessment
- On-call health review
- Service ownership record
- SRE charter
- Operating-model decision
- Success scorecard

Use [Section 25](./25-SRE-Foundation-Practical-Exercises.md) to build and validate these artifacts.

---

## 58. Resource Contribution Requirements

A proposed resource should include:

- Title
- Author or organization
- Stable direct link
- Resource type
- Access type
- Publication or revision date where known
- Difficulty
- What it teaches
- Why it is useful
- Chapter 1 mapping
- Known limitations
- Date verified

Submissions without a clear learning purpose may be declined even if the source is popular.

---

## 59. Resource Verification Policy

Before acceptance, verify:

- The link resolves
- The title and author are accurate
- The source contains the described material
- Access requirements are labeled
- The content is not copied without authorization
- The source is not a duplicate
- The material is relevant to SRE foundations

For web resources, record the last verification date in the contribution or maintenance record.

---

## 60. Maintenance Policy

Review resources periodically for:

- Broken links
- Moved canonical pages
- New editions
- Superseded standards
- Changed access conditions
- Significant technical corrections
- Duplicate coverage
- Lost relevance

Do not replace an historically important source merely because it is old. Label historical context and add current guidance where needed.

---

## 61. Link Failure Policy

When a link fails:

1. Search for the canonical replacement from the same author or organization.
2. Confirm that the replacement contains the intended material.
3. Update the link and verification record.
4. Use an archive only when copyright and repository policy permit it.
5. Remove the entry if no trustworthy version remains.

Do not redirect readers to copied or unauthorized versions.

---

## 62. Resource Retirement Policy

Retire or replace a resource when:

- It is technically incorrect in a harmful way
- It has been superseded by an authoritative version
- The source is no longer accessible and no lawful replacement exists
- It duplicates stronger material
- Its connection to SRE foundations is weak
- It becomes primarily promotional without unique value

Record the reason in the repository changelog where the change is material.

---

## 63. Resource Review Checklist

### Authority

- [ ] Author or organization is identifiable.
- [ ] Primary source is used where possible.
- [ ] Claims can be traced to evidence.

### Relevance

- [ ] The resource supports a defined Chapter 1 concept.
- [ ] The learning outcome is explicit.
- [ ] The source adds value beyond existing entries.

### Context

- [ ] Service and organizational context is visible.
- [ ] Tradeoffs and limitations are identified.
- [ ] Company-specific practice is not presented as universal.

### Access and Integrity

- [ ] Direct canonical link resolves.
- [ ] Free or paid access is labeled.
- [ ] Copyright is respected.
- [ ] No affiliate tracking is used.

### Maintenance

- [ ] Publication or revision date is recorded where known.
- [ ] Verification date can be recorded.
- [ ] A replacement or retirement path exists.

---

## 64. Reflection Questions

1. Which foundation concept has the weakest source coverage in your current learning plan?
2. Which resource changed your understanding of SRE most?
3. Which Google-specific practice should not be copied directly into your organization?
4. Which source provides a useful challenge to simple root-cause thinking?
5. Which resource should you apply before reading another one?
6. Can you trace every major reliability claim to a primary source?
7. Which saved resource are you unlikely to use?
8. Which link requires periodic version review?
9. What practical artifact will prove that reading produced learning?
10. Which source is best for your next production problem?

---

## 65. Knowledge Check

1. Why should SRE World avoid listing every available SRE link?
2. What is the difference between a primary source and commentary?
3. Why should company case studies be interpreted in context?
4. Which resource is the main practical companion to the original SRE book?
5. Which resources introduce SLO implementation and burn-rate alerting?
6. Why should distributed-systems research be part of an SRE foundation?
7. What does resilience-engineering material add to SRE study?
8. How should vendor content be evaluated?
9. What should a learner produce after reading a resource?
10. When should an old resource remain in the collection?
11. What information must accompany a new resource contribution?
12. How should a broken link be handled?

---

## 66. Knowledge Check Answers

1. A large uncurated list makes quality, relevance, sequence, verification, and maintenance difficult. The collection should support decisions and learning outcomes.
2. A primary source presents the original standard, research, product behavior, or organizational experience. Commentary explains, compares, critiques, or teaches from sources.
3. Scale, architecture, staffing, risk, users, and organizational authority may differ. A practice can fail when its assumptions do not transfer.
4. The Site Reliability Workbook.
5. Implementing SLOs and Alerting on SLOs in The Site Reliability Workbook.
6. SRE operates distributed services where ordering, consensus, partitions, replication, and failure assumptions affect reliability.
7. It adds sociotechnical systems, adaptation, human expertise, multiple contributing conditions, and learning beyond simple component failure.
8. Assess technical authority, marketing interest, portability, evidence, alternatives, maintenance, and disclosed failure modes.
9. A service artifact, analysis, decision, test, or verified change connected to the learning objective.
10. When it remains historically important or explains a durable principle. Label its context and add current guidance where required.
11. Title, author, canonical link, type, access, date, difficulty, learning value, Chapter mapping, limitations, and verification date.
12. Find the canonical replacement, verify its content, update the record, use lawful archives only when appropriate, or remove the entry.

---

## 67. Key Takeaways

- SRE resources should be curated by authority, relevance, evidence, context, and practical value.
- The Google SRE books remain foundational primary sources, but their implementation context must be considered.
- SRE study should include risk, SLOs, toil, on-call, incidents, recovery, systems design, and organizational practice.
- Distributed-systems research explains technical limits that summaries often hide.
- Resilience and human-factors sources strengthen incident analysis and organizational learning.
- Cloud reliability frameworks are useful references, not proof that a service is reliable.
- Vendor content can be valuable when commercial context and portability are assessed.
- Reading should produce an artifact, decision, experiment, or verified improvement.
- A small applied collection is more valuable than an unread link archive.
- Every resource needs a maintenance and retirement path.

---

## 68. Related SRE World Sections

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
- [SRE Foundations](./README.md)

---

## Next Section

[Section 27: SRE Foundation Completion Assessment](./27-SRE-Foundation-Completion-Assessment.md)

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> The purpose of an SRE resource is not to increase the number of links a learner has saved. It is to improve how that learner understands services, evaluates risk, operates production, and builds reliable systems.
