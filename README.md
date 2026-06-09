# 📊 Telco Customer Churn — Exploratory Data Analysis

An end-to-end exploratory data analysis (EDA) of a telecom customer churn dataset, identifying the key factors that drive customers to leave. Built with **Python, Pandas, Matplotlib, and Seaborn**.

## 📁 Project Overview

Customer churn is when a customer cancels their subscription or stops using a service. Since acquiring new customers costs far more than retaining existing ones, understanding *why* customers churn is critical for any subscription business.

This notebook (`Customer_churn_EDA.ipynb`) walks through:

1. **Data Inspection & Cleaning**
   - Loaded the dataset and inspected structure with `info()`, `describe()`, and null checks
   - Fixed `TotalCharges`: blank strings replaced with `0` and converted from object to float
   - Verified no duplicate records or duplicate `customerID`s
   - Converted `SeniorCitizen` from `0/1` to readable `no/yes` labels

2. **Univariate & Bivariate Analysis**
   - Overall churn distribution (count plot + pie chart)
   - Churn by demographics: gender, senior citizen status
   - Churn by tenure (histogram)
   - Churn by contract type
   - Churn across 9 service features (3×3 subplot grid)
   - Churn by payment method

## 🔍 Key Insights

| Factor | Finding |
|---|---|
| **Overall churn rate** | ~26.5% of customers have churned |
| **Senior citizens** | Churn at a noticeably higher *rate* than younger customers |
| **Gender** | Little to no effect on churn |
| **Tenure** | Long-tenured customers stay; churn is concentrated in customers with short tenure |
| **Contract type** | Month-to-month contracts churn far more than 1-year or 2-year contracts |
| **Internet service** | Fiber optic users churn the most (~42%); DSL (~19%); no internet (~7%) |
| **Support add-ons** | Customers *without* Online Security, Tech Support, Online Backup, or Device Protection churn at roughly double the rate of those with them |
| **Streaming TV / Movies & Multiple Lines** | Weak churn predictors — churn rates are similar with or without |
| **Payment method** | Electronic check users are the most likely to churn |

## 🧾 Conclusions

1. **Fiber optic internet** is associated with the highest churn — likely tied to price or service quality.
2. **Support and protection add-ons** strongly correlate with retention; bundling these may reduce churn.
3. **Month-to-month contracts** and **electronic check payments** are high-risk segments worth targeting with retention offers.
4. **New customers (low tenure)** are the most vulnerable — early engagement matters most.

## 🛠️ Tech Stack

- Python 3
- Pandas / NumPy — data cleaning & manipulation
- Matplotlib / Seaborn — visualization

## 🚀 How to Run

```bash
pip install pandas numpy matplotlib seaborn
jupyter notebook Customer_churn_EDA.ipynb
```

Place `Customer Churn.csv` in the same directory as the notebook before running.

## 📌 Next Steps could be 

- Encode categorical features and build predictive models (Logistic Regression, Random Forest, XGBoost)
- Evaluate feature importance to confirm the EDA findings
- Build a churn-risk scoring system for proactive retention
