# 🎵 Chinook Store: Genre Revenue & Marketing Investment Analysis

## Project Background
As a Data Analyst at **Chinook**, a global digital media retailer offering digital tracks and video content, I conducted an end-to-end sales analysis to optimise our upcoming marketing budget allocation. Operating in the digital entertainment industry, Chinook relies on a direct-to-consumer e-commerce model where customers purchase individual tracks and media items. Key performance indicators (KPIs) for our business include **Gross Revenue**, **Units Sold**, **Active Unique Customers**, and **Revenue per Customer**.

This project evaluates historical customer purchasing behaviour across media genres to answer a critical business question: *Which genre should receive primary marketing investment to maximise ROI without taking on unnecessary risk?*

Insights and recommendations are provided on the following key areas:
* **Category 1: Catalogue Volume vs. Revenue Generation**
* **Category 2: Customer Spend Normalisation (Revenue per Customer)**
* **Category 3: Unit Pricing Impact across Media Types**
* **Category 4: Sample Size Distribution & Statistical Reliability**


* Targeted SQL queries regarding various business questions can be found here: [SQL queries](SQL)
---

## Data Structure & Initial Checks
Chinook's main relational database structure consists of four primary tables used in this analysis: `invoice`, `invoice_line`, `track`, and `genre`, capturing thousands of historical sales transactions across our global customer base. A description of each table is as follows:

* **Table 1: `invoice`** — Contains high-level transaction records including invoice ID, customer ID, invoice date, and billing location.
* **Table 2: `invoice_line`** — Contains itemised line-item details for each transaction, linking individual tracks to invoices alongside unit prices and quantities purchased.
* **Table 3: `track`** — Contains song and video metadata including track name, album, media type, unit price, and genre ID.
* **Table 4: `genre`** — Master lookup table mapping genre IDs to plain-text genre names (e.g., Rock, Latin, TV Shows).

---

## Executive Summary

### Overview of Findings
An initial surface-level view suggests doubling down entirely on high-volume music categories like Rock due to overwhelming gross revenue dominance. However, deeper multi-variable analysis reveals that niche genres yield high revenue per customer primarily due to higher unit prices, but suffer from low sample sizes. For marketing leadership, **Rock remains the safest high-yield investment ($826.65 total revenue, $14.01 spend/customer across 59 active buyers)**, while categories like **TV Shows ($1.99 unit price, 19 buyers)** should be treated as experimental testing grounds rather than core budget priorities.

---

## Insights Deep Dive

### Category 1: Catalogue Volume vs. Revenue Generation
1. **Rock Dominates Gross Revenue:** Rock generated **$826.65** in gross revenue, accounting for the single largest share of total store earnings across all categories.
2. **Volume-Driven Performance:** Rock leads total units sold with **835 tracks purchased**, demonstrating sustained customer volume rather than isolated large transactions.
3. **Broad Customer Reach:** A total of **59 unique customers** purchased Rock tracks, representing near-total penetration across Chinook's entire active buyer base.
4. ** Catalogue Inventory Bias:** Rock also possesses the largest catalogue availability in our database. Because inventory volume naturally inflates total sales, gross revenue alone cannot be the sole deciding metric for future marketing spend.

![Alt text](https://github.com/AmandaSibanda/Chinook-Store-Data-Analytics/blob/9c08c91e68f392beb574394075b7521016eb183f/chinook_screenshots/Screenshot%202026-09-10%20123451.png)

---

### Category 2: Customer Spend Normalisation (Revenue per Customer)
1. **Rock Delivers Highest Per-Customer Yield:** Normalising sales by unique customer count shows Rock customers spend an average of **$14.01 per buyer**, leading all categories.
2. **Solid Performance from Secondary Genres:** **Latin ($7.49/customer)** and **Metal ($8.14/customer)** maintain strong per-customer yield alongside consistent sales volume.
3. **Niche Category Outliers:** Non-music categories like **TV Shows** generate **$4.92 per customer**, outperforming several traditional music genres despite serving far fewer total buyers.
4. **Distinction Between Reach and Value:** Measuring revenue per customer prevents volume bias and highlights smaller categories that punch above their weight on a per-buyer basis.

![Alt text](https://github.com/AmandaSibanda/Chinook-Store-Data-Analytics/blob/4d50659742d807dd1a94b88afb8fc845cf17327d/chinook_screenshots/Screenshot%202026-09-10%20122353.png)

---

### Category 3: Unit Pricing Impact across Media Types
1. **Dual Pricing Structure:** Standard audio music tracks sell uniformly at **$0.99**, whereas video and television content sells at **$1.99** per item.
2. **Price Point Sensitivity:** Higher per-customer spend in video categories is driven primarily by a **100% price premium ($1.99 vs $0.99)** rather than higher transaction frequency per user.
3. **Volume Disparity:** Despite higher unit prices, video content shows significantly lower overall unit volume (**65 units sold for TV Shows** vs **835 units for Rock**).
4. **Margin vs. Volume Tradeoff:** High unit price items generate attractive revenue per transaction but face lower customer adoption across our current user base.

![Alt text](https://github.com/AmandaSibanda/Chinook-Store-Data-Analytics/blob/7a72e9934a5a8f7fa078ef257b77643aa5365df2/chinook_screenshots/Screenshot%202026-09-10%20122353.png)

---

### Category 4: Sample Size Distribution & Statistical Reliability
1. **Low Sample Threshold Identified:** Several high-performing niche genres fall below our statistical reliability threshold of 25 unique customers.
2. **TV Shows Sample Size Risk:** TV Shows reflects transactions from only **19 unique customers**, meaning performance metrics are heavily susceptible to individual outlier purchases.
3. **Extreme Niche Categories:** Categories such as Comedy and Drama contain under **5 unique customers**, making any generalized conclusions statistically unreliable.
4. **Risk Mitigation:** Identifying small sample sizes prevents the business from over-allocating capital to categories that lack broad market validation.


---

## Recommendations

Based on the insights and findings above, I recommend the **Marketing and Executive Leadership Team** consider the following:

1. **Primary Budget Allocation (Rock):** Commit **75–80% of the primary acquisition budget to Rock**. Rock holds the largest market reach (59 customers), highest total revenue ($826.65), and highest per-customer yield ($14.01), making it our lowest-risk, highest-return asset.
2. **Controlled A/B Testing (TV Shows):** Reserve a **10–15% experimental budget** to test campaign messaging for TV Shows. Higher unit margins ($1.99) present an upside opportunity, but small sample sizes (19 customers) require validation before committing scaling capital.
3. **Core Retargeting (Latin & Metal):** Maintain baseline retargeting campaigns for **Latin and Metal**, which consistently generate solid volume ($382.14 and $374.22) across reliable customer bases (51 and 46 buyers).
4. **Price-Sensitivity Monitoring:** Conduct a pricing elasticity study before expanding $1.99 video inventory to evaluate whether higher prices depress overall customer purchase frequency.
5. **Inventory Diversification:** Re-evaluate catalogue sourcing to ensure marketing campaigns in niche genres are backed by sufficient track depth before launching new customer acquisition drives.

---

## Assumptions and Caveats

Throughout the analysis, multiple assumptions were made to manage challenges with the dataset:

* **Assumption 1 (Static Snapshot):** The database provides a static snapshot of historical purchases. It is assumed these historical purchasing patterns reflect current customer demand.
* **Assumption 2 (Exclusion of Acquisition Costs):** Customer Acquisition Cost (CAC) and operational margin data were unavailable; all evaluations are based on gross revenue rather than net margin.
* **Assumption 3 (Synthetic Data Scale):** Due to the synthetic nature of the Chinook dataset, sample sizes for minor genres were capped at low thresholds and required explicit `HAVING count(distinct customer_id) < 25` filtering to isolate statistical noise.
