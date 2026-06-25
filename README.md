# Project: Travel, Tourism & Hospitality - Customer Retention and Dynamic Pricing Analysis

## Executive Summary
This project addresses revenue leakage in the hospitality sector caused by unoptimized pricing and unpredictable customer cancellations. Our goal is to leverage historical booking datasets to identify key drivers of churn and provide actionable insights for a dynamic pricing engine.

## Methodology
The project follows a structured 4-week engineering roadmap:
* **Week 1: Data Acquisition & Cleaning:** Handled missing values, removed duplicates, and engineered new time-series features.
* **Week 2: EDA & Statistical Testing:** Utilized correlation matrices and bivariate analysis to identify the relationship between ADR, lead time, and cancellation rates.

## Key Findings (EDA)

* **Correlation Drivers:** Heatmap analysis identified key churn predictors and their relationships.
![Correlation Heatmap](Images/Correlation_Heatmap.png)

* **Price Sensitivity:** High Average Daily Rates (ADR) correlate positively with increased cancellation rates.
![ADR vs Cancellation Analysis](Images/ADR_vs_Cancellations.png)

* **Channel Volatility:** The Online Travel Agent (OTA) segment exhibits the highest cancellation risk, while Corporate bookings remain the most stable.
![Market Segment Cancellation Rate](Images/Cancellation_Rate_by_Segment.png)

## How to Reproduce
1. Clone the repository.
2. Ensure you have the `requirements.txt` installed.
3. Run the notebooks in order: `1_EDA_and_Cleaning.ipynb` followed by `2_EDA_and_Statistical_Testing.ipynb`.