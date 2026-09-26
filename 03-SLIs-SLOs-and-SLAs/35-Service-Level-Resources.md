# Service Level Resources

> A useful resource collection is selective, primary-source oriented, annotated, and maintained. It should help a reader make better service-level decisions, not bury them in links.

## Section Purpose

This index supports the work in this collection: user-centered indicators, objective design, measurement quality, error-budget fundamentals, pipeline objectives, alerting boundaries, machine-readable specifications, and SLA measurability. It intentionally excludes general monitoring-product lists and does not substitute for dedicated observability, alerting, or error-budget-policy material.

Difficulty uses three levels: **Foundation** for direct introductions, **Practitioner** for implementation guidance, and **Advanced** for material requiring statistical or systems context. Links were verified on **2026-09-26**.

## Core SLI, SLO, and SLA Sources

### 1. Service Level Objectives

- **Author/organization:** Chris Jones, John Wilkes, Niall Murphy, Cody Smith; Google
- **Canonical link:** [Site Reliability Engineering, Chapter 4](https://sre.google/sre-book/service-level-objectives/)
- **Type / difficulty:** Book chapter / Foundation
- **What it teaches:** Core distinctions among SLIs, SLOs, and SLAs; indicator selection; aggregation; target choice; control loops; safety margins.
- **Why it belongs:** It is a foundational primary source for the vocabulary and reasoning used throughout this collection.
- **Limitations:** Some examples use older Google systems, and its sample average-latency objective should not override the distribution-aware guidance elsewhere in the same chapter.
- **Relevant sections:** 01–02, 08–09, 18, 21–23, 28–30

### 2. Implementing SLOs

- **Author/organization:** Alex Hidalgo, Google SRE Workbook
- **Canonical link:** [Implementing SLOs](https://sre.google/workbook/implementing-slos/)
- **Type / difficulty:** Implementation chapter / Practitioner
- **What it teaches:** User journeys, SLI specifications, valid events, objectives, error budgets, documentation, and iteration.
- **Why it belongs:** It converts service-level concepts into a repeatable design workflow.
- **Limitations:** Organizations must adapt roles, data sources, and governance to their own authority model.
- **Relevant sections:** 03–07, 16–17, 21–27

### 3. SLO Engineering Case Studies

- **Author/organization:** Google SRE Workbook contributors
- **Canonical link:** [SLO Engineering Case Studies](https://sre.google/workbook/slo-engineering-case-studies/)
- **Type / difficulty:** Case studies / Practitioner
- **What it teaches:** How different organizations introduce, refine, and operationalize SLOs.
- **Why it belongs:** It shows that principles remain stable while implementation varies with service and organizational context.
- **Limitations:** Case-study outcomes are contextual, not universal target recommendations.
- **Relevant sections:** 01, 21–27, 31–33

### 4. Example SLO Document

- **Author/organization:** Google SRE Workbook
- **Canonical link:** [Example SLO Document](https://sre.google/workbook/slo-document/)
- **Type / difficulty:** Worked example / Foundation
- **What it teaches:** A concrete service description, SLI implementations, objectives, and error-budget calculation.
- **Why it belongs:** Readers can compare their own specification and SLO document with a complete example.
- **Limitations:** The example is illustrative; copying its boundaries or targets without analysis would be an anti-pattern.
- **Relevant sections:** 05, 08–09, 21, 26, 34

## Budgets and Alerting Boundaries

### 5. Example Error Budget Policy

- **Author/organization:** Google SRE Workbook
- **Canonical link:** [Example Error Budget Policy](https://sre.google/workbook/error-budget-policy/)
- **Type / difficulty:** Policy example / Practitioner
- **What it teaches:** How SLO performance can inform release and reliability decisions.
- **Why it belongs:** It clarifies why an error budget must connect to a decision and why the budget is not an SLA remedy threshold.
- **Limitations:** This collection covers budget derivation only; policy design and enforcement require broader organizational work.
- **Relevant sections:** 01, 21, 26–27, 30

### 6. Alerting on SLOs

- **Author/organization:** Google SRE Workbook
- **Canonical link:** [Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/)
- **Type / difficulty:** Technical chapter / Advanced
- **What it teaches:** Error-budget consumption, burn rates, windows, precision, recall, and alert design trade-offs.
- **Why it belongs:** It establishes the boundary between measuring an objective and notifying humans about threatening consumption.
- **Limitations:** Implementing multi-window, multi-burn-rate alerting belongs in the dedicated alerting collection, not here.
- **Relevant sections:** 23, 26, 35

## Workload-Specific Measurement

### 7. Data Processing Pipelines

- **Author/organization:** Google SRE Workbook contributors
- **Canonical link:** [Data Processing Pipelines](https://sre.google/workbook/data-processing/)
- **Type / difficulty:** Technical chapter / Practitioner
- **What it teaches:** Pipeline correctness, timeliness, monitoring, retries, and operational design.
- **Why it belongs:** Request-centric measures do not adequately describe batch and data-processing outcomes.
- **Limitations:** Examples require translation to local data semantics, deadlines, and reconciliation sources.
- **Relevant sections:** 10, 12, 14–15

### 8. Monitoring Distributed Systems

- **Author/organization:** Rob Ewaschuk; Google
- **Canonical link:** [Site Reliability Engineering, Chapter 6](https://sre.google/sre-book/monitoring-distributed-systems/)
- **Type / difficulty:** Book chapter / Foundation
- **What it teaches:** Monitoring definitions, the four golden signals, symptom-versus-cause reasoning, and measurement design.
- **Why it belongs:** It helps separate user-facing service indicators from diagnostic infrastructure signals.
- **Limitations:** Full telemetry architecture and instrumentation are outside this collection.
- **Relevant sections:** 04, 08–12, 16, 31

## Machine-Readable Objectives

### 9. OpenSLO Specification

- **Author/organization:** OpenSLO community
- **Canonical link:** [OpenSLO](https://openslo.com/)
- **Type / difficulty:** Open specification / Practitioner
- **What it teaches:** Vendor-neutral objects for representing services, indicators, objectives, alert conditions, and related metadata as code.
- **Why it belongs:** It provides a shared machine-readable vocabulary and supports version-controlled SLO practice.
- **Limitations:** A schema can encode a decision but cannot determine the correct user journey, boundary, source, or target.
- **Relevant sections:** 05, 21, 27, 34

### 10. OpenSLO Reference Repository

- **Author/organization:** OpenSLO community
- **Canonical link:** [OpenSLO on GitHub](https://github.com/OpenSLO/OpenSLO)
- **Type / difficulty:** Specification repository / Advanced
- **What it teaches:** Current schema, examples, proposals, governance, and implementation-facing details.
- **Why it belongs:** It is the authoritative place to verify the version being implemented rather than relying on secondary summaries.
- **Limitations:** Specification evolution requires version pinning and compatibility review.
- **Relevant sections:** 27, 34

## Provider Implementation References

### 11. Concepts in Service Monitoring

- **Author/organization:** Google Cloud
- **Canonical link:** [Google Cloud Observability: Concepts in Service Monitoring](https://docs.cloud.google.com/stackdriver/docs/solutions/slo-monitoring)
- **Type / difficulty:** Official provider documentation / Foundation
- **What it teaches:** Services, SLIs, SLOs, compliance, and error budgets in a concrete implementation.
- **Why it belongs:** It demonstrates how abstract definitions become data and calculations in an operational platform.
- **Limitations:** Product-specific object models are not universal standards and should not define the service boundary by themselves.
- **Relevant sections:** 01–02, 16–17, 21, 26

### 12. SLI Metrics Overview

- **Author/organization:** Google Cloud
- **Canonical link:** [Creating SLI Metrics](https://docs.cloud.google.com/stackdriver/docs/solutions/slo-monitoring/sli-metrics/overview)
- **Type / difficulty:** Official provider documentation / Practitioner
- **What it teaches:** Request-based and windows-based indicators, metric selection, and implementation constraints.
- **Why it belongs:** It gives a concrete comparison of two common calculation families.
- **Limitations:** Readers must validate provider semantics, retention, alignment, missing data, and aggregation against their own specification.
- **Relevant sections:** 16–17, 20

## Statistical Foundations

### 13. NIST/SEMATECH e-Handbook of Statistical Methods

- **Author/organization:** National Institute of Standards and Technology
- **Canonical link:** [Exploratory Data Analysis](https://www.itl.nist.gov/div898/handbook/eda/eda.htm)
- **Type / difficulty:** Official statistical handbook / Advanced
- **What it teaches:** Distributions, quantiles, variability, graphical analysis, and assumptions needed for sound interpretation.
- **Why it belongs:** Latency and reliability data are often skewed, censored, segmented, and misread through averages.
- **Limitations:** It is not SRE-specific; readers must translate statistical methods into event-based service measurement.
- **Relevant sections:** 18–20, 22–23

## SLA Engineering Boundary

SLA language is jurisdictional and contractual. Use the engineering records in Sections 28–30 to test measurability, feasibility, data authority, and operational administration. Use the organization's authorized legal and commercial reviewers for contract interpretation, remedies, enforceability, regulatory terms, and negotiation. No general web resource can replace that review.

## Resource Acceptance Standard

A proposed addition should:

1. address a defined learning need in this collection;
2. prefer an original, official, or standards source;
3. have a stable canonical location and identifiable maintainer;
4. disclose scope, assumptions, and material limitations;
5. avoid acting as promotion for a monitoring tool;
6. include a verification date and section mapping.

Review links at least twice each year and when a referenced specification is superseded. Mark archived resources; do not silently replace a source with materially different guidance.

## Navigation

- Previous: [Service Level Templates](34-Service-Level-Templates.md)
- Next: [Service Level Completion Assessment](36-Service-Level-Completion-Assessment.md)
- Collection: [SLIs, SLOs, and SLAs](README.md)

---

Part of **SRE World**, maintained by **VERIQTA**.
