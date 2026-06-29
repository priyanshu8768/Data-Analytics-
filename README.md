# Data Cleaning: Medical Appointment No-Shows

## Project Overview
This repository contains the data cleaning and preprocessing tasks completed for the **Elevate Data Analyst Internship**. The objective was to transform the raw `KaggleV2-May-2016.csv` dataset into a structured, high-quality format ready for downstream analysis, visualization, and statistical modeling.

## Problem Statement
The raw dataset contained several data quality issues that hindered immediate analysis:
* **Inconsistent Date Formats:** Dates were stored as raw ISO 8601 text strings, preventing time-series analysis.
* **Categorical Noise:** Crucial columns like `No-show` and binary flags (e.g., `Scholarship`) were stored as text ("Yes"/"No"), which cannot be used for quantitative calculations.
* **Data Integrity Risks:** The dataset contained potential duplicate records and required validation to ensure logical consistency.
* **Structural Issues:** Header and data type inconsistencies threatened to cause errors during importation into BI tools like Tableau or Power BI.

## Work Performed
To address these issues, the following systematic steps were performed using **Microsoft Excel**:

| Task | Action Taken | Purpose |
| :--- | :--- | :--- |
| **Data Integrity** | Removed duplicate rows and validated missing values. | To ensure each record represents a unique, valid appointment. |
| **Date Formatting** | Converted ISO strings to `dd-mm-yyyy` via **Text to Columns**. | To enable time-based analysis and proper sorting. |
| **Categorical Encoding** | Converted `No-show` and binary flags (e.g., `Scholarship`) to `0/1` integers. | To prepare the dataset for statistical modeling and calculations. |
| **Data Type Fixes** | Standardized `Age` as an integer and verified all numeric columns. | To prevent calculation errors in future analysis. |
| **Text Standardization** | Cleaned `Gender` and `Neighbourhood` text labels. | To remove inconsistencies and ensure accurate grouping. |

## Challenges & Solutions
* **ISO Date Recognition:** Excel did not natively recognize the raw ISO format. **Solution:** Used the **Text to Columns** tool with the **YMD Date** setting to force the conversion to a valid date serial number.
* **"Ghost" Text Formatting:** Numbers appeared as text (left-aligned) even after conversion. **Solution:** Applied **Text to Columns > Finish** to trigger a refresh of the data type to "Number," ensuring all columns were right-aligned and ready for math operations.

## The Solution: Post-Cleaning Impact
By performing this cleaning process, the dataset is now "ready-to-analyze":
* **Improved Analytical Accuracy:** Findings will be more representative due to the removal of duplicates and illogical entries.
* **Enabling Quantitative Analysis:** Binary numeric encoding allows for direct correlation analysis and average rate calculations.
* **Tool-Readiness:** The dataset is now structurally consistent, allowing for seamless integration into visualization software.

## Tools Used
* **Microsoft Excel**: Data filtering, cleaning, formatting, and standardization.

---
*Completed as part of the Elevate Data Analyst Internship (MSME).*
