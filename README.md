<p align="center">
  <img src="https://github.com/veriqta/veriqta/blob/main/sre%201.png" alt="VERIQTA SRE World Roadmap" width="100%">
</p>

<h1 align="center">SRE WORLD</h1>

<p align="center">
  <strong>A production-focused knowledge base for measuring, protecting, restoring, and improving the reliability of modern services.</strong>
</p>

<p align="center">
  Site Reliability Engineering · SLOs · Error Budgets · Observability · Incidents · On-Call · Resilience
</p>

---

## About SRE World

SRE World is a curated Site Reliability Engineering knowledge base for engineers responsible for availability, latency, performance, capacity, operational risk, and production resilience.

This repository is not a collection of general DevOps tools. It is organized around the responsibilities, decisions, failure modes, and engineering practices involved in operating reliable services.

Every resource should help answer at least one of these questions:

- How do we define and measure reliability?
- How do we detect customer-impacting problems?
- How do we respond when production fails?
- How do we reduce operational risk before failure occurs?
- How do we learn from incidents and prevent recurrence?
- How do we balance reliability, delivery speed, complexity, and cost?

## What This Repository Covers

- Site Reliability Engineering principles and operating models
- Service ownership and production responsibility
- Service Level Indicators, Objectives, and Agreements
- Error budgets and reliability-based release decisions
- Reliability measurement and reporting
- Observability and telemetry design
- Alerting strategy and alert quality
- On-call engineering and sustainable operations
- Incident command, response, and communication
- Production troubleshooting and evidence-based debugging
- Postmortems, learning reviews, and corrective actions
- Toil measurement and safe operational automation
- Production readiness and operational readiness reviews
- Change and release reliability
- Capacity planning and performance engineering
- Distributed systems failure modes
- Resilience engineering and failure testing
- Disaster recovery and continuity planning
- Reliability across cloud, Kubernetes, networks, and data systems
- SRE organizations, maturity, governance, and leadership

## What This Repository Does Not Cover

SRE World does not attempt to duplicate [DEVOPS WORLD](https://github.com/veriqta/DEVOPS-WORLD).

You will not find:

- Beginner Linux, Git, Docker, or Kubernetes courses
- General CI/CD and infrastructure-as-code tutorials
- Cloud certification preparation
- Tool installation walkthroughs without a reliability use case
- Generic lists of monitoring products
- DevOps beginner roadmaps
- Certification dumps or memorization material
- Random links included only because they mention SRE
- Unverified AI-generated summaries

Tools may appear when they support a specific reliability practice, incident scenario, measurement method, or production investigation. The practice remains the focus, not the product.

---

## Start by Responsibility

| If you are responsible for... | Start here |
|---|---|
| Defining acceptable reliability | [SLIs, SLOs, and SLAs](./03-SLIs-SLOs-and-SLAs/) |
| Managing reliability risk | [Error Budgets](./04-Error-Budgets/) |
| Understanding service behavior | [Observability Engineering](./06-Observability-Engineering/) |
| Deciding what should wake an engineer | [Alerting Engineering](./07-Alerting-Engineering/) |
| Joining or improving an on-call rotation | [On-Call Engineering](./08-On-Call-Engineering/) |
| Coordinating production failures | [Incident Management](./09-Incident-Management/) |
| Diagnosing unclear production problems | [Troubleshooting and Debugging](./10-Troubleshooting-and-Debugging/) |
| Learning from failure | [Postmortems and Learning](./11-Postmortems-and-Learning/) |
| Reducing repetitive operational work | [Toil and Automation](./12-Toil-and-Automation/) |
| Deciding whether a service can enter production | [Production Readiness](./13-Production-Readiness/) |
| Preparing for traffic growth | [Capacity Planning](./15-Capacity-Planning/) |
| Designing systems that survive failure | [Resilience Engineering](./18-Resilience-Engineering/) |
| Recovering from major disruption | [Disaster Recovery](./19-Disaster-Recovery/) |

## Explore the Knowledge Map

### Reliability Definition and Control

- [SRE Foundations](./01-SRE-Foundations/)
- [Service Ownership](./02-Service-Ownership/)
- [SLIs, SLOs, and SLAs](./03-SLIs-SLOs-and-SLAs/)
- [Error Budgets](./04-Error-Budgets/)
- [Reliability Measurement](./05-Reliability-Measurement/)

### Detection and Response

- [Observability Engineering](./06-Observability-Engineering/)
- [Alerting Engineering](./07-Alerting-Engineering/)
- [On-Call Engineering](./08-On-Call-Engineering/)
- [Incident Management](./09-Incident-Management/)
- [Troubleshooting and Debugging](./10-Troubleshooting-and-Debugging/)
- [Postmortems and Learning](./11-Postmortems-and-Learning/)

### Prevention and Improvement

- [Toil and Automation](./12-Toil-and-Automation/)
- [Production Readiness](./13-Production-Readiness/)
- [Change and Release Reliability](./14-Change-and-Release-Reliability/)
- [Capacity Planning](./15-Capacity-Planning/)
- [Performance and Load](./16-Performance-and-Load/)

### Systems and Resilience

- [Distributed Systems Reliability](./17-Distributed-Systems-Reliability/)
- [Resilience Engineering](./18-Resilience-Engineering/)
- [Disaster Recovery](./19-Disaster-Recovery/)
- [Data Reliability](./20-Data-Reliability/)
- [Network Reliability](./21-Network-Reliability/)
- [Cloud Reliability](./22-Cloud-Reliability/)
- [Kubernetes Reliability](./23-Kubernetes-Reliability/)
- [Security and Reliability](./24-Security-and-Reliability/)
- [Reliability Architecture](./25-Reliability-Architecture/)

### Organization and Professional Practice

- [SRE Organizations and Culture](./26-SRE-Organizations-and-Culture/)
- [SRE Maturity and Governance](./27-SRE-Maturity-and-Governance/)
- [SRE Leadership](./28-SRE-Leadership/)
- [SRE Case Studies](./29-SRE-Case-Studies/)
- [Production Incidents](./30-Production-Incidents/)
- [SRE Projects and Labs](./31-SRE-Projects-and-Labs/)
- [SRE Interview Scenarios](./32-SRE-Interview-Scenarios/)
- [SRE Research Papers](./33-SRE-Research-Papers/)
- [Books, Talks, and Courses](./34-Books-Talks-and-Courses/)
- [SRE Career Development](./35-SRE-Career-Development/)

---

## Featured Collections

### Reliability Pattern Library

Practical explanations of patterns such as circuit breakers, bulkheads, retry budgets, backpressure, load shedding, graceful degradation, fault isolation, and cell-based architecture.

[Explore reliability patterns](./Reliability-Patterns/)

### SLO Example Library

Inspectable SLI and SLO examples for APIs, authentication, payments, e-commerce, messaging, data pipelines, internal platforms, batch workloads, Kubernetes platforms, and AI services.

[Explore SLO examples](./SLO-Examples/)

### Public Incident Library

Public production incidents classified by trigger, impact, contributing conditions, detection, mitigation, recovery, and transferable reliability lessons.

[Explore public incidents](./Incident-Library/)

### SRE Decision Records

Decision guides for questions such as whether an alert should page, whether a retry is safe, whether to fail open or closed, and whether a service needs multi-region architecture.

[Explore SRE decisions](./Decision-Records/)

### Production Failure Encyclopedia

Failure investigations organized by customer symptoms and system behavior, not by product names.

[Explore production failures](./Production-Failure-Library/)

---

## SRE Learning Paths

SRE World does not prescribe one universal tool roadmap. Choose a path based on the production responsibility you want to develop.

### SRE Practitioner

1. SRE foundations
2. Service ownership
3. SLIs and SLOs
4. Error budgets
5. Observability
6. Alerting
7. On-call engineering
8. Incident response
9. Production troubleshooting
10. Postmortems
11. Toil reduction
12. Production readiness
13. Capacity and performance
14. Distributed systems
15. Resilience engineering

[Open the SRE Practitioner path](./Learning-Paths/SRE-Practitioner.md)

### Senior SRE

Focus on advanced SLO design, complex incident leadership, distributed failure, capacity modelling, reliability architecture, cross-team risk, and organizational reliability programs.

[Open the Senior SRE path](./Learning-Paths/Senior-SRE.md)

### Incident Commander

Learn incident declaration, severity assignment, command structure, coordination, decision logging, communication, mitigation, recovery, and post-incident handover.

[Open the Incident Commander path](./Learning-Paths/Incident-Commander.md)

### SLO and Reliability Measurement

Develop expertise in user journeys, indicator design, SLO mathematics, error budgets, burn rates, alerting, reporting, and SLO governance.

[Open the SLO Engineer path](./Learning-Paths/SLO-Engineer.md)

### SRE Leadership

Study SRE team models, staffing, sustainable on-call, reliability investment, stakeholder negotiation, governance, metrics, and executive communication.

[Open the SRE Leadership path](./Learning-Paths/SRE-Leadership.md)

---

## Reliability Templates

The template collection turns SRE principles into repeatable operational practice.

| Template | Purpose |
|---|---|
| [SLI Specification](./Templates/SLI-Specification.md) | Define exactly what is measured and why it represents user experience. |
| [SLO Design Worksheet](./Templates/SLO-Design-Worksheet.md) | Design an objective, measurement window, target, exclusions, and ownership model. |
| [Error Budget Policy](./Templates/Error-Budget-Policy.md) | Connect reliability performance to release and risk decisions. |
| [Production Readiness Review](./Templates/Production-Readiness-Review.md) | Assess whether a service is ready for production ownership. |
| [Incident Timeline](./Templates/Incident-Timeline.md) | Record evidence, events, decisions, actions, and impact. |
| [Incident Communication](./Templates/Incident-Communication.md) | Communicate clear, timely updates during an incident. |
| [Blameless Postmortem](./Templates/Blameless-Postmortem.md) | Analyze contributing conditions and corrective work. |
| [Runbook](./Templates/Runbook.md) | Document a safe and verifiable operational response. |
| [On-Call Handover](./Templates/On-Call-Handover.md) | Transfer active risk, incidents, and operational context. |
| [Capacity Review](./Templates/Capacity-Review.md) | Evaluate demand, limits, headroom, and failure capacity. |

Additional operational material is available in [Checklists](./Checklists/), [Runbooks](./Runbooks/), [Playbooks](./Playbooks/), and [Worksheets](./Worksheets/).

## Production Failure Library

The failure library teaches investigation through realistic symptoms.

Every failure scenario should include:

- Customer impact
- Observable system symptoms
- Timeline and recent changes
- Likely failure domains
- Evidence to collect
- Hypotheses to test
- Dangerous assumptions
- Safe mitigation options
- Recovery verification
- Prevention and follow-up work

Example scenarios include:

- Latency increases while CPU remains normal
- Error rates rise after a successful deployment
- A service is healthy but users cannot complete transactions
- Database connections are exhausted
- Queue depth rises continuously
- Retries amplify an upstream failure
- DNS fails for only part of the user population
- Autoscaling creates instability
- Monitoring is green while customers report failure
- Regional failover risks overloading the recovery region

[Enter the Production Failure Library](./Production-Failure-Library/)

## Recently Added

New and materially updated resources will be listed here with their verification dates.

| Date | Resource | Domain | Change |
|---|---|---|---|
| To be added | Initial SRE World release | Repository | Foundation structure and first verified collections |

See [CHANGELOG.md](./CHANGELOG.md) for the complete history.

---

## Contribution Standard

Contributions are welcome when they improve the quality, accuracy, or practical value of the repository.

Before opening a pull request:

1. Confirm that the contribution is specifically relevant to Site Reliability Engineering.
2. Search the repository to avoid duplicates.
3. Prefer original sources, engineering publications, public incident reports, conference talks, research papers, and official documentation.
4. Explain why the resource is valuable to a reliability practitioner.
5. Identify the intended experience level and SRE domain.
6. Declare whether the resource is free, paid, archived, or requires registration.
7. Check that the link works and points to the permanent source when possible.
8. Avoid promotional, copied, misleading, or low-context material.
9. Do not submit certification dumps, generic DevOps tutorials, or unexplained tool lists.
10. Use clear language and preserve the existing repository structure.

Read [CONTRIBUTING.md](./CONTRIBUTING.md) and [RESOURCE-STANDARD.md](./RESOURCE-STANDARD.md) before contributing.

## Resource Record Standard

Resources should be documented with enough context for an engineer to decide whether they are useful before leaving the repository.

```text
Resource ID:
Title:
Author or Organization:
Resource Type:
SRE Domain:
Experience Level:
Publication Date:
Last Verified:
Access:
Primary or Secondary Source:

What It Covers:
Why It Is Valuable:
What It Does Not Cover:
Production Relevance:
Recommended Prerequisites:
Estimated Time:
Key Lessons:
Related Resources:
Permanent Link:
Status:
```

Experience levels:

- Foundation
- Practitioner
- Senior
- Staff
- Leadership
- Research

Resource status:

- Active
- Stable
- Historically important
- Archived
- Broken

## Maintenance and Verification Policy

SRE World is maintained as a curated engineering knowledge base, not an unrestricted link directory.

- Links should be checked before inclusion.
- Every resource should include a `Last Verified` date.
- Broken links should be repaired, replaced, or clearly marked.
- Outdated resources may remain when they have historical or conceptual value.
- Archived resources should be labeled.
- Duplicate resources should be consolidated.
- Vendor resources should teach transferable reliability principles.
- Incident reports should link to the original publication whenever possible.
- Major technical claims should be supported by primary or authoritative sources.
- Resource quality takes priority over resource quantity.

If you find an outdated, misleading, duplicated, or broken resource, open an issue with the resource path and recommended correction.

---

## About VERIQTA

SRE World is created and maintained by **VERIQTA**, an engineering education platform focused on production infrastructure, Site Reliability Engineering, platform engineering, cloud systems, security, and modern technical operations.

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- LinkedIn: [VERIQTA](https://www.linkedin.com/company/veriqta-academy/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)
- X: [@veriqta](https://x.com/veriqta)
- Telegram: [VERIQTA](https://t.me/veriqta)

## Support the Project

If SRE World helps you, you can support it by:

- Starring the repository
- Sharing it with another reliability engineer
- Reporting broken or outdated resources
- Contributing high-quality production knowledge
- Supporting VERIQTA through [Buy Me a Coffee](https://www.buymeacoffee.com/veriqta)

## License

This repository is licensed under the terms provided in [LICENSE](./LICENSE).

Resource ownership remains with the original authors and publishers. SRE World provides curation, classification, commentary, templates, and original educational material. Always follow the license and usage terms of each linked resource.

---

<p align="center">
  <strong>Reliability is not the absence of failure. It is the ability to anticipate, detect, withstand, recover from, and learn from failure.</strong>
</p>

<p align="center">
  Created by <a href="https://github.com/veriqta">VERIQTA</a>
</p>
