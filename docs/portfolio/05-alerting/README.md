# Item #4 — Alerting Based on Error Budget

## Objective
Define alerting rules aligned with Service Level Objectives (SLOs), avoiding alert fatigue and ensuring alerts represent real risk to user experience.

---

## Why Error Budget Alerting
Traditional alerting triggers on symptoms (CPU, memory, pod restarts).

SRE alerting triggers on **risk to SLO compliance**.

Alerts should fire only when:
- The service is likely to violate its SLO
- Immediate action is required

---

## SLO Reference
This alerting strategy is based on the following SLO:

- **Service:** Orders (Checkout flow)
- **SLO:** 99.5% availability over 30 days
- **Error budget:** 0.5%

---

## Burn Rate Concept
**Burn rate** measures how fast the error budget is being consumed.

A burn rate > 1 means the service is consuming error budget faster than allowed.

---

## Alerting Strategy

### Fast Burn Alert (Critical)
Triggers when the error budget is being consumed rapidly.

- **Burn rate:** > 14x
- **Window:** 5 minutes
- **Severity:** Critical

This indicates an incident requiring immediate response.

---

### Slow Burn Alert (Warning)
Triggers when error budget is being consumed steadily.

- **Burn rate:** > 2x
- **Window:** 1 hour
- **Severity:** Warning

This indicates reliability degradation that requires investigation.

---

## Operational Impact
- Critical alerts trigger immediate incident response.
- Warning alerts trigger analysis and corrective action.
- No alerts are triggered for transient or harmless failures.

---

## Lessons Learned
- Alerting on symptoms creates noise.
- Alerting on SLO risk creates focus.
- Error budgets align engineering and business priorities.
