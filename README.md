# Olist E-commerce RFM Analysis & 20% Revenue Growth Plan
## Overview
This project analyzes the Olist e-commerce dataset (Brazil) to identify revenue drivers and design actionable strategies to grow revenue by ≥20%. I built an RFM segmentation in Power BI, explored temporal and geographic purchasing patterns, and translated the findings into a prioritized growth plan (campaigns, bundles, timing, and city targeting).

**Why it matters**: Most customers purchase only once and the bulk of revenue sits with “at-risk” and “low-frequency” cohorts. Knowing who to target, when, and with what offer is the fastest way to lift revenue.

## Business Goal
**Increase revenue by at least 20%.**

I translate analytical findings into concrete actions (reactivation, cross-sell, city-level targeting, timing-based promos, and review/delivery fixes).


## Dataset
**Source:** Olist Brazilian E-commerce Public Dataset (Kaggle)

**Tables used:** customers, orders, products, order_reviews, (plus date/time fields derived in Power BI), order_items, order_payments,  geolocation, sellers.

**Rows (approx):** ~100k orders, ~96k customers


## Cleaning & prep (Power Query):

Fixed data types (dates/times, numeric).

Created Order Status from delivery timestamps.

Handled missing/unknown product categories (kept as “Unknown” for honesty).

Built a clean Date table for time intelligence.


## Tools & Skills
Power BI (DAX, Model, Visuals), Power Query

Segmentation (RFM), Cohort & Time Analysis

KPI design, Business storytelling, Marketing strategy.


## Metrics & DAX (high level)
Total Revenue: SUM(payment_value)

Customers: DISTINCTCOUNT(customer_unique_id)

Orders: DISTINCTCOUNT(order_id)

AOV: DIVIDE([Total Revenue], [Orders])

Frequency (per customer): count of orders per customer_unique_id

Recency (days): days since each customer’s last purchase vs. model “As-Of” date

Monetary (per customer): total payment_value per customer_unique_id


## Buckets:
Recency: Recent (0–30), Medium (31–90), Old (>90)

Frequency: High (>3), Medium (2–3), Low (1)

Monetary: Low/Med/High via 25th/75th percentiles



## RFM Score:
Concatenate R(1–3), F(1–3), M(1–3) → RFM Segment (Champions, At Risk, Need Attention, Hibernating, Promising, Potential Loyalist, Big Spenders, About to Sleep, etc.)

**Note:** RFM is implemented as calculated columns on a Customer-level table so segment membership stays stable in visuals and can be sliced.


## Key Insights (From my Power BI dashboard)

**Company-level KPIs**

**Total revenue:** ~R$16M

**Customers:** ~96.1k

**Orders**: ~99.4k

**AOV:** ~R$161.00 



## Product & Category

**Top categories by orders:**

**cama_mesa_banho** (~11,115 orders)

**beleza_saude** (~9,670)

**esporte_lazer** (~8,641)

“Unknown” category still present (≈1,586 orders) — retained to avoid biasing results.


## Reviews

**Review score =** 5 dominates (≈57,328 orders), then 4, then 1, 3, 2.

**→ Service & delivery still matter:** many low scores (1–2) remain and correlate with delays/cancellations.


## When customers buy (all customers)
**Month:** August peaks (12,158 orders), December is lowest (6,309).

**Weekday:** Monday (18,399), then Tuesday (18,237); Saturday lowest (~12,168).

**Hour:** Peak at 10:00 (~11,993), then 09:00, 11:00.

**AM vs PM:** ~91.6% AM, ~8.4% PM.


## Where customers buy

**Cities (Top):** São Paulo (15,618 customers), Rio de Janeiro (6,923) dominate.


## RFM Distribution (all customers)

**Frequency buckets:** Low ~96.88% (≈93,099), Medium ~3.07% (≈2,948), High ~0.05% (≈49).

**Recency buckets:** Old >90 days dominate (≈87–90k), Medium ≈9.6k, Recent ≈single digits.

**Monetary buckets:** Low ~95% (≈91,603), Medium ≈3,274, High ≈1,219.


## Segment Deep Dives (highlights)


### At Risk


**Revenue:** ~R$10M; ~81k customers; AOV ~R$124.8

Buy mostly Mon–Tue, AM, and 10:00 hour; São Paulo leads.

Top categories: cama_mesa_banho, beleza_saude.



### Potential Loyalists


**Revenue:** ~R$3M; ~3.8k customers

AM 91.9%; Tuesday strongest; 10:00 best hour.

Skew to medium/high monetary buckets.

**Top:** relogios_presentes, informatica_acessorios.



### Big Spenders


Very small base (≈15 customers, 102 orders), high frequency, AM ~90%.

**Top:** cama_mesa_banho, moveis_decoracao.



### Need Attention


~R$692k revenue, ~3.3k orders; heavy AM & weekday bias (Tue/Thu), 10:00 peak.

Monetary mostly Low (76%), but reachable.



### Hibernating


~R$792k revenue, 1.9k customers; all low frequency, recency = Medium (31–90).

Monetary mostly Low (79%) → re-activation target.



### Promising


Small & newish: Aug and AM heavy; good for nurturing into Loyalists.



## What This Means (Business Interpretation)

**Massive long-tail:** Most customers buy once. Revenue growth will come from reactivation + second purchase (At Risk, Hibernating, Need Attention), while nurturing small high-value cohorts (Potential Loyalists, Big Spenders) yields disproportionate lift.

**Time matters:** AM (9–11am) and Mon–Tue are prime windows to place promos and triggered campaigns.

**Geo concentration:** São Paulo and Rio deserve budget priority; replicate winning playbooks to next-tier cities.

**Category levers:** cama_mesa_banho and beleza_saude drive demand → bundle/cross-sell and protect delivery quality to reduce low reviews.



## Strategy to +20% Revenue (90-Day Plan)

**Win back “At Risk” & “Hibernating” (reactivation engine)**

**Offer:** category-based bundles (e.g., cama_mesa_banho + utilidades_domesticas), “come back” vouchers (R$ off next order, 7-day expiry).

**Timing:** Mon–Tue, 9–11am (matches observed peaks).

**Channels:** Email/SMS + WhatsApp flows; cart remarketing.

**Goal:** convert 3–5% of At Risk in 90 days → ~R$1.2–1.6M lift (conservative).



**Nurture “Potential Loyalists” → repeat & upsell**

**Offer:** complementary accessories (informatica_acessorios), loyalty points, free shipping thresholds.

**Timing:** trigger post-purchase day 7 & day 30; AM.

**Goal:** +15–20% repeat rate in this cohort → ~R$0.4–0.6M lift.


**Protect & grow “Big Spenders”**

**Offer:** VIP service (priority support), early access, guaranteed delivery windows, premium bundles in moveis_decoracao/cama_mesa_banho.

**Goal:** +2 purchases per VIP across quarter → small base, high margin lift.



**City playbooks**

**São Paulo & Rio:** increase bid caps & email cadence during Aug/May; mono-product landing pages for top categories; localized creatives.

**Next 8 cities (top-10):** replicate with 70% of São Paulo’s bid/discount.



