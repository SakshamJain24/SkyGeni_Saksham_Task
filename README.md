# SkyGeni_Saksham_Task

# Sales Win-Rate Risk Intelligence System

## Objective
Despite a healthy pipeline, win rates are declining.  
This project identifies **where deals fail**, **why they fail**, and **how leadership can intervene early** using a data-driven risk scoring system.

---

## Dataset Overview
Each row represents a sales deal with:
- Business context (industry, region, product_type, lead_source)
- Funnel position (deal_stage)
- Performance signals (deal_amount, sales_cycle_days)
- Final outcome (Won / Lost)

Deal stages follow the funnel:
Qualified → Demo → Proposal → Negotiation → Closed

---

## Key Business Insights
- A large portion of losses occur in **late funnel stages**
- Partner-sourced leads inflate pipeline volume but reduce quality
- Deals with long sales cycles have a much higher loss probability

The issue is **conversion efficiency**, not lead volume.

---

## Risk Scoring Approach
Instead of a black-box model, we use an **explainable rule-based risk score** derived directly from historical loss patterns.

Each deal starts with a risk score of 0.  
Risk points are added when known loss signals are present.

### Risk Signals
- Long sales cycle
- Stalled in Proposal or Negotiation
- Partner lead source

### Risk Categories
- **Low Risk (0–2)** → Healthy
- **Medium Risk (3–5)** → Monitor
- **High Risk (6+)** → Immediate intervention

---

## Risk Analytics Summary

| Risk Level | Description | Suggested CRO Action |
|-----------|------------|----------------------|
| Low | Strong win signals | Minimal oversight |
| Medium | Early warning signs | Weekly review, coaching |
| High | Strong loss signals | Exec review or deprioritize |

---

## How This Helps the CRO
- Focus leadership attention on **high-risk, high-cost deals**
- Reduce wasted effort on deals unlikely to close
- Improve forecast accuracy
- Turn pipeline data into **actionable intelligence**

---

## Files
- `SkyGenTask.ipynb` – Full analysis, risk logic, and outputs

---

## Future Improvements
- Learn risk weights automatically from historical data
- Add rep-level risk insights
- Use NLP on call notes and deal summaries
- Track effectiveness of interventions
