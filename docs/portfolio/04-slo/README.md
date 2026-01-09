# Item #3 — SLO Definition (Orders / Checkout)

## Context
This document defines Service Level Objectives (SLOs) for a critical user-facing flow in the Sock Shop application.

The goal is to establish measurable reliability targets aligned with user experience, supported by observable metrics.

---

## Service Scope
**Service:** Orders  
**User flow:** Add item to cart → Checkout → Order confirmation

This flow was selected because it directly impacts revenue and user trust.

---

## SLI Definition
### Selected SLI
**Availability of the checkout flow**

Measured as the ratio of successful HTTP responses during checkout requests.

**Metric source:** Prometheus  
**Metric type:** HTTP request success rate

---

## SLO Definition
### Availability SLO
- **Target:** 99.5%
- **Time window:** 30 days

This allows approximately **3.6 hours of unavailability per month**, balancing reliability and operational cost.

---

## Error Budget
### Error Budget Calculation
- **Error budget:** 0.5%
- **Monthly error budget:** ~3.6 hours

The error budget is consumed when checkout requests fail or exceed acceptable latency thresholds.

---

## Justification
This SLO is justified based on:
- Observed behavior during failure injection (RabbitMQ outage)
- Partial service degradation without total system failure
- Business impact of checkout unavailability

The system tolerates brief degradation, but prolonged failures directly affect user experience.

---

## Operational Implications
- If error budget consumption exceeds 50%, feature releases should be slowed.
- If error budget is exhausted, reliability work takes priority over new features.

---

## Future Improvements
- Introduce latency-based SLI (p95 checkout duration)
- Create alerting rules tied to error budget burn rate
- Refine SLO based on real traffic patterns

