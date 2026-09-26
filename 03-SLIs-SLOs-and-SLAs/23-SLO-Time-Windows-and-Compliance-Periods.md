# SLO Time Windows and Compliance Periods

> Select time windows that produce timely, stable, and decision-appropriate service-level evidence.

## Section Purpose

Select time windows that produce timely, stable, and decision-appropriate service-level evidence.

This section chooses SLO evaluation periods. Alert windows and burn-rate implementation belong in later alerting material.

The practical output is a **SLO window selection record**.

---

## Learning Objectives

After completing this section, you should be able to:

1. Explain rolling windows and its role in a defensible service-level system.
2. Explain calendar windows and its role in a defensible service-level system.
3. Explain short windows and its role in a defensible service-level system.
4. Explain long windows and its role in a defensible service-level system.
5. Explain seasonality and peaks and its role in a defensible service-level system.
6. Explain business-hour objectives and its role in a defensible service-level system.
7. Explain low-frequency journeys and its role in a defensible service-level system.
8. Explain late data and restatement and its role in a defensible service-level system.
9. Apply the section to an ambiguous production scenario.
10. Produce and defend the required artifact.

---

## Rolling windows

A rolling period always evaluates the most recent duration. It avoids hard resets but changes continuously and requires clear report timestamps.

---

## Calendar windows

A calendar month or quarter aligns with business and contractual reporting but resets abruptly and varies in length.

---

## Short windows

Short periods reveal current harm quickly but are volatile, especially for low traffic. They can trigger overreaction to small samples.

---

## Long windows

Long periods smooth noise and support trend analysis but allow recent severe harm to be diluted by older healthy behavior.

---

## Seasonality and peaks

Choose windows that represent launches, holidays, payroll dates, market hours, or other critical periods rather than averaging them away.

---

## Business-hour objectives

Some services have defined operating schedules. Record timezone, holidays, emergency use, and whether off-hours work remains protected elsewhere.

---

## Low-frequency journeys

Monthly or annual events need run-based or consecutive-success evidence rather than a conventional 28-day request ratio.

---

## Late data and restatement

Define when a period is provisional, when it closes, how late evidence is included, and who is notified of a material correction.

---

## Timezone boundaries

Use an explicit timezone and timestamp convention. Daylight-saving shifts and regional reporting can otherwise change denominators.

---

## Comparison and reset

Do not compare rolling and calendar results as if identical. Explain how budget reset, clustering, and prior incidents affect interpretation.

---

## Production Scenario

A monthly SLA resets at midnight on the first day, while the internal SLO uses a rolling 28-day window. One outage appears in different reporting periods and creates a dispute.

### Analysis Questions

1. What user outcome or commitment is affected?
2. Which definition, target, source, or authority is missing?
3. What can be concluded from the current evidence?
4. What cannot be concluded?
5. Who owns the decision?
6. What correction is required?
7. What evidence will prove that the correction works?

---

## Practical Output: SLO window selection record

Create a record containing:

- Decision purpose:
- Candidate windows:
- Traffic pattern:
- Seasonality:
- Low-volume treatment:
- Timezone:
- Late data:
- Closure:
- Reset effect:
- Selected window:
- Rationale:

Every target, exception, or commitment must identify its authority. Unknown evidence must remain visible with an owner and resolution date.

---

## Review Checklist

- [ ] The protected outcome or commitment is explicit.
- [ ] The SLI definition is versioned and reproducible.
- [ ] Target and time window are justified.
- [ ] Scope, segments, exclusions, and unknowns are visible.
- [ ] Measurement quality is sufficient for the decision.
- [ ] Dependencies and mismatched commitments are recorded.
- [ ] The accountable owner and approving authority are named.
- [ ] Review triggers, effective dates, and history are preserved.
- [ ] The artifact supports a real decision rather than reporting alone.

---

## Key Takeaways

- Select time windows that produce timely, stable, and decision-appropriate service-level evidence.
- A target is defensible only when its measurement, rationale, owner, and decision are explicit.
- Strong governance preserves meaning as services and data change.
- Internal objectives and external commitments must be compared field by field.
- Contractual authority remains outside a technical team acting alone.

---

## Navigation

[Previous: Setting Defensible SLO Targets](./22-Setting-Defensible-SLO-Targets.md)

[Next: Multiple SLOs, Tiers, and User Segments](./24-Multiple-SLOs-Tiers-and-User-Segments.md)

Return to the [SLIs, SLOs, and SLAs README](./README.md).

---

## Maintained by VERIQTA

SRE World is created and maintained by [VERIQTA](https://github.com/veriqta).

- Website: [veriqta.com](https://www.veriqta.com/)
- GitHub: [github.com/veriqta](https://github.com/veriqta)
- Instagram: [@veriqta](https://www.instagram.com/veriqta/)
- Medium: [veriqta.medium.com](https://veriqta.medium.com/)

