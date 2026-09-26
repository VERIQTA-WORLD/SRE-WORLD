# Durability and Data Integrity SLIs

> Measure whether committed state remains preserved, correct, and retrievable over the period users and obligations require.

## Section Purpose

Measure whether committed state remains preserved, correct, and retrievable over the period users and obligations require.

This section defines indicators and evidence. Backup architecture, disaster recovery, and restoration design belong in later resilience collections.

The practical output is a **Durability and data-integrity SLI specification**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain committed state and its effect on service-level accuracy.
2. Explain loss and corruption and its effect on service-level accuracy.
3. Explain retrievability and its effect on service-level accuracy.
4. Explain silent failure and its effect on service-level accuracy.
5. Explain replica agreement and its effect on service-level accuracy.
6. Explain restore verification and its effect on service-level accuracy.
7. Explain retention and its effect on service-level accuracy.
8. Explain rare-event measurement and its effect on service-level accuracy.
9. Apply the section to a realistic production service.
10. Produce and verify the required practical artifact.

---

## Committed state

Define the point at which the service tells a user that data is durable. Acknowledgement before safe persistence changes the risk boundary.

---

## Loss and corruption

Loss means expected data is absent. Corruption means data exists but is invalid, altered, or unusable. Both require independent detection.

---

## Retrievability

Stored data that cannot be retrieved by an authorized user within the required process is not delivering the intended durable outcome.

---

## Silent failure

Rare durability defects may remain invisible for months. Scrubbing, checksums, reconciliation, restore tests, and audit evidence provide leading signals.

---

## Replica agreement

Replication reduces some risks but can copy corruption or deletion. Agreement among replicas is not proof of correctness.

---

## Restore verification

A successful backup job is not a durable user outcome. Measure whether protected state can be restored and validated.

---

## Retention

Durability operates within a retention promise. Data preserved beyond required deletion can be a compliance failure rather than success.

---

## Rare-event measurement

Short windows cannot prove extremely high durability claims directly. Combine observed outcomes with control evidence and state the inference.

---

## Integrity and authorization

Integrity includes protection from unauthorized or unintended change. Pair state validation with custody and access evidence.

---

## Durability, Integrity, and Recoverability

Durability asks whether a committed object remains preserved and retrievable over time. Integrity asks whether the retrieved object is correct and uncorrupted. Recoverability asks whether service and data can be restored after disruption. These properties support one another but are not interchangeable.

Replication does not prove durability. Replicas can reproduce accidental deletion, software corruption, compromised credentials, or a faulty write.

## Define the Commit Point

The denominator begins when the service tells the consumer that data is committed. If acknowledgement occurs before required persistence, the service creates an unmeasured loss interval.

For committed objects:

$$
Durability = \frac{Committed\ Objects\ Preserved\ and\ Retrievable}{All\ Committed\ Objects}
$$

Because loss is rare and may be discovered late, report counts and confidence as well as percentages.

## Evidence Sources

- write-ahead or commit records;
- periodic inventory reconciliation;
- checksums and content hashes;
- read-after-write verification;
- independent backup inventories;
- restore-test results;
- deletion and retention audit records;
- customer-reported missing objects.

No single source proves every failure mode.

## Worked Example

A storage service records 500,000,000 committed objects. Reconciliation finds:

- 499,999,970 retrievable with valid integrity;
- 10 missing;
- 12 corrupted;
- 8 inaccessible because authorization metadata is inconsistent.

If all 30 represent failed committed objects:

$$
Durability = \frac{499{,}999{,}970}{500{,}000{,}000} = 99.999994\%
$$

The high percentage must not minimize the consequence. Report the 30 objects, affected users, data class, cause, and recovery status.

## Backup Is Not the SLI

Backup completion is a control measure. It does not prove that committed data remains recoverable. A durability program validates:

- backup scope and completeness;
- independence from primary failure domains;
- integrity of retained data;
- authorization to retrieve;
- restore success;
- achieved RPO and RTO where applicable.

## Destructive and Correlated Failure

Test accidental deletion, corrupted writes, lost encryption keys, malicious deletion, common credentials, region loss, and faulty lifecycle policies. Durability claims must state which failure model they cover.

## Production Scenario

All backup jobs report success, but a restore exercise reveals that encryption keys for older backups are unavailable. Backup activity is healthy while retrievability is not.

### Analysis Questions

1. Which user or consumer outcome matters?
2. Which population and measurement boundary apply?
3. Which evidence should be trusted?
4. What could make the reported value misleading?
5. Which owner has authority to correct the design?
6. What should be changed now?
7. How will the change be verified?

---

## Practical Output: Durability and data-integrity SLI specification

Create a record containing:

- Commit point:
- Protected state:
- Retention period:
- Loss definition:
- Corruption definition:
- Retrieval success:
- Validation source:
- Restore evidence:
- Rare-event limitations:
- Owner:

Record unknowns, limitations, owners, dates, and validation evidence. Never improve a result by silently removing difficult observations.

---

## Review Checklist

- [ ] User outcome and population are explicit.
- [ ] Measurement and service boundaries are distinguished.
- [ ] Calculation rules are reproducible.
- [ ] Missing, duplicate, delayed, excluded, and unknown evidence is handled.
- [ ] Relevant segments remain visible.
- [ ] Limitations and uncertainty are stated.
- [ ] The accountable owner accepted the design.
- [ ] Test cases include failure and edge conditions.
- [ ] Review triggers and version history are recorded.

---

## Key Takeaways

- Measure whether committed state remains preserved, correct, and retrievable over the period users and obligations require.
- Convenient telemetry is not automatically reliable evidence.
- Aggregate success must not hide a materially harmed population.
- Measurement failure is itself an operational risk.
- Every material definition or query change requires controlled review.

---

## Navigation

[Previous: Freshness SLIs](./12-Freshness-SLIs.md)

[Next: Batch and Data Pipeline SLIs](./14-Batch-and-Data-Pipeline-SLIs.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)
