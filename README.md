# 💳 FinInsight — Banking Analytics Dashboard

<div align="center">

**Turning $307M+ in raw transaction data into decisions banks can act on.**
*An end-to-end Power BI platform covering transactions, credit risk, customer behavior, and branch performance.*

<br>

[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://app.powerbi.com/view?r=eyJrIjoiOTQ5Y2UyY2UtNWM2NC00NGYyLTllNWUtYmU1ZDhkM2YwYzg5IiwidCI6IjdlMzEwODQ1LTg0ZTEtNGRiOC1hZjk4LTcwNDA0MTkwZDhkZSJ9)
[![DAX](https://img.shields.io/badge/DAX-Measures%20%26%20KPIs-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)](https://github.com/ajaya-kumar-pradhan)
[![SQL](https://img.shields.io/badge/SQL-Data%20Modeling-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)](https://github.com/ajaya-kumar-pradhan)
[![Python](https://img.shields.io/badge/Python-Data%20Prep-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://github.com/ajaya-kumar-pradhan)

<br>

### 🚀 [View Live Power BI Dashboard →](https://app.powerbi.com/view?r=eyJrIjoiOTQ5Y2UyY2UtNWM2NC00NGYyLTllNWUtYmU1ZDhkM2YwYzg5IiwidCI6IjdlMzEwODQ1LTg0ZTEtNGRiOC1hZjk4LTcwNDA0MTkwZDhkZSJ9)

</div>

---

## 📌 Overview

**FinInsight** is a multi-page banking analytics platform built to mirror how financial institutions actually monitor and manage performance.

The dashboard consolidates 100K+ transactions across 600 branches into a unified view — covering everything from daily cash flow trends to individual credit risk flags. It's designed for analysts, risk officers, and branch managers who need fast answers without touching a spreadsheet.

> **The Business Problem:** Banks generate enormous transaction and account data daily, but most of it sits fragmented across systems. Risk goes undetected, branch performance gaps are invisible, and customer churn is only noticed after the fact.
>
> **The Solution:** A single Power BI platform that surfaces the right financial signals — from macro cash flow to flagged high-risk accounts — in real time.

---

## 📊 Key Features

- 💸 **Transaction intelligence** — Analyze $307M+ in volume by type, time-of-day, day-of-week, and branch with full drill-down capability
- ⚠️ **Credit risk monitoring** — Identify and isolate 162 risk-flagged accounts (1.4%) by credit score band and loan stress level
- 🏦 **Branch performance benchmarking** — Rank and compare all 600 branches on transaction volume, account activity, and revenue contribution
- 👥 **Customer segmentation** — Profile customers by account type, industry sector, balance tier, and loyalty status
- 📅 **Time-series trend analysis** — Track MoM and YoY shifts in transaction volume, net cash flow, and account growth
- 🔁 **Cross-filtered navigation** — Every visual interacts with every other — no page refreshes, no dead ends
- 📐 **Star Schema data model** — Built on 2 fact tables and 4 dimension tables for fast, accurate aggregation at any grain

---

## 🛠️ Tech Stack

| Layer | Tool / Technology |
|---|---|
| **BI & Visualization** | Power BI Desktop + Power BI Service |
| **Data Modeling** | Star Schema — 2 Facts, 4 Dimensions |
| **Calculations** | DAX (KPIs, time intelligence, risk flags) |
| **Data Transformation** | Power Query (M Language) |
| **Data Source & Prep** | SQL Server, Python, Excel |
| **Deployment** | Power BI Service (Published Live) |

---

## 📈 Key Metrics & Scale

| Metric | Value |
|---|---|
| 💳 Total Transactions | **100,000+** |
| 💵 Total Transaction Volume | **$307M+** |
| 📊 Avg Transaction Value | **$3,249** |
| 🏦 Total Branches | **600** |
| 👤 Total Accounts | **12,000+** |
| 💰 Avg Account Balance | **$17,235** |
| 🔁 Net Cash Flow | **+$16.8M** |
| ⚠️ Risk-Flagged Accounts | **162 (1.4%)** |
| 📉 Avg Credit Score | **692** |
| 🥇 Top Performing Branch | **BR-0532** |

---

## 🧠 Insights & Business Value

**What the analysis revealed:**

- 📤 **Withdrawal-heavy behavior** — Withdrawals dominate the transaction type mix, indicating potential cash reserve management issues at the branch level
- ⏰ **Peak transaction windows** — Morning and afternoon slots drive the majority of daily volume; staffing and system load should align accordingly
- 💼 **Sector concentration** — Tech and Finance customers account for a disproportionate share of account balances, creating both opportunity and sector risk
- ⚠️ **Loan stress clustering** — High-risk accounts cluster in the lowest credit score bands, enabling early, targeted intervention before defaults occur
- 📉 **YoY transaction decline** — Despite strong absolute volume, a year-over-year decline signals a retention or acquisition issue that needs attention before it compounds
- 🏆 **Branch performance gap** — Wide dispersion between top and bottom branches points to a replicable model from high performers that can lift the rest

**Business value delivered:**
> Risk teams can prioritize outreach to the 162 flagged accounts. Branch managers can benchmark against top performers. Executive leadership can monitor net cash flow and customer trends — all without waiting for a weekly report.

---

## 🖼️ Dashboard Preview

### 1️⃣ Executive Overview
*Total Volume · Net Cash Flow · KPI Cards · Transaction Trend (MoM/YoY) · Account Distribution*

![Executive Overview](Screenshots/overview.png)

---

### 2️⃣ Transaction Analysis
*Volume by Type (Deposit / Withdrawal / Transfer / Payment) · Time-of-Day Heatmap · Weekday vs Weekend Pattern*

![Transaction Analysis](Screenshots/transactions.png)

---

### 3️⃣ Credit Risk & Loan Stress
*Risk-Flagged Accounts · Credit Score Distribution · Loan Stress by Segment · High-Risk Account Drill-Through*

![Credit Risk Dashboard](Screenshots/credit_risk.png)

---

### 4️⃣ Branch Performance
*600 Branch Ranking · Top & Bottom Performers · Branch-Level Volume & Account Count · Geographic Spread*

![Branch Performance](Screenshots/branch_performance.png)

---

### 5️⃣ Customer Insights
*Account Type Mix · Sector Distribution · Balance by Segment · Customer Loyalty Analysis*

![Customer Insights](Screenshots/customer_insights.png)

---

## 🏗️ Data Architecture

**Star Schema Design:**

```
                    dim_date
                       │
dim_customers ── fact_transactions ── dim_branches
                       │
               fact_loans ── dim_accounts
```

```sql
-- Fact Tables
fact_transactions  → transaction_id, account_id, branch_id, date_id,
                     type, amount, currency

fact_loans         → loan_id, customer_id, date_id,
                     loan_amount, interest_rate, risk_flag

-- Dimension Tables
dim_customers  → customer_id, name, sector, credit_score, loyalty_status
dim_accounts   → account_id, customer_id, account_type, balance
dim_branches   → branch_id, branch_code, region
dim_date       → date_id, full_date, month, quarter, year
```

---

## 💡 Sample DAX — Core Measures

```dax
-- Volume & Flow
Total Volume = SUM(fact_transactions[amount])

Net Cash Flow =
    CALCULATE([Total Volume], fact_transactions[type] = "Deposit") -
    CALCULATE([Total Volume], fact_transactions[type] = "Withdrawal")

-- Risk Intelligence
Risk Flagged Rate =
DIVIDE(
    CALCULATE(COUNTROWS(fact_loans), fact_loans[risk_flag] = 1),
    COUNTROWS(fact_loans)
)

Avg Credit Score = AVERAGE(dim_customers[credit_score])

-- Time Intelligence
MoM Volume Change =
VAR PrevMonth = CALCULATE([Total Volume], DATEADD(dim_date[full_date], -1, MONTH))
RETURN DIVIDE([Total Volume] - PrevMonth, PrevMonth)

YoY Volume Change =
VAR PrevYear = CALCULATE([Total Volume], SAMEPERIODLASTYEAR(dim_date[full_date]))
RETURN DIVIDE([Total Volume] - PrevYear, PrevYear)
```

---

## 📂 Project Structure

```
FinInsight-Banking-Analytics/
│
├── 📁 Data/                   # Source datasets (SQL exports / CSV)
│
├── 📁 Screenshots/            # Dashboard preview images
│   ├── overview.png
│   ├── transactions.png
│   ├── credit_risk.png
│   ├── branch_performance.png
│   └── customer_insights.png
│
├── 📁 PowerBI_File/           # .pbix source file
│
└── 📄 README.md
```

---

## 🔭 Roadmap & Future Enhancements

- [ ] 🔴 **Real-time data pipeline** — Connect live transaction feeds via SQL Server streaming
- [ ] 🤖 **ML-based risk scoring** — Integrate Python model to predict default probability per account
- [ ] 🔍 **Fraud detection layer** — Flag anomalous transaction patterns using statistical thresholds
- [ ] 👥 **Customer churn model** — Predict at-risk customers before they close accounts

---

## 👤 About Me

**Ajaya Kumar Pradhan** — Data Analyst | Power BI Developer

I build analytics solutions that make complex financial data fast to understand and easy to act on. My focus is on clean data modeling, performance-tuned DAX, and dashboards that tell a clear business story.

**Core Skills:** `Power BI` `DAX` `SQL` `Python` `Star Schema` `Power Query` `Data Modeling` `Risk Analytics`

<br>

📧 [ajayapradhan.connect@gmail.com](mailto:ajayapradhan.connect@gmail.com)
🔗 [linkedin.com/in/ajayakumarpradhan](https://www.linkedin.com/in/ajayakumarpradhan/)
💻 [github.com/ajaya-kumar-pradhan](https://github.com/ajaya-kumar-pradhan)

---

<div align="center">

*If this project helped or inspired you, consider giving it a ⭐ — it helps others find it too.*

</div>
