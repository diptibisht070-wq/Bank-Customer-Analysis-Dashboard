# 🏦 PNB Bank Customer Analysis Dashboard (Power BI)

An interactive Power BI dashboard that analyses a bank's customer base across **balance, demographics, account types, loan behaviour, geography and customer onboarding trends**. It turns raw customer records into a clear picture of who the bank's most valuable customers are and where the balance comes from.

---

## 📌 Project Overview

| | |
|---|---|
| **Tool** | Microsoft Power BI (Power Query, DAX, Data Modelling) |
| **Domain** | Banking / Customer Analytics |
| **Customers analysed** | 249 |
| **Total balance (sum)** | ~13.5M |
| **Period covered** | Jan – Apr 2023 (customer join dates) |
| **Regions** | California, New York, Florida, Texas |

### Business questions answered
- Which customer segments (age, gender, marital status) hold the most balance?
- Which account type contributes most to total deposits?
- Which states have the largest customer share?
- How does loan type vary with marital status?
- When did customer acquisition and balance inflow peak?
- Who is the top customer?

---

## 📊 Dashboard Pages

### Page 1 – Executive Summary
- **KPI cards:** Total Bank Balance, Total Customers (249), Top Customer (Elbert Klein), Most Common Account Type (Business)
- **Balance by Gender** – average balance: Female ~55.3K vs Male ~53.6K
- **Balance % by Account Type** – CA 54.56% (7.38M), SA 23.91% (3.24M), CD 21.54% (2.91M)
- **Balance by Marital Status** – Married 7.7M, Single 4.4M, Divorced 1.5M
- **Customer % by State** – California 73.09% (182), New York 17.27% (43), Florida 6.02% (15), Texas (remainder)
- **Balance by Age Group** – 30–40 leads with 5.9M, then 40–50 (3.4M) and 20–30 (2.7M)
- **State slicer** (California / Florida / New York / Texas) to filter the whole page

### Page 2 – Deep Dive
- **Loan type by marital status (100% stacked)** – house loan, no loan, both loans, other loans
- **Bank balance vs customers joined over time** – dual-axis trend showing onboarding spikes in Feb, Mar and Apr 2023
- **Decomposition Tree** – drill down total balance by Marital Status → Gender → Account Type → Age Group

---

## 🔍 Key Insights

1. **Married customers hold ~57% of total balance** (7.69M of 13.53M), making them the most valuable segment.
2. **Age 30–40 is the sweet spot**, contributing roughly 44% of total balance; customers under 20 and over 60 are almost negligible (0.2M each).
3. **Current accounts (CA) dominate deposits** with over half of the total balance.
4. **California accounts for 73% of customers**, so the bank is heavily concentrated in one state; Texas and Florida are under-penetrated.
5. **Female customers have a slightly higher average balance** than male customers, although the difference is small (~1.7K).
6. **Married customers are the majority in every loan category** (55–65%), and the share is highest for "other loan" (64.97%).
7. **Customer acquisition is spiky, not steady.** The largest single-day spike (~36 customers) also produced the highest balance inflow (~2.2M), suggesting campaign- or event-driven onboarding.
8. In the decomposition tree, the strongest path is **Married → Male → CA → age 30–40 (~1.26M)**.

---

## 💡 Recommendations
- Run targeted savings/investment products for **married customers aged 30–40**.
- Launch acquisition campaigns in **Texas, Florida and New York** to reduce dependence on California.
- Cross-sell **SA / CD products** to CA-heavy customers to diversify deposits.
- Replicate the campaigns behind the Feb/Mar/Apr onboarding spikes.
- Build youth (10–30) and senior (60+) offerings, as both segments are under-represented.

---

## 🛠️ Technical Details

- **Data cleaning (Power Query):** handled nulls, fixed data types, created `age_group` bins and `balance_roundup`
- **Data modelling:** customer table with date, account and loan attributes
- **DAX measures (examples):**
  ```DAX
  Total Balance = SUM(Customers[balance_roundup])
  Total Customers = DISTINCTCOUNT(Customers[Customer ID])
  Avg Balance = AVERAGE(Customers[balance_roundup])
  ```
- **Visuals used:** KPI cards, slicer, pie, donut, bar/column, 100% stacked chart, dual-axis area/line chart, decomposition tree

---

## 📁 Repository Structure

```
├── PNB_Bank_Dashboard.pbix     # Power BI report file
├── bank_dashboard.pdf          # Exported dashboard (PDF)
├── data/
│   └── bank_customers.csv      # Dataset 
└── README.md
```

## 📈 Skills Demonstrated
Data cleaning · Data modelling · DAX · KPI design · Dashboard storytelling · Customer segmentation · Business insight generation

---

## 👤 Author
**<diptibisht070-wq>**
[LinkedIn](https://linkedin.com/in/your-profile) · [GitHub](https://github.com/your-username)

> ⭐ If you found this project useful, consider giving it a star!
