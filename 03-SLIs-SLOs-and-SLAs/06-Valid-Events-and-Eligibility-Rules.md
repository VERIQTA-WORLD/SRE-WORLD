# Valid Events and Eligibility Rules

> Define which observations belong in the evaluated population without hiding genuine user harm or allowing denominator manipulation.

## Section Purpose

Define which observations belong in the evaluated population without hiding genuine user harm or allowing denominator manipulation.

This section controls eligibility. It does not decide whether an eligible event is good, which belongs in Section 7.

The practical output is a **Valid-event and exclusion policy**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain the role of eligibility before quality in a service-level system.
2. Explain the role of malformed and unauthorized requests in a service-level system.
3. Explain the role of client cancellation in a service-level system.
4. Explain the role of retries and duplicates in a service-level system.
5. Explain the role of synthetic and health traffic in a service-level system.
6. Explain the role of administrative and internal traffic in a service-level system.
7. Explain the role of abuse and attack traffic in a service-level system.
8. Explain the role of maintenance in a service-level system.

---

## Eligibility before quality

First decide whether an observation belongs in scope. Only then classify it as good or bad. Mixing the decisions creates exclusions that silently improve the result.

---

## Malformed and unauthorized requests

Some traffic is clearly outside the service contract. Other failures result from confusing product behavior or service defects. Exclusion requires a documented boundary, not a convenient status code.

---

## Client cancellation

A cancellation before the service begins work may be excluded. A cancellation caused by excessive latency represents user harm. The data must distinguish the cases.

---

## Retries and duplicates

Counting every retry can exaggerate both volume and failure. Deduplication may better represent a user attempt, while request-level reliability may intentionally count each server interaction. Choose explicitly.

---

## Synthetic and health traffic

Synthetic probes can validate reachability but should not silently dominate a user-traffic SLI. Separate synthetic and real-user populations unless the objective explicitly combines them.

---

## Administrative and internal traffic

Back-office, operator, migration, and maintenance operations may have different reliability expectations. Exclude them only if another indicator protects their required outcome.

---

## Abuse and attack traffic

Filtering malicious or abusive traffic may be justified, but the detection method can misclassify valid users. Record the control owner, uncertainty, and impact.

---

## Maintenance

Planned work is still experienced by users. An SLA may exclude approved maintenance, while an internal SLO may count it to preserve the engineering cost of downtime.

---

## Missing fields

An event that cannot be classified should become unknown, not automatically good. Track unknown volume and define when measurement confidence is lost.

---

## Anti-gaming controls

Review denominator changes, exclusion growth, filter ownership, and segment removal. Recalculate from raw data when possible and require approval for material rule changes.


---

## Production Scenario

A team excludes every 4xx response. The service recently began returning 429 to valid customers because of an internal capacity problem. The exclusion converts a reliability failure into invisible traffic.

### Analysis Questions

1. Which user outcome is at risk?
2. What is the correct measurement population and boundary?
3. Which evidence is authoritative?
4. Which assumption could make the result misleading?
5. Who owns the indicator and decision?
6. What immediate correction is required?
7. How will the corrected design be verified?

---

## Practical Output: Valid-event and exclusion policy

Create a record containing:

- Observation type:
- Included population:
- Excluded population:
- Reason:
- Detection rule:
- Risk of misclassification:
- Unknown handling:
- Approval authority:
- Test cases:
- Version and review:

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

- Define which observations belong in the evaluated population without hiding genuine user harm or allowing denominator manipulation.
- A percentage without a precise population, calculation, window, and owner is not a trustworthy service level.
- User-visible outcomes take priority over convenient infrastructure signals.
- Unknown and excluded events require explicit treatment.
- Every service-level artifact needs validation and lifecycle control.

---

## Navigation

[Previous: Anatomy of an SLI Specification](./05-Anatomy-of-an-SLI-Specification.md)

[Next: Good, Bad, and Total Events](./07-Good-Bad-and-Total-Events.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

