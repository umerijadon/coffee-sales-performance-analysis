# Coffee Sales Performance Dashboard & Strategic Analysis

An interactive Excel dashboard and executive report analyzing four years of retail coffee transaction data (2019–2022), built to answer commercial, operational, and forecasting questions at an executive level — not just "what happened," but "what should we do about it."

**Tools:** Microsoft Excel · PivotTables · INDEX/MATCH · XLOOKUP · Interactive Slicers · Data Modeling

---

## Overview

This project analyzes 957 transactions across a three-table relational dataset (orders, customers, products) to evaluate product performance, geographic concentration, loyalty program effectiveness, and growth trajectory for a specialty coffee retailer. The deliverable is a live, filterable Excel dashboard paired with a written executive report covering commercial insights, technical methodology, and strategic recommendations.

| Metric | Value |
|---|---|
| Aggregate Sales | $45,134.25 |
| Total Orders | 957 |
| Average Order Value | $47.16 |
| Loyalty Program Share of Revenue | 46.3% |
| Unique Customers | 913 |

---

## The Business Problem

The brief called for executive-level analysis, not descriptive reporting — questions like *why* the US outperforms European markets, whether 2022 was on pace to beat prior years, which customer segments deserve investment, and how inventory/pricing decisions should shift in response. The goal was to move beyond "what are the numbers" into "what should leadership decide."

---

## Dashboard

The dashboard is a single interactive view built around three linked visuals and three slicers (Roast Type, Package Size, Loyalty Status) that filter all charts simultaneously:

- **Total Sales Over Time** — monthly sales trend, 2019–2022, by coffee varietal
- **Sales by Country** — geographic revenue concentration
- **Top 5 Customers** — highest lifetime spenders

> 📸 *Add a screenshot of the dashboard here:* `![Dashboard](assets/dashboard-screenshot.png)`

---

## Data Architecture

Built on a three-layer relational structure rather than flat, hardcoded data:

- **`orders`** (957 line items) — transactional ledger
- **`customers`** (913 records) — customer master data
- **`products`** (48 SKUs) — product master data with pricing

Key techniques:
- **XLOOKUP** to pull customer name, email, and country dynamically from the customer master table
- **INDEX/MATCH** (rather than VLOOKUP) to resolve coffee type, roast, size, and price from the product table
- Nested **IF** logic to decode categorical shorthand (e.g., `"Rob"` → `"Robusta"`, `"M"` → `"Medium"`)
- **PivotTables** driving all three dashboard charts, connected to slicers for real-time filtering
- Zero formula errors across ~15,800 populated cells in the orders table

---

## Key Insights

**Geographic concentration:** The US generates 78.96% of total revenue ($35,638.89), with Ireland (14.84%) and the UK (6.20%) representing early-stage, underdeveloped markets — a clear expansion opportunity rather than a mature one.

**Product mix:** Demand is balanced across four varietals, with Excelsa (27.27%) and Liberica (26.71%) narrowly outperforming Arabica (26.07%) and Robusta (19.95%). Light roasts lead all roast levels at 38.45% of revenue.

**2022 run-rate:** Based on the seven complete months of 2022 data (Jan–Jul, $6,819.19), the annualized run-rate projects to **~$11,690** — a decline from 2021's $13,766 and roughly flat against 2019–2020. This reframes 2022 from "growth story" to "watch closely," and directly motivates the marketing and expansion recommendations below.

**Loyalty program, re-examined:** The headline number (46.3% of revenue from loyalty members) looks like an unambiguous win — but a deeper look complicates that. Loyalty members actually spend **less** on average per customer ($47.22) than non-members ($51.52), and repeat purchases are rare across the board (only 2.7% of customers placed more than one order). This means the highest-leverage fix isn't necessarily acquiring more loyalty members — it's understanding why loyalty isn't yet converting into higher spend or repeat behavior.

---

## Strategic Recommendations

1. **Targeted European expansion.** Light roast Excelsa and Liberica already lead demand and align with Western European specialty coffee preferences — prioritize marketing spend in Ireland and the UK rather than further US saturation.
2. **Investigate loyalty program economics before scaling it.** Given loyalty members currently show *lower* average spend than non-members, test incentive structures (e.g., spend-threshold rewards) rather than simply growing membership count.
3. **Reallocate inventory toward demand.** Shift ~15–20% of Robusta purchasing capital toward Excelsa and Liberica, which show stronger revenue performance per unit.

---

## Limitations & Assumptions

- **Customer segmentation (household vs. commercial):** Order sizes (0.2–2.5kg) and quantities (1–6 units per line item) are consistently retail-scale across the dataset, with no signal of bulk/wholesale purchasing behavior. Rather than force a household/commercial split the data doesn't support, this analysis treats all customers as individual retail buyers and segments by spend tier and loyalty status instead.
- **2022 forecast** is a simple run-rate projection (7-month average × 12) and does not account for seasonality between January–August vs. September–December, since no historical September–December 2022 data exists yet to validate a seasonal model.

---

## Author

**Jadon Umeri**  
Data Analyst focused on business analytics, customer insights, revenue optimization, and data-driven decision-making.
