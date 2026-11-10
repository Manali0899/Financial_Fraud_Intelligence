# 🔐 FraudScope – Financial Fraud Intelligence Dashboard

**An Interactive Power BI Dashboard for Financial Fraud Detection, Risk Analysis, and Transaction Intelligence**

FraudScope is an end-to-end financial fraud analytics project built using **Microsoft Power BI**. It transforms transactional data into actionable insights through interactive dashboards, advanced visualizations, and KPI-driven analysis.

The dashboard helps financial institutions, fraud analysts, and business stakeholders identify suspicious transaction patterns, monitor fraud trends, investigate high-risk accounts, and understand potential vulnerabilities across payment methods, time periods, and geographical regions.

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Project Objectives](#-project-objectives)
- [Technology Stack](#-technology-stack)
- [Dataset Overview](#-dataset-overview)
- [Dashboard Features](#-dashboard-features)
  - [Dashboard Overview](#1-dashboard-overview)
  - [Fraud Decomposition Analysis](#2-fraud-decomposition-analysis)
  - [Customer Analysis](#3-customer-analysis)
  - [Device-Based Alerts](#4-device-based-alerts)
  - [Payment Method Trends](#5-payment-method-trends)
  - [Account Type Analysis](#6-account-type-analysis)
- [Key Business Insights](#-key-business-insights)
- [Getting Started](#-getting-started)
- [Repository Structure](#-repository-structure)
- [Future Enhancements](#-future-enhancements)

---

## 🎯 Project Overview

Financial fraud is a growing challenge for banks and financial institutions. Identifying suspicious transactions requires analyzing large volumes of financial data and recognizing patterns that may indicate fraudulent behavior.

**FraudScope** addresses this challenge by providing an interactive analytical environment that explores:

- Transaction-level fraud patterns.
- Financial exposure and transaction amounts at risk.
- Customer behavior and unusual login activity.
- Fraud distribution across geographical locations.
- Payment method vulnerabilities.
- Time-based and account-specific fraud trends.

The dashboard combines data transformation, DAX calculations, and interactive Power BI visualizations to make complex financial data easier to understand and investigate.

## 🚀 Project Objectives

The primary objectives of FraudScope are to:

1. **Detect Fraud Patterns:** Identify suspicious transactions based on transaction status, payment methods, account types, and transaction timing.
2. **Analyze Financial Risk:** Evaluate fraudulent transaction amounts and understand potential financial exposure.
3. **Understand Customer Behavior:** Examine unusual login activity and transaction-level anomalies.
4. **Identify Geographical Risks:** Visualize fraud distribution across countries and branches.
5. **Monitor Temporal Trends:** Identify days and times associated with increased fraudulent activity.
6. **Support Decision-Making:** Provide interactive insights that help analysts investigate suspicious activity and prioritize potential risks.

## 🛠 Technology Stack

| Technology | Purpose |
|---|---|
| Microsoft Power BI Desktop | Dashboard development and data visualization |
| Power Query | Data cleaning, transformation, and preprocessing |
| DAX | KPI calculations, measures, and time-based analysis |
| Decomposition Tree | Multi-dimensional fraud investigation |
| Donut Charts & KPI Cards | Financial metrics and fraud distribution |
| Heatmaps | Temporal fraud pattern analysis |
| Line Charts | Transaction and fraud trends |
| Treemaps | Category-level fraud analysis |
| Bing Maps | Geographical fraud visualization |
| Drillthrough & Interactive Filters | Detailed transaction investigation |

## 📂 Dataset Overview

The project uses financial transaction data containing customer, transaction, account, and fraud-related attributes.

| Field | Description |
|---|---|
| Customer ID | Unique customer or transaction identifier |
| Transaction Amt | Monetary value of the transaction |
| Account Type | Savings or Current account |
| isFraud | Binary indicator identifying fraudulent transactions |
| UnusualLogin | Number of login events triggering suspicious activity alerts |
| Method | Transaction method (CASH_IN, CASH_OUT, PAYMENT, DEBIT, TRANSFER) |
| Time of Day | Transaction time categorized as Morning, Afternoon, or Night |
| Day of Week | Day on which the transaction occurred |
| Country / Branch | Geographical origin of the transaction |

*Note: The dataset's exact field definitions and granularity should be considered when interpreting individual metrics.*

---

## 📊 Dashboard Features

FraudScope consists of six interactive dashboard pages, each designed to investigate a different dimension of financial fraud.

### 1. Dashboard Overview

**File:** `dashboard.png`

Provides a high-level summary of transaction activity, fraud distribution, and financial exposure.

**Key Visualizations:**

- **Transaction Status Distribution:** Donut chart displaying 10,122 transactions categorized as Fraud, Safe, and Not Reviewed.
- **Average Transaction Amount at Risk:** Compares fraudulent transactions ($0.533M) against safe transactions ($0.102M).
- **Fraud by Time of Day:** Highlights fraud distribution across Morning, Afternoon, and Night.
- **Transaction Trend Analysis:** Tracks daily transaction values and identifies significant changes in fraudulent activity.
- **Geographical Fraud Heatmap:** Uses map visualizations to identify countries with higher reported fraud activity.

**Key Observation:**

January 6 recorded the highest reported fraudulent transaction value, reaching approximately **$16.3M**.

### 2. Fraud Decomposition Analysis

**File:** `fraud_tree.png`

Provides a deeper understanding of fraudulent transactions through multi-dimensional analysis.

**Key Visualizations:**

- **Decomposition Tree:** Breaks down fraud by Status → Country → Account Type → Method → Time of Day → Day of Week.
- **Weekly Fraud Trends:** Compares fraud patterns across Savings and Current accounts.
- **Time-Based Heatmap:** Identifies combinations of weekdays and transaction periods associated with higher fraud counts.

**Notable Patterns:**

- Estados Unidos → Savings → PAYMENT → Morning → Friday.
- Francia → Current → CASH_OUT → Night.
- Friday Afternoon recorded 13 fraudulent transactions.
- Sunday Night recorded 8 fraudulent transactions.
- Saturday Morning recorded 7 fraudulent transactions.

**Business Value:** Helps fraud analysts investigate combinations of attributes that contribute to suspicious transaction patterns.

### 3. Customer Analysis

**File:** `customers.png`

Provides transaction-level visibility to support customer profiling and fraud investigation.

**Key Data Points:**

- Customer ID
- Account Type
- Transaction Date
- Transaction Amount
- Previous and New Account Balances
- Destination Account IDs
- Fraud Indicator (`isFraud`)
- Unusual Login Indicator

**Key Observations:**

- Fraud-flagged transactions show potential imbalances in debit and credit behavior.
- Customers with unusual login activity can be investigated alongside transaction-level fraud indicators.
- Transaction-level details support auditing and anomaly investigation.

**Dataset Summary:**

| Metric | Value |
|---|---:|
| Total Transaction Amount | $1.06B |
| Total Fraud Count | 68 |
| Verified Safe Transactions | 10,057 |

**Business Value:** Supports customer-level investigation, transaction auditing, and suspicious activity analysis.

### 4. Device-Based Alerts

**File:** `device.png`

Examines fraud activity using device-related and behavioral alert indicators.

**Key Visualization:**

- Line chart tracking fraudulent transactions across days of the week.

**Key Observation:**

- Saturday recorded a peak of 13 fraudulent transactions.
- Tuesdays and Wednesdays showed relatively lower fraud activity.

**Business Value:**

Helps identify potential behavioral patterns and provides a foundation for investigating unusual device or access activity.

### 5. Payment Method Trends

**File:** `methods.png`

Analyzes fraudulent transaction activity across different payment methods.

**Payment Methods Covered:**

| Method | Description |
|---|---|
| CASH_IN | Cash deposit transactions |
| CASH_OUT | Cash withdrawal transactions |
| PAYMENT | Payment transactions |
| DEBIT | Debit transactions |
| TRANSFER | Account transfer transactions |

**Key Visualizations:**

- Transaction volume by payment method.
- Fraud trends across transaction dates.
- Interactive filtering by account holder and transaction status.

**Key Observations:**

- PAYMENT and CASH_OUT are among the most frequently observed fraud-linked methods.
- Repeated transaction spikes across multiple dates may indicate patterns worth investigating.

**Business Value:** Helps identify payment channels requiring additional monitoring and investigation.

### 6. Account Type Analysis

**File:** `accounts.png`

Examines financial exposure and suspicious activity across Savings and Current accounts.

**Fraudulent Transaction Amount:**

| Account Type | Fraudulent Amount | Share |
|---|---:|---:|
| Current | $24.09M | 66.4% |
| Savings | $12.19M | 33.6% |

**Safe Transaction Amount:**

| Account Type | Safe Transaction Amount |
|---|---:|
| Current | $732.03M |
| Savings | $329.47M |

**Key Visualizations:**

- Donut charts comparing fraudulent and safe transaction amounts.
- Average unusual login analysis by transaction status.
- Treemap showing fraud distribution by time of day.

**Key Observations:**

- Current accounts account for approximately 66.4% of the reported fraudulent transaction amount.
- Fraudulent transactions show an average unusual login metric of approximately 4.5.
- Safe transactions show an average of approximately 10 unusual logins.

**Business Value:** Helps analysts compare account-level financial exposure and investigate whether login alerts provide useful context for fraud detection.

---

## 💡 Key Business Insights

The dashboard highlights several patterns that can support further fraud investigation.

| Category | Key Finding |
|---|---|
| Peak Fraud Date | January 6 – approximately $16.3M |
| High-Risk Account Type | Current accounts – 66.4% of fraudulent transaction value |
| High-Fraud Periods | Afternoon and Night |
| Geographical Patterns | USA, France, and Mexico |
| Frequently Observed Methods | PAYMENT and CASH_OUT |
| Peak Fraud Day | Saturday – 13 reported fraudulent transactions |
| Total Fraud Count | 68 |

### Business Recommendations

Based on the observed patterns, financial institutions could consider:

- Prioritizing investigations involving high-value suspicious transactions.
- Strengthening monitoring of PAYMENT and CASH_OUT transactions.
- Reviewing unusual transaction activity during afternoon and nighttime periods.
- Conducting additional risk assessments for Current accounts.
- Combining unusual login indicators with transaction behavior rather than treating login alerts as standalone fraud evidence.
- Monitoring geographical patterns and investigating unusual transaction concentrations.

*These findings represent patterns in the analyzed dataset and should not be interpreted as proof of causation or as a production-ready
