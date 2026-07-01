# Data Visualization & Storytelling: Global Revenue & Fulfillment Efficiency

## Project Overview
[cite_start]This repository contains the visual report and interactive dashboard developed for **Task 2 of the Elevate Data Analyst Internship (MSME)**[cite: 2, 5]. [cite_start]The project bridges a programmatic data cleaning workflow (Python/Google Colab) with an enterprise business intelligence layout (Power BI) to transform raw sales logs into strategic executive insights[cite: 6, 7].

---

## Problem Statement
The raw e-commerce sales dataset (`sales_data_sample.csv`) presented several structural challenges that hindered direct business intelligence ingestion:
* [cite_start]**Format Constraints:** Dates were stored as raw text objects, breaking time-series hierarchies[cite: 10].
* **Data Caps:** The default `PRICEEACH` column was systematically capped at $100, distorting true margins and pricing structures.
* **Geographical Gaps:** High volumes of missing values in address lines and territories threatened to drop key customer demographics during spatial mapping.

---

## Data Cleaning & Engineering (Python / Google Colab)
Before building the dashboard, the raw data was preprocessed in Google Colab to enforce data integrity:
1. **Feature Engineering:** Calculated `ACTUAL_PRICE` (`sales` / `quantityordered`) to bypass the $100 system reporting cap.
2. **Missing Data Imputation:** Dropped `ADDRESSLINE2` due to an 89% missing rate; imputed missing `STATE` and `TERRITORY` markers as "N/A" and "Unknown" to preserve row completeness.
3. **Temporal Standardization:** Converted the `ORDERDATE` column into a standardized datetime format to establish robust chronological hierarchies.

---

## Dashboard Architecture & Storytelling Blueprint

### 1. Executive Summary (KPI Tiles)
* **Total Revenue:** \$10.03M — The total financial footprint of the dataset.
* **Total Volume:** 307 Unique Orders — Tracks global sales conversion depth.
* **Average Basket Demand:** 35 Units — Evaluates baseline transaction scale.

### 2. Analytical Visualizations

#### A. Temporal Seasonality (Line Chart)
* **Fields:** X-Axis: `ORDERDATE` (Year/Month Hierarchy), Y-Axis: `SALES`
* **Insight:** Solves the inventory allocation problem by mapping clear demand surges. Visual trends demonstrate massive revenue spikes every November, signaling peak holiday procurement cycles.

#### B. Category Dominance (Horizontal Bar Chart)
* **Fields:** Y-Axis: `PRODUCTLINE`, X-Axis: `SALES`
* [cite_start]**Insight:** Ranks inventory sectors without screen clutter[cite: 11]. Confirms that **Classic Cars** serves as the anchor revenue channel (\$3.92M), while categories like Trains require structural strategic reviews.

#### C. Operational Fulfillment Health (Donut Chart)
* **Fields:** Legend: `STATUS`, Values: `SALES`
* **Insight:** Isolates revenue leakage by coloring fulfillment exceptions (e.g., *Cancelled*, *Disputed*) in high-contrast alert tones, giving operations an immediate focal point for auditing friction.

---

## Dashboard Visual Interface

> [cite_start]**⚠️ NOTE TO REVIEWERS:** Below are the production screenshots of the finalized interactive Power BI report[cite: 8].

### Main Report Canvas
:::

<img width="1173" height="662" alt="image" src="https://github.com/user-attachments/assets/dee5a39d-a8a0-48f7-8eb7-e48d3949a24d" />

---

## Operational Outlier Discovery
Running a statistical check (Interquartile Range) inside Python revealed **81 transactions** that qualify as outliers, exceeding \$7,965 per line item. 

* **Business Treatment:** Rather than removing these points as errors, they were identified as **High-Value Enterprise Accounts**.
* **Dashboard Solution:** A `DEALSIZE` filter slicer was introduced to allow managers to cleanly toggle between standard retail operations (`Small`/`Medium`) and high-impact corporate accounts (`Large`).

---

## Tools & Libraries Used
* **Data Processing:** Python, Pandas, NumPy, Google Colab
* **Exploratory Outlier Graphs:** Matplotlib, Seaborn
* [cite_start]**Dashboard Design & Delivery:** Power BI Desktop / Architecture Layouts [cite: 7]

---
[cite_start]*Completed as part of the Elevate Data Analyst Internship (MSME)[cite: 2, 3].*
