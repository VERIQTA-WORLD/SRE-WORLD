# Service Level Completion Assessment

> Completion means being able to design, calculate, challenge, govern, and defend a coherent service-level system from user outcome through external commitment.

## Section Purpose

This assessment tests applied competence across the complete collection. It is evidence-based: terminology alone cannot compensate for an invalid measurement boundary, incorrect calculation, or unsupported SLA claim.

## Assessment Case

Use one production-like service with at least:

- a human or machine Critical User Journey;
- synchronous and asynchronous behavior;
- one material dependency;
- at least two user, operation, or geographic segments;
- a measurable availability or completion outcome;
- a latency, correctness, freshness, durability, or quality outcome;
- incomplete or imperfect measurement evidence;
- an internal objective and a proposed or existing external commitment.

Real organizational data may be used only when disclosure is authorized. Otherwise create a realistic fictional case and clearly label assumptions.

## Assessment Structure

| Part | Assessment | Weight | Required evidence |
| --- | --- | ---: | --- |
| A | Terminology and conceptual distinctions | 5 | Written distinctions and counterexamples |
| B | CUJ and measurement-boundary analysis | 10 | Journey map and boundary record |
| C | SLI specification and event classification | 15 | Complete specification and classification tests |
| D | Availability, latency, correctness, freshness, and batch calculations | 15 | Reproducible calculations with units and populations |
| E | SLO target and time-window design | 12 | Target and window decision records |
| F | Dependency, segmentation, and data-quality analysis | 12 | Maps, reconciliation, controls, and unknown handling |
| G | SLA measurability and SLI-SLO-SLA alignment | 10 | Engineering review and alignment matrix |
| H | Production scenarios | 8 | Analysis of four assigned scenarios from Section 32 |
| I | Practical service-level portfolio | 8 | Complete, internally consistent portfolio |
| J | Written or oral defence | 5 | Answers supported by evidence |
|  | **Total** | **100** |  |

## Part Requirements

### A. Terminology

Define SLI, SLO, SLA, valid event, good event, bad event, exclusion, unknown, compliance period, and error budget. For each, give one plausible misuse and explain its consequence.

### B. CUJ and Boundary

Identify the protected user outcome and select a measurement boundary. Explain what happens before, inside, and after it; which failures remain invisible; and why the chosen observation point supports the intended decision.

### C. Specification and Classification

Write one implementation-ready SLI and classify at least twenty representative events, including invalid requests, retries, duplicates, timeouts, dependency failures, partial success, planned maintenance, missing telemetry, and late-arriving truth.

### D. Calculations

Show at least:

1. one ratio-based availability or completion calculation;
2. two threshold-based latency calculations from a distribution;
3. one correctness calculation using a validation source;
4. one freshness or batch deadline calculation;
5. one reconciliation showing good + bad = valid.

State formulas, units, rounding, timestamp rules, source versions, and the interpretation of unknown data.

### E. Target and Window

Compare at least three target candidates and two time-window designs. Defend the selection using user harm, criticality, historical evidence, measurement uncertainty, cost, feasibility, and external commitments. A copied “number of nines” is not sufficient.

### F. Dependencies, Segmentation, and Data Quality

Map critical dependencies and correlated failure, reconcile global and segment results, define minimum-volume treatment, and establish controls for completeness, uniqueness, validity, freshness, and lineage.

### G. SLA Alignment

Review a proposed SLA for engineering measurability. Identify questions requiring legal or commercial authority. Demonstrate headroom and expose differences in population, source, threshold, window, exclusions, consequences, and reporting.

### H. Production Scenarios

Analyze four scenarios selected by the reviewer, including at least one measurement-integrity failure and one contractual-alignment case. Separate facts from unknowns and immediate containment from durable correction.

### I. Portfolio

Submit the following exact structure:

```text
service-level-assessment/
├── service-level-context.md
├── cuj-service-level-map.md
├── measurement-boundary-record.md
├── sli-specification.md
├── event-classification-tests.md
├── sli-calculations.md
├── segmentation-plan.md
├── sli-data-quality-plan.md
├── slo-document.md
├── slo-target-decision.md
├── time-window-decision.md
├── dependency-slo-map.md
├── error-budget-worksheet.md
├── sla-measurability-review.md
├── sli-slo-sla-alignment-matrix.md
└── completion-reflection.md
```

Every reference between files must resolve to the same service, SLI version, boundary, source, target, and window.

### J. Defence

Complete a 20–30 minute review. The reviewer may change one assumption and ask how the design responds. Unsupported confidence should reduce the score more than a clearly stated, managed uncertainty.

## Scoring Rubric

| Performance | Description |
| --- | --- |
| 90–100 | Production-ready: precise, reproducible, user-centered, decision-bearing, and actively challenges weak evidence. |
| 80–89 | Competent: complete and substantially correct, with minor gaps that do not invalidate decisions. |
| 70–79 | Conditional: core reasoning is present, but specified corrections and verification are required. |
| Below 70 | Reassessment required: important definitions, calculations, alignment, or evidence are unreliable. |

The minimum full-pass score is **80/100**. Parts C, D, E, F, G, and I are mandatory pass areas and each requires at least **70%** of its available points.

## Critical-Failure Conditions

Regardless of total score, full pass is withheld when the learner:

- counts missing measurement as success without an approved rule;
- cannot reconcile numerator, denominator, exclusions, and unknowns;
- presents infrastructure health as proof of user success;
- materially changes a source or query without versioning;
- invents facts or conceals uncertainty;
- claims legal approval or contractual meaning without authority;
- proposes an objective with no owner or decision use;
- submits calculations that cannot be reproduced;
- exposes confidential production or customer information without authorization.

## Conditional Pass

A score from 70–79 may receive a conditional pass only when no critical failure exists, every mandatory area reaches 70%, and all required corrections can be completed without redesigning the core model. The reviewer records each correction, evidence required, owner, and due date. Conditional status expires after 30 days unless the program defines a shorter period.

## Reassessment

The learner resubmits only failed areas plus any dependent artifacts affected by corrections. Reassessment must use new event samples or changed assumptions so that memorized answers cannot substitute for competence. One independent reviewer should confirm closure of any measurement-integrity or SLA-alignment defect.

## Evidence Requirements

- Source data may be synthetic, but must be supplied with schema and provenance.
- Calculations must be executable or independently reproducible.
- Screenshots may support evidence but cannot replace authoritative definitions.
- Queries, specifications, and decisions require versions and effective dates.
- Exclusions and unknowns must remain visible.
- Claims about users, contracts, and owners require a cited record or explicit assumption.
- Corrections need verification results, not only revised wording.

## Reviewer Guidance

1. Score the submitted evidence, not presumed experience or job title.
2. Test semantic correctness with adversarial events, not only normal examples.
3. Trace one raw event through eligibility, classification, aggregation, objective, and decision.
4. Change a segment, source, dependency, or window during the defence.
5. Distinguish a measurement defect from poor service performance.
6. Do not award precision when the underlying evidence is uncertain.
7. Record conflicts of interest and use a second reviewer where the candidate designed the organizational standard being assessed.

## Defence Questions

1. Which user harm does this SLI represent, and which harm does it miss?
2. What is the strongest reason to move the measurement boundary?
3. Show how a timeout, retry, duplicate, and missing event are classified.
4. What result would make the current compliance value unknowable?
5. Why is the selected target preferable to the next stricter and weaker targets?
6. How does low volume change interpretation?
7. Which global result could hide a harmed segment?
8. Where can a dependency meet its own objective while this journey fails?
9. What measurement or architecture change would invalidate the SLO?
10. Which SLA term is technically ambiguous, and who has authority to resolve it?
11. What action follows an SLO miss, and who may authorize it?
12. What evidence would cause you to admit that your design is wrong?

## Completion Decision Record

```markdown
# Service Level Completion Decision

- Candidate:
- Service case:
- Reviewers:
- Assessment date:

| Part | Score | Mandatory? | Evidence | Required correction |
| --- | ---: | --- | --- | --- |

- Total:
- Critical failure present: yes/no
- Decision: pass / conditional pass / reassessment required
- Conditions and due dates:
- Reassessment scope:
- Reviewer signatures:
```

## Navigation

- Previous: [Service Level Resources](35-Service-Level-Resources.md)
- Collection home: [SLIs, SLOs, and SLAs](README.md)
- Next collection: `04-Error-Budgets/` when available

---

Part of **SRE World**, maintained by **VERIQTA**.
