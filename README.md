# 📉 Telecom Customer Churn Analysis – Exploratory Data Analysis

## 📌 Project Overview
This project focuses on performing **Exploratory Data Analysis (EDA)** on a telecom customer dataset to understand customer churn behavior.  
The analysis examines customer usage patterns, billing information, service-related factors, and their relationship with churn.

The project also includes a **Power BI dashboard** for visualizing churn insights.

The dataset contains **3,333 customer records** with **11 original features**, including customer usage, service details, and churn status.

### Key Columns
- Churn  
- AccountWeeks  
- ContractRenewal  
- DataPlan  
- DataUsage  
- CustServCalls  
- DayMins  
- DayCalls  
- MonthlyCharge  
- OverageFee  
- RoamMins  

---

## Tools & Libraries Used
- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  
- Power BI  

---

## Data Loading & Inspection
- Loaded the dataset using `pandas.read_csv`
- Reviewed the first few records using `head()`
- Checked dataset structure using `info()`
- Verified data types and memory usage

---

## Data Quality Checks
- Generated descriptive statistics using `describe()`
- Checked for missing values (none found)
- Verified duplicate records (none found)

---

## Feature Engineering
- Converted column names to snake_case
- Created `churn_group` to label churned and non-churned customers
- Created derived customer segments:
  - `long_term_customer` (account weeks ≥ 120)
  - `high_value_customer` (monthly charge ≥ 60)
  - `high_complaints` (customer service calls ≥ 3)

---

## Exploratory Data Analysis
- Analyzed churn distribution using bar plots
- Examined contract renewal behavior using cross-tabulation
- Compared account weeks, monthly charges, and service calls using boxplots
- Calculated average metrics by churn group:
  - Monthly charge
  - Day calls
  - Roaming minutes
  - Overage fees
- Generated a correlation heatmap for numerical features

---

## Key Insights
- **Churn Rate:**  
  The overall churn rate is **14.49%**, indicating that the majority of customers remain with the telecom service.

- **Contract Renewal Impact:**  
  Customers who churn are significantly less likely to have contract renewals compared to non-churned customers.

- **Tenure Behavior:**  
  Churned customers generally have **lower account weeks**, suggesting that customers with shorter tenure are more likely to churn.

- **Data Plan Usage:**  
  A higher proportion of churned customers do **not** have a data plan compared to retained customers.

- **Monthly Charges:**  
  Churned customers have a **higher average monthly charge (59.19)** compared to non-churned customers (**55.82**).

- **Customer Service Calls:**  
  Customers who churn tend to make **more customer service calls**, indicating dissatisfaction or unresolved issues.

- **Usage Patterns:**  
  Average day calls are similar across churn groups, while churned customers show slightly higher roaming minutes and overage fees.

---

## Churn Metrics
- Total customers: **3,333**
- Churned customers: **483**
- Overall churn rate: **14.49%**
- Average monthly charge of churned customers: **59.19**
- Overall average monthly charge: **56.30**

## Power BI Dashboard
An interactive Power BI dashboard was created to visualize:
- Overall churn rate
- Customer segmentation
- Usage patterns by churn group
- High-value and high-complaint customer behavior

### Dashboard Preview
![Telecom Customer Churn Dashboard](Telecom%20customer%20churn%20dashboard.jpg)

---

## Conclusion
This project demonstrates a structured exploratory analysis of telecom customer churn using Python and visual storytelling through Power BI to highlight key churn drivers and customer behavior patterns.
