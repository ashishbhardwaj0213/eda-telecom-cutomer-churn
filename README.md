# 📉 Telecom Customer Churn Analysis – Exploratory Data Analysis

## 📌 Project Overview
This project focuses on performing **Exploratory Data Analysis (EDA)** on a telecom customer dataset to understand customer churn behavior.  
The analysis examines customer usage patterns, billing information, service-related factors, and their relationship with churn.

The project also includes a **Power BI dashboard** for visualizing churn insights.

---

## 📂 Dataset Description
The dataset contains **3,333 customer records** with the following features:

- `Churn`
- `AccountWeeks`
- `ContractRenewal`
- `DataPlan`
- `DataUsage`
- `CustServCalls`
- `DayMins`
- `DayCalls`
- `MonthlyCharge`
- `OverageFee`
- `RoamMins`

---

## 🛠 Tools & Technologies
- Python  
- pandas  
- numpy  
- matplotlib  
- seaborn  
- Power BI  

---

## 📥 Data Loading
The dataset is loaded using pandas and inspected for initial understanding.

```python
df = pd.read_csv("telecom_churn.csv")
🔍 Data Understanding & Quality Checks
The following checks were performed:

Dataset structure and data types using df.info()

Summary statistics using df.describe()

Missing value check

Duplicate record check

Observations:
No missing values present

No duplicate records found

Dataset includes numerical and categorical features

Churn is a binary variable (0 = No, 1 = Yes)

🧹 Data Cleaning & Transformation
Column Name Standardization
Column names were converted to snake_case for consistency.

df.columns = df.columns.str.replace(
    r'(?<!^)(?=[A-Z])', '_', regex=True
).str.lower()
Churn Group Creation
A categorical churn label was created:

df["churn_group"] = df["churn"].map({1: "Yes", 0: "No"})
📊 Exploratory Data Analysis
Churn Distribution
Bar chart used to visualize churned vs non-churned customers

Majority of customers have not churned

Contract Renewal Analysis
Crosstab analysis shows higher churn among customers without contract renewal

Account Duration
Boxplot analysis shows churned customers tend to have lower account duration

Data Plan Analysis
Customers without a data plan have a higher churn percentage

Monthly Charge Analysis
Average monthly charge:

Non-churned customers: ~55.8

Churned customers: ~59.19

Boxplots used to compare charge distribution

Customer Service Calls
Churned customers make more customer service calls on average

Call Usage
Average day calls are similar across churn groups

Call count alone does not strongly indicate churn

Feature Correlation
Correlation heatmap created for numerical features

Helps understand relationships between usage, charges, and churn

Roaming Minutes & Overage Fees
Churned customers show higher:

Roaming minutes

Overage fees

📉 Churn Rate Calculation
(churned_customers / total_customers) * 100
Churn Rate: 14.49%

Total Churned Customers: 483

🧠 Feature Engineering
Additional features were created:

Long-term customer

account_weeks >= 120

High-value customer

monthly_charge >= 60

High complaints

cust_serv_calls >= 3

These features help analyze churn patterns more effectively.

💾 Exported Dataset
The transformed dataset was saved for further analysis:

df.to_csv("transformed_Churn_file.csv", index=False)
📊 Power BI Dashboard
A Power BI dashboard was created to visualize key churn metrics, including:

Total customers

Churn rate

Churned customers

Monthly charge comparison

Data usage by churn group

High-value customer churn

Complaints vs churn

Account duration distribution

📁 Project Structure
telecom-customer-churn
│
├── telecom_customer_churn.ipynb
├── transformed_Churn_file.csv
├── customer_churn.pbix
├── images/
│   └── telecom_churn_dashboard.png
└── README.md


📌 Key Insights
Customers without contract renewal are more likely to churn

Higher monthly charges are associated with higher churn

Frequent customer service calls indicate churn risk

Long-term customers are less likely to churn
