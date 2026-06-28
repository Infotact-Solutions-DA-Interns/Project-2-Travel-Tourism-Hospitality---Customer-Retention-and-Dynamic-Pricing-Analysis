# Project: Travel, Tourism & Hospitality - Customer Retention and Dynamic Pricing Analysis



## Summary of the Project

This project is an end-to-end data pipeline, predictive machine learning model, and interactive dashboard designed to tackle a critical challenge in the hospitality industry: booking cancellations. By analyzing over 87,000 historical booking logs, this solution identifies the core drivers of customer churn, predicts at-risk revenue, and provides actionable intelligence to drive a dynamic pricing strategy.


## Live Dashboard Link



## Project Overview

In the travel and hospitality sector, last-minute cancellations represent a massive source of revenue leakage, often forcing hotels into reactionary pricing strategies. This project transitions the business from a reactive state to a proactive one. By cleaning and analyzing historical reservation data, we uncovered behavioral patterns that lead to churn and built a predictive engine that flags high-risk bookings before the revenue is lost.


## Business Objectives

* **Mitigate Revenue Leakage:** Accurately predict booking cancellations to allow for proactive customer retention efforts.
* **Optimize Pricing:** Identify how Average Daily Rate (ADR) and lead time impact customer churn to inform dynamic pricing models.
* **Customer Segmentation:** Pinpoint high-value, reliable customer segments versus high-risk booking channels.
* **Operational Efficiency:** Provide management with clear, actionable metrics to optimize room allocation and marketing spend.


## Dataset Overview

* **Size:** 87,396 clean records across 32 analytical features.
* **Key Dimensions:** Booking status, lead time, arrival dates, demographic data (country, adults/children), market segment, deposit type, Average Daily Rate (ADR), and special requests.
* **Target Variable:** is_canceled (Binary: 1 for Canceled, 0 for Not Canceled).


## Dashboard Architecture

* **ETL Pipeline:** Built in Python (Pandas) to handle missing values, drop duplicates, remove data leakage columns, and engineer time-series features.
* **Data Modeling:** Star schema architecture connecting the centralized Fact Table (Bookings) to associated Dimension Tables (Customers, Dates, Property details).
* **Predictive Engine:** Logistic Regression model integrated to assign a "Churn Risk Score" to incoming data.


## Methodology: A Four-Week Project Lifecycle

This project was executed in a structured, four-phase approach, transitioning from raw data processing to predictive analytics and final stakeholder visualization:

### Week 1: Data Engineering & Preprocessing

* **Data Acquisition & Cleaning:** Imported over 87,000 raw booking logs using Python and Pandas. 
* **Data Integrity:** Handled missing values across key demographic columns (Country, Children, Agent IDs) and systematically removed duplicate entries to prevent analytical bias.
* **Version Control:** Established a robust Git workflow, tracking all foundational data transformations under the `dev-data-cleaning` branch.

### Week 2: Exploratory Data Analysis (EDA) & Statistical Testing

* **Pattern Recognition:** Conducted comprehensive univariate and bivariate analysis to uncover historical booking trends and seasonal demand.
* **Identifying Churn Drivers:** Utilized correlation mapping and visual analytics (Matplotlib/Seaborn) to identify key variables impacting cancellations, revealing high risk in OTA channels and price-sensitive bookings.
* **Feature Engineering:** Engineered new time-series metrics and categorized data to prepare the dataset for machine learning consumption.

### Week 3: Predictive Modeling & Machine Learning

* **Preventing Data Leakage:** Identified and dropped retrospective columns (e.g., `reservation_status`, `reservation_status_date`) to ensure the model could not "cheat" by looking at the future.
* **Addressing Dimensionality & Imbalance:** Applied One-Hot Encoding to categorical variables (reducing text columns to 76 numerical features). Overcame severe target class imbalance by utilizing `StandardScaler` and applying balanced class weights.
* **Model Training & Evaluation:** Built and tuned a Logistic Regression classifier, ultimately achieving a **77% recall rate** for predicting actual cancellations. Extracted feature coefficients to translate mathematical weights into actionable business drivers.

### Week 4: Business Intelligence & Dashboard Development

* **Data Modeling:** Imported the cleaned, scored dataset into the BI visualization tool, establishing a Star Schema architecture connecting the central Fact table with associated Dimension tables.
* **UI/UX Design:** Designed a multi-page interactive dashboard tailored for non-technical hotel executives.
* **Metric Calculation:** Developed custom DAX/Calculations to track live KPIs including Total Revenue, Churn Probability, and Operational Efficiency, effectively turning historical data into a dynamic pricing tool.


## Key Findings (EDA)

* **Correlation Drivers:** Heatmap analysis identified key churn predictors and their relationships.
![Correlation Heatmap](Images/Correlation_Heatmap.png)

* **Price Sensitivity:** High Average Daily Rates (ADR) correlate positively with increased cancellation rates.
![ADR vs Cancellation Analysis](Images/ADR_vs_Cancellations.png)

* **Channel Volatility:** The Online Travel Agent (OTA) segment exhibits the highest cancellation risk, while Corporate bookings remain the most stable.
![Market Segment Cancellation Rate](Images/Cancellation_Rate_by_Segment.png)


## Tools & Technologies Used

* **Data Engineering & ML:** Python, Pandas, Scikit-learn, NumPy.
* **Version Control:** Git, GitHub (dev-data-cleaning branch workflow).
* **Development Environment:** Jupyter Notebooks, VS Code.
* **Visualization:** Power BI


## Business Impact

* Engineered a Logistic Regression predictive model utilizing balanced class weights to successfully identify 77% of all true cancellations.
* Translated algorithmic coefficients into transparent business intelligence, proving that extended lead times drive churn, while customer engagement (parking, special requests) guarantees stays.
* Provided a data-backed foundation for Infotact Solutions to transition to a dynamic pricing model.


## Key Learning

* **Data Leakage:** Successfully identified and removed features (reservation_status, reservation_status_date) that would have caused the machine learning model to cheat.
* **Class Imbalance:** Overcame heavy target variable imbalance by applying Standard Scaling and penalizing minority class misclassifications, improving recall from 43% to 77%.
* **High Cardinality:** Prevented the "Curse of Dimensionality" during One-Hot Encoding by strategically dropping unneeded text columns, reducing the feature space from 1,972 to a highly efficient 76 columns.


## Future Enhancements

* **Real-Time API Integration:** Connecting the predictive model directly to the hotel's booking engine to score cancellation risk the second a reservation is made.
* **Automated Retention Triggers:** Using the risk scores to automatically trigger targeted discounts or confirmation emails to at-risk guests.
* **Advanced ML Models:** Exploring Random Forest or XGBoost algorithms to further optimize the Precision-Recall tradeoff.


## Author
**Kunal Nilkanth Patle**
Aspiring Data Business Analytics
🔗https://www.linkedin.com/in/kunal-patle-b687a716a/
