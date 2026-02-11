# SkyGeni_Saksham_Task

# SkyGeni – Sales Intelligence Challenge  
## Data-Driven Insight System for CRO Decision-Making

---

# Part 1 – Problem Understanding & Framing

## 1. What is the real business problem?

The core business problem is **declining win rates despite a healthy-looking sales pipeline**.

Although lead volume and pipeline size appear strong, a significant portion of deals are failing to convert into wins. This indicates that the issue is **not lead generation**, but rather:

- Poor qualification discipline  
- Late-stage deal leakage  
- Pipeline quality inconsistencies  
- Inefficient allocation of sales effort  

The CRO lacks visibility into where conversion breaks down and what actions should be taken to improve outcomes.

---

## 2. What key questions should an AI-driven system answer?

The system should help the CRO answer:

- Which stages of the funnel contribute most to losses?
- Are certain industries or regions underperforming?
- Which lead sources degrade pipeline quality?
- Which deals are currently high-risk?
- Where should leadership intervene to prevent revenue leakage?

---

## 3. What metrics matter most for diagnosing win-rate issues?

Key diagnostic metrics:

- Win/Loss ratio across funnel stages  
- Late-stage loss ratio  
- Win rate by industry and region  
- Win rate by lead source  
- Sales cycle duration vs outcome  
- Deal aging compared to historical benchmarks  

These metrics isolate conversion inefficiencies rather than focusing on surface-level pipeline volume.

---

## 4. What assumptions are made about the data or business?

- Funnel stage order is assumed to be:  
  **Qualified → Demo → Proposal → Negotiation → Closed**
- Deal stage updates are assumed to be accurate and timely  
- Historical performance patterns are assumed to reflect near-term future behavior  
- Deals are evaluated independently  

---

# Part 2 – Exploratory Data Analysis (EDA) & Key Insights

## Insight 1 – Late-Stage Leakage

Approximately **39% of lost deals fail in Proposal or Negotiation stages.**

This indicates:
- Weak qualification early in the funnel  
- Advancement of deals without sufficient validation  
- High resource wastage on deals that should have been filtered earlier  

---

## Insight 2 – Sales Cycle Duration as a Risk Signal

Win rate declines significantly as sales cycle length increases.

- Deals closed within shorter cycles show the highest win rates  
- Long-running deals are more likely to end in losses  

Conclusion:  
Deal aging is a strong early-warning signal.

---

## Insight 3 – Pipeline Quality Varies by Source and Segment

- Partner-sourced leads have lower conversion quality  
- Certain industry–region combinations outperform others  
- Loss patterns are segment-specific, not uniform across the business  

Conclusion:  
Win-rate decline is not global — it is concentrated.

---

# Part 3 – Risk Metric Design

## Why a Risk Metric?

Instead of deploying a black-box model, a **transparent risk scoring framework** enables:

- Interpretability  
- Immediate operationalization  
- Executive trust  
- Direct actionability  

Each deal begins with a **risk score of 0**.  
Risk points are added based on historically observed loss patterns.

---

## Risk Metric Definition

| Risk Signal | Condition | Risk Points |
|-------------|----------|-------------|
| Deal Aging | Sales cycle exceeds median duration | +2 |
| Late-Stage Stagnation | Deal in Proposal or Negotiation | +3 |
| Extended Negotiation | Negotiation exceeds expected duration | +5 |
| Weak Lead Source | Partner / historically low-conversion source | +2 |
| Low-Performing Segment | Industry or region with below-average win rate | +1 |

---

## Risk Categories

| Risk Score | Category | Meaning |
|------------|----------|----------|
| 0–2 | Low Risk | Healthy deal, minimal oversight |
| 3–5 | Medium Risk | Requires monitoring and coaching |
| ≥ 6 | High Risk | Immediate intervention required |

---

# Part 4 – System Output & CRO Enablement

## What the CRO Receives

- Ranked list of deals by risk score  
- Risk category (Low / Medium / High)  
- Key risk drivers per deal  
- Clear recommended actions  

This transforms raw pipeline data into decision-ready intelligence.

---

## Actionable Recommendations

### High-Risk Deals
- Mandatory manager and executive review  
- Revalidate decision authority, urgency, and budget  
- Decide: strategic intervention or deprioritization  

### Medium-Risk Deals
- Weekly checkpoints  
- Enforce clear next-step commitments  
- Targeted coaching  

### Low-Risk Deals
- Maintain momentum  
- Avoid unnecessary interference  

---

## Pipeline-Level Strategic Actions

- Enforce stricter exit criteria before Proposal and Negotiation  
- Tighten partner lead qualification  
- Auto-flag aging deals  
- Discount high-risk deals in revenue forecasting  

---

# Part 5 – Reflection & Limitations

## Weakest Assumptions

- Risk thresholds depend on historical stability  
- CRM data is assumed to be accurate and complete  

---

## What Could Break in Production

- Inconsistent CRM updates  
- Market or GTM strategy changes  
- Poorly tuned alerts causing fatigue  

---

## Future Enhancements

- Learn risk weights automatically from historical data  
- Add rep-level and team-level insights  
- Incorporate qualitative signals using NLP  
- Track whether interventions reduce loss rates over time  

---

# Final Executive Summary

The win-rate decline is **not a volume problem**.

It is driven by:

- Late-stage leakage  
- Aging high-risk deals  
- Inconsistent pipeline quality  

This system converts pipeline data into **interpretable, operational, and immediately actionable sales intelligence for the CRO.**

# How to Run the Project

## 1. Clone the Repository

```bash
git clone <your-repository-link>
cd <repository-folder>
