# SkyGeni_Saksham_Task

# SkyGeni – Sales Intelligence & Win-Rate Risk Analysis

## Objective

The goal of this assignment is to investigate why **win rates are declining despite a healthy pipeline** and to design a **data-driven insight system** that helps the CRO:
- Understand what is happening in the sales funnel
- Identify where deals are failing
- Take timely and actionable decisions to improve conversion

This project focuses on **insight, explainability, and actionability**, not just reporting.

---

## Dataset Overview

Each row in the dataset represents a single sales deal.

### Key Columns Used

- `industry` – Customer industry
- `region` – Geographic region
- `product_type` – Product sold
- `lead_source` – Origin of the lead
- `deal_stage` – Current stage in the sales funnel
- `deal_amount` – Deal value
- `sales_cycle_days` – Time taken to close the deal
- `outcome` – Final result (Won / Lost)

### Sales Funnel Assumption

Based on common B2B sales processes, the deal stages are assumed to follow this sequence:

**Qualified → Demo → Proposal → Negotiation → Closed**

This assumption is used consistently across the analysis.

---

## Part 1 – Problem Framing

### 1. What is the real business problem?

The core problem is **not lead volume**.

The pipeline shows a healthy number of deals, but a growing percentage of those deals are **not converting into wins**. This indicates:
- Inefficiencies inside the funnel
- Poor lead quality entering later stages
- Deals progressing without sufficient qualification

The CRO lacks visibility into **where the funnel breaks** and **which deals deserve attention**.

---

### 2. What key questions should the system answer for the CRO?

The system should help answer:
- Which stages of the funnel are causing the most losses?
- Which industries, regions, and lead sources underperform?
- Are sales teams spending time on deals unlikely to close?
- Which active deals are high risk and require intervention?
- Where should leadership focus resources to improve win rate?

---

### 3. What metrics matter most?

The most important metrics are:
- Win vs loss rate by deal stage
- Late-stage loss rate
- Win rate by industry, region, and lead source
- Sales cycle duration vs outcome
- Distribution of deal outcomes across funnel stages

These metrics directly explain **conversion efficiency**, not just volume.

---

### 4. Key assumptions made

- Deal stages follow a consistent logical sequence
- CRM data (stage, cycle time, outcome) is correctly updated
- Historical loss patterns are indicative of future risk
- Longer sales cycles increase loss probability

---

## Part 2 – Exploratory Data Analysis & Insights

### Insight 1 – Late-Stage Deal Leakage

A significant percentage of deals are lost **after reaching Proposal or Negotiation** stages.

**Why this matters:**  
In a healthy funnel, most losses should occur early. Late-stage losses represent wasted effort and poor qualification.

**Business implication:**  
Deals are being advanced without strong intent or buying signals.

---

### Insight 2 – Lead Source Quality Issues

Partner-sourced deals show a disproportionately high number of losses compared to wins.

**Why this matters:**  
Pipeline volume looks strong, but quality is weak.

**Business implication:**  
Lead source quality is inflating pipeline numbers without improving revenue.

---

### Insight 3 – Sales Cycle Duration as a Risk Signal

Deals with longer sales cycles show significantly lower win rates.

**Why this matters:**  
Long-running deals are not delayed wins; they are high-risk losses.

**Business implication:**  
Deal aging is an early warning signal that should trigger intervention.

---

### Key Takeaway for the CRO

The win-rate decline is driven by:
- Late-stage deal leakage
- Low-quality lead sources
- Excessive time spent on aging deals

This is a **conversion and prioritization problem**, not a volume problem.

---

## Part 3 – Deal Risk Scoring System

### Why a Risk Score?

The CRO needs a system that:
- Flags risky deals early
- Is easy to understand
- Translates directly into action

Instead of a black-box ML model, a **rule-based risk score** is used for transparency and trust.

---

### Risk Scoring Logic

Each deal starts with a risk score of **0**.

Risk points are added when known loss signals are present:

- Long sales cycle → +2
- Deal stuck in Proposal or Negotiation → +3
- Partner-sourced lead → +2

---

### Risk Categories

| Risk Score | Risk Level | Meaning |
|-----------|-----------|--------|
| 0–2 | Low | Healthy deal |
| 3–5 | Medium | Needs monitoring |
| 6+ | High | High probability of loss |

---

## Risk Analytics Summary

| Risk Level | Interpretation | Recommended Action |
|----------|---------------|-------------------|
| Low | Strong win signals | Minimal oversight |
| Medium | Early warning signs | Weekly review and coaching |
| High | Strong loss indicators | Manager / exec intervention or exit |

---

## Part 4 – System Architecture (Conceptual)

### Flow

1. CRM data ingestion  
2. Risk score computed for each active deal  
3. Deals categorized into risk buckets  
4. CRO dashboard highlights high-risk deals  
5. Action triggered based on risk level  

This allows leadership to **intervene before deals are lost**, not after.

---

## Part 5 – Reflection

### Weakest assumptions
- Risk weights are rule-based and may require tuning
- Depends on consistent CRM updates

### What could break in production
- Incomplete or delayed data
- Changes in GTM strategy or market conditions

### What I would build next
- Learn risk weights automatically from data
- Add rep-level and team-level insights
- Use NLP on call notes and deal summaries
- Track whether interventions reduce losses

---

## Final Outcome

This system:
- Explains *why* win rates dropped
- Identifies *where* the funnel leaks
- Tells leadership *what to do next*

It converts raw sales data into **actionable decision intelligence for the CRO**.

---

## Files

- `SkyGenTask.ipynb` – Full analysis, EDA, and risk scoring logic
