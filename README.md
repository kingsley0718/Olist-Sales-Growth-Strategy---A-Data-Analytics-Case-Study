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

cama_mesa_banho (~11,115 orders)

beleza_saude (~9,670)

esporte_lazer (~8,641)
