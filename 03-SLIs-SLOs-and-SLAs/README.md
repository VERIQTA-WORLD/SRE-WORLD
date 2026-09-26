# SLIs, SLOs, and SLAs

> Service-level engineering turns important user outcomes into measurements, internal reliability objectives, and carefully governed commitments.

## Collection Purpose

This collection teaches how to define, calculate, validate, govern, and defend Service Level Indicators, Service Level Objectives, and Service Level Agreements for real production services.

It answers one central question:

> How does an organization translate important user outcomes into measurable service levels, set justified reliability targets, make external commitments, and prove that the measurements can be trusted?

SRE Foundations explains why reliability must be explicit. [Service Ownership](../02-Service-Ownership/README.md) identifies who owns the production outcome. This collection defines how that outcome is measured, targeted, reviewed, and committed.

## Intended Audience

This material is designed for:

- Site Reliability Engineers
- Production Engineers
- Software and service owners
- Platform and infrastructure teams
- Observability engineers
- Engineering managers and technical leaders
- Product leaders responsible for reliability decisions
- Data and analytics engineers supporting reliability measurement
- Risk, commercial, and legal stakeholders reviewing service commitments

This is not a beginner guide to monitoring tools. It focuses on the reasoning, mathematics, evidence, ownership, and governance behind service levels.

## Prerequisites

Before starting, you should be able to:

- Explain reliability as a user and business outcome
- Identify a production service and its accountable owner
- Define a Critical User Journey
- Distinguish a service from its components and dependencies
- Read basic metrics, logs, traces, and event records
- Work with percentages, ratios, time windows, and simple distributions
- Explain risk tolerance and service criticality

Recommended preparation:

- [SRE Foundations](../01-SRE-Foundations/README.md)
- [Service Ownership](../02-Service-Ownership/README.md)

## Scope

This collection covers:

- Service-level terminology
- User-centered SLI design
- Measurement boundaries
- Valid, good, bad, excluded, and unknown events
- Availability, latency, correctness, quality, freshness, durability, batch, and asynchronous SLIs
- Measurement sources and measurement-system failure
- Ratios, time-based indicators, windows, distributions, percentiles, aggregation, and segmentation
- SLO documents, targets, compliance periods, dependencies, and lifecycle governance
- Error-budget derivation from an SLO
- SLA foundations, measurability, exclusions, consequences, and claims
- Alignment among SLIs, SLOs, SLAs, vendor commitments, and internal operating targets
- Production scenarios, exercises, templates, resources, and assessment

## Scope Exclusions

This collection does not teach these subjects in full:

- Service discovery, ownership transfer, and service catalogs
- Monitoring-platform installation
- Full observability architecture
- Alert routing and escalation engineering
- Multi-window multi-burn-rate alert implementation
- Complete error-budget policy and release enforcement
- Incident command
- On-call staffing
- Capacity engineering
- Disaster-recovery architecture
- Contract drafting or legal advice

Those subjects belong in their dedicated SRE World collections. They appear here only where necessary to define measurement, ownership, evidence, or commitment boundaries.

## Learning Outcomes

After completing this collection, you should be able to:

1. Distinguish an SLI, SLO, SLA, KPI, KRI, OLA, RTO, and RPO.
2. Translate a Critical User Journey into measurable reliability dimensions.
3. Select a defensible measurement boundary.
4. Write a reproducible SLI specification.
5. Classify valid, good, bad, excluded, and unknown events.
6. Design SLIs for different service behaviors and workload types.
7. Calculate request-based, time-based, and window-based indicators.
8. Interpret distributions and tail latency correctly.
9. Prevent aggregation and segmentation from hiding user harm.
10. Evaluate the quality and failure modes of SLI data.
11. Write and govern a complete SLO document.
12. Set targets and windows using evidence and risk.
13. Derive and interpret an error budget.
14. Evaluate whether an SLA is measurable and operationally supportable.
15. Align internal objectives with external and provider commitments.
16. Defend service-level decisions under production ambiguity.

## Section Map

| Section | Guide | Primary outcome |
| ---: | --- | --- |
| 01 | [Service Level Engineering](./01-Service-Level-Engineering.md) | Establish the operating model for service-level decisions. |
| 02 | [SLI, SLO, and SLA Terminology](./02-SLI-SLO-and-SLA-Terminology.md) | Build precise shared vocabulary. |
| 03 | [From Critical User Journeys to Service Levels](./03-From-Critical-User-Journeys-to-Service-Levels.md) | Translate user outcomes into reliability dimensions. |
| 04 | [Service Boundaries and Measurement Boundaries](./04-Service-Boundaries-and-Measurement-Boundaries.md) | Select where experience is measured. |
| 05 | [Anatomy of an SLI Specification](./05-Anatomy-of-an-SLI-Specification.md) | Produce a reproducible indicator specification. |
| 06 | [Valid Events and Eligibility Rules](./06-Valid-Events-and-Eligibility-Rules.md) | Define the denominator honestly. |
| 07 | [Good, Bad, and Total Events](./07-Good-Bad-and-Total-Events.md) | Classify observations and calculate ratios. |
| 08 | [Availability SLIs](./08-Availability-SLIs.md) | Measure whether the service is usable. |
| 09 | [Latency SLIs](./09-Latency-SLIs.md) | Measure whether outcomes finish in useful time. |
| 10 | [Correctness SLIs](./10-Correctness-SLIs.md) | Measure whether outcomes are right. |
| 11 | [Quality and Degradation SLIs](./11-Quality-and-Degradation-SLIs.md) | Measure usefulness during partial degradation. |
| 12 | [Freshness SLIs](./12-Freshness-SLIs.md) | Measure whether information is current enough. |
| 13 | [Durability and Data Integrity SLIs](./13-Durability-and-Data-Integrity-SLIs.md) | Measure preservation and trustworthy retrieval. |
| 14 | [Batch and Data Pipeline SLIs](./14-Batch-and-Data-Pipeline-SLIs.md) | Measure scheduled and multi-stage processing. |
| 15 | [Asynchronous and Event-Driven SLIs](./15-Asynchronous-and-Event-Driven-SLIs.md) | Measure accepted work through eventual completion. |
| 16 | [SLI Measurement Sources](./16-SLI-Measurement-Sources.md) | Select authoritative evidence. |
| 17 | [Ratio, Time-Based, and Window-Based SLIs](./17-Ratio-Time-Based-and-Window-Based-SLIs.md) | Choose the right calculation form. |
| 18 | [Distributions, Percentiles, and Tail Latency](./18-Distributions-Percentiles-and-Tail-Latency.md) | Interpret latency populations accurately. |
| 19 | [Aggregation, Segmentation, and Weighting](./19-Aggregation-Segmentation-and-Weighting.md) | Prevent healthy totals from hiding harmed groups. |
| 20 | [SLI Data Quality and Measurement Failure](./20-SLI-Data-Quality-and-Measurement-Failure.md) | Treat measurement as a production dependency. |
| 21 | [Anatomy of an SLO Document](./21-Anatomy-of-an-SLO-Document.md) | Produce an operational SLO record. |
| 22 | [Setting Defensible SLO Targets](./22-Setting-Defensible-SLO-Targets.md) | Choose targets from evidence and risk. |
| 23 | [SLO Time Windows and Compliance Periods](./23-SLO-Time-Windows-and-Compliance-Periods.md) | Select decision-appropriate time periods. |
| 24 | [Multiple SLOs, Tiers, and User Segments](./24-Multiple-SLOs-Tiers-and-User-Segments.md) | Control complexity across several objectives. |
| 25 | [Dependency, Composite, and End-to-End SLOs](./25-Dependency-Composite-and-End-to-End-SLOs.md) | Connect local objectives to complete journeys. |
| 26 | [Deriving Error Budgets from SLOs](./26-Deriving-Error-Budgets-from-SLOs.md) | Calculate permitted unreliability. |
| 27 | [SLO Ownership, Governance, and Lifecycle](./27-SLO-Ownership-Governance-and-Lifecycle.md) | Keep objectives accepted and current. |
| 28 | [Service Level Agreement Foundations](./28-Service-Level-Agreement-Foundations.md) | Establish the engineering boundary of an SLA. |
| 29 | [SLA Terms, Exclusions, Consequences, and Claims](./29-SLA-Terms-Exclusions-Consequences-and-Claims.md) | Test whether an agreement can be administered fairly. |
| 30 | [Aligning SLIs, SLOs, SLAs, and Internal Commitments](./30-Aligning-SLIs-SLOs-SLAs-and-Internal-Commitments.md) | Build a coherent commitment hierarchy. |
| 31 | [Service Level Anti-Patterns](./31-Service-Level-Anti-Patterns.md) | Detect and correct misleading service-level practices. |
| 32 | [Service Level Production Scenarios](./32-Service-Level-Production-Scenarios.md) | Apply the model to realistic failures. |
| 33 | [Service Level Practical Exercises](./33-Service-Level-Practical-Exercises.md) | Build reusable engineering artifacts. |
| 34 | [Service Level Templates](./34-Service-Level-Templates.md) | Use copy-ready Markdown and YAML templates. |
| 35 | [Service Level Resources](./35-Service-Level-Resources.md) | Study authoritative sources with limitations noted. |
| 36 | [Service Level Completion Assessment](./36-Service-Level-Completion-Assessment.md) | Demonstrate complete service-level engineering competence. |

## Recommended Study Order

Complete Sections 01 through 07 in order. They establish the model, vocabulary, boundary, specification, and event mathematics used everywhere else.

Sections 08 through 15 cover different reliability dimensions and workload types. Complete all of them once, then return to the sections relevant to a specific service.

Sections 16 through 20 establish trustworthy measurement. Sections 21 through 27 build and govern SLOs. Sections 28 through 30 cover SLAs and commitment alignment. Complete Sections 31 through 36 in order.

## Required Practical Outputs

A complete learner portfolio should contain:

1. Service-level engineering charter
2. Terminology reference
3. CUJ to service-level map
4. Measurement-boundary record
5. SLI specification
6. Valid-event and exclusion policy
7. Event-classification test set
8. Reliability-dimension SLI specifications
9. Measurement-source decision record
10. Calculation-method comparison
11. Distribution analysis
12. Segmentation plan
13. SLI data-quality control plan
14. SLO document
15. Target decision record
16. Time-window decision record
17. Multi-SLO model
18. Dependency and end-to-end SLO map
19. Error-budget worksheet
20. SLO governance policy
21. SLA requirements record
22. SLA measurability checklist
23. SLI-SLO-SLA alignment matrix
24. Anti-pattern assessment
25. Production scenario analysis set
26. Practical exercise portfolio
27. Template library
28. Resource index
29. Completion assessment portfolio

## Completion Requirements

Completion requires more than reading. A learner must:

- Produce the required artifacts for one coherent service or Critical User Journey
- Show calculations and source evidence
- Test event-classification rules with edge cases
- Identify measurement uncertainty and blind spots
- Defend the target and time-window choice
- Explain the relationship between the SLO and any SLA
- Complete at least six production scenarios
- Pass the final assessment and defence
- Record unresolved risks with owners and dates

## Navigation

[Previous collection: Service Ownership](../02-Service-Ownership/README.md)

Next collection: Error Budgets and Reliability Policy, planned.

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

> A service level is credible only when the user outcome, measurement, target, ownership, and decision are explicit.
