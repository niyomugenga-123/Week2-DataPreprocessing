# Week 2: Data Preprocessing & Feature Engineering for Machine Learning

**Project:** Telco Customer Churn - Data Preprocessing Pipeline  
**Program:** AnalystLab Africa Machine Learning Internship  
**Author:** Mae (Marie Claire Niyomugenga)  
**Date:** August 2026

---

## 📋 Project Overview

This project focuses on **data preprocessing and feature engineering** for the Telco Customer Churn dataset. The raw dataset has been transformed into a clean, machine-learning-ready format through systematic cleaning, feature engineering, encoding, and scaling.

**Objective:** Prepare a high-quality dataset for predictive modeling to identify customers at risk of churning.

---

## 📊 Dataset

- **Source:** Telco Customer Churn (Kaggle)
- **Records:** 7,043 customers
- **Original Features:** 21 columns
- **Target Variable:** Churn (Yes/No)
- **Data Quality:** No missing values, no duplicates

### Key Features
- Customer demographics (gender, age, dependents, etc.)
- Service subscriptions (internet, phone, streaming, security, etc.)
- Account information (tenure, contract type, billing method)
- Billing data (monthly charges, total charges)

---

## 🔧 Preprocessing Steps Performed

### Part 1: Data Inspection
- ✅ Loaded and examined dataset structure
- ✅ Identified data types (21 columns, 7,043 rows)
- ✅ Checked for missing values (none found)
- ✅ Checked for duplicates (none found)
- ✅ Generated descriptive statistics

### Part 2: Data Cleaning
- ✅ **Converted TotalCharges** from text to numeric (float64)
- ✅ **Removed customerID** (not predictive)
- ✅ Validated all data types

### Part 3: Feature Engineering
Created 4 new predictive features:

| Feature | Definition | Rationale |
|---------|-----------|-----------|
| **TotalServices** | Count of add-on services (0-6) | Loyalty indicator |
| **ContractMonths** | Contract duration in months (1, 12, 24) | Strong churn predictor |
| **ChargePerMonth** | Total charges ÷ tenure | Identifies spending patterns |
| **TenureGroup** | Categorical tenure grouping (0-1yr, 1-2yr, 2-4yr, 4+yr) | Interpretable tenure bins |

### Part 4: Feature Encoding & Scaling
- **Binary Encoding:** Yes/No → 1/0 for Partner, Dependents, PhoneService, PaperlessBilling, Churn
- **Ordinal Encoding:** No(0), No internet service(1), Yes(2) for service features
- **One-Hot Encoding:** InternetService, Contract, PaymentMethod
- **StandardScaler:** Applied to all numerical features (mean=0, std=1)

### Part 5: Outlier Detection
- **Method:** Interquartile Range (IQR)
- **Decision:** Retained all outliers (represent real customer behavior)

### Part 6: Final Dataset
- ✅ 7,043 rows × 20 features
- ✅ All numeric format (ML-ready)
- ✅ 0 missing values
- ✅ 0 duplicates
- ✅ Scaled and encoded

---

## 📈 Visualizations Created

6 professional visualizations for analysis and reporting:

1. **Histograms** - Distribution of numerical features
2. **Box Plots** - Outlier detection visualization
3. **Churn Distribution** - Count plot of target variable
4. **Correlation Heatmap** - Feature correlations with churn
5. **Scatter Plot** - Tenure vs Total Charges (colored by churn)
6. **Churn by Contract Type** - Churn rates by contract duration

---

## 🔍 Key Findings

- **Contract Length:** Strongly correlated with churn - multi-year contracts reduce churn risk
- **Service Adoption:** Customers with more services show lower churn rates
- **New Customers:** Tenure < 1 year has highest churn risk
- **Data Quality:** Excellent - no missing values or duplicates detected

---

## 💡 Key Recommendations

1. **Encourage service adoption** as a retention strategy
2. **Focus retention efforts** on the first year of service
3. **Promote longer contracts** to reduce churn
4. **Use engineering features** (TotalServices, ContractMonths) in predictive models

---

## 📁 Files in Repository
