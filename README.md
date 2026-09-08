# 🎵 Chinook Store: Genre Revenue & Marketing Investment Analysis

## Project Background
As a Data Analyst at **Chinook**, a global digital media retailer offering digital tracks and video content, I conducted an end-to-end sales analysis to optimise our upcoming marketing budget allocation. Operating in the digital entertainment industry, Chinook relies on a direct-to-consumer e-commerce model where customers purchase individual tracks and media items. Key performance indicators (KPIs) for our business include **Gross Revenue**, **Units Sold**, **Active Unique Customers**, and **Revenue per Customer**.

This project evaluates historical customer purchasing behaviour across media genres to answer a critical business question: *Which genre should receive primary marketing investment to maximise ROI without taking on unnecessary risk?*

Insights and recommendations are provided on the following key areas:
* **Category 1: Catalogue Volume vs. Revenue Generation**
* **Category 2: Customer Spend Normalisation (Revenue per Customer)**
* **Category 3: Unit Pricing Impact across Media Types**
* **Category 4: Sample Size Distribution & Statistical Reliability**


* Targeted SQL queries regarding various business questions can be found here:
* An interactive Tableau dashboard used to report and explore sales trends can be found here: `[Link to Tableau Public Dashboard]`

---

## Data Structure & Initial Checks
Chinook's main relational database structure consists of four primary tables used in this analysis: `invoice`, `invoice_line`, `track`, and `genre`, capturing thousands of historical sales transactions across our global customer base. A description of each table is as follows:

* **Table 1: `invoice`** — Contains high-level transaction records including invoice ID, customer ID, invoice date, and billing location.
* **Table 2: `invoice_line`** — Contains itemised line-item details for each transaction, linking individual tracks to invoices alongside unit prices and quantities purchased.
* **Table 3: `track`** — Contains song and video metadata including track name, album, media type, unit price, and genre ID.
* **Table 4: `genre`** — Master lookup table mapping genre IDs to plain-text genre names (e.g., Rock, Latin, TV Shows).
