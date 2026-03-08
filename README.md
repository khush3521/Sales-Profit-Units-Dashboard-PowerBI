# 📊 Sales, Profit & Units Performance Dashboard — Power BI

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-005C84?style=for-the-badge)
![Power Query](https://img.shields.io/badge/Power%20Query-217346?style=for-the-badge&logo=microsoft&logoColor=white)
![Status](https://img.shields.io/badge/Project-Completed-success?style=for-the-badge)

> 💰 $118.73M revenue analyzed | 📦 1M+ units sold | 🌍 Multi-country global dataset | 📉 Profit, loss & margin deep dive

---

## 📊 End-to-End Analytics Pipeline

```
Raw Financial Data → Power Query (Cleaning & Transformation) 
→ Data Modeling → DAX (Sales, Profit, Units KPIs) → 3-Page Power BI Dashboard → Business Insights
```

---

## 📌 Project Overview

A global business generating $118M+ in revenue across 6 products, multiple countries, and 5 customer segments — but not all of that revenue was profitable. The **Enterprise segment was losing money**, discount spend was eating $9.2M in margin, and profit concentration was hiding in just a few products.

This project builds a **3-dashboard Power BI solution** to surface exactly where revenue, profit, and volume are being won or lost — giving business leaders the clarity to act.

---

## 🎯 Business Objectives

1. **Where is revenue coming from — and which segments are most valuable?**
2. **Which products and segments are profitable vs loss-making?**
3. **Are discounts helping sales or destroying margins?**
4. **Where are the seasonal peaks in sales and volume?**

---

## 📷 Dashboard Previews

### 📌 Dashboard 1 — Sales Overview
[![Sales Dashboard](Screenshot%202025-11-27%20222756.png)](https://github.com/khush3521/Sales-Profit-Units-Dashboard-PowerBI/blob/main/Screenshot%202025-11-27%20222756.png)

### 📌 Dashboard 2 — Profit Analysis
[![Profit Dashboard](Screenshot%202025-11-27%20222812.png)](https://github.com/khush3521/Sales-Profit-Units-Dashboard-PowerBI/blob/main/Screenshot%202025-11-27%20222812.png)

### 📌 Dashboard 3 — Units Sold Analysis
[![Units Dashboard](Screenshot%202025-11-27%20222823.png)](https://github.com/khush3521/Sales-Profit-Units-Dashboard-PowerBI/blob/main/Screenshot%202025-11-27%20222823.png)

---

## 📈 Key Insights & Business Impact

| Finding | Business Implication |
|---|---|
| **Government segment: $53M sales, $11.4M profit** | Highest-value segment — protect and grow this relationship |
| **Enterprise segment: -$0.6M loss** | Pricing or discount strategy needs urgent review |
| **$9.21M discounts given vs $16.89M total profit** | Discounts equal 54% of profit — significant margin risk |
| **Paseo: $33M sales, $4.8M profit — top product** | Double down on Paseo in top markets |
| **October peak: $21.7M sales vs June low: $5.6M** | 4x seasonal swing — inventory and campaign planning critical |
| **Canada leads units sold (0.25M), France close behind** | North America + France are core markets for volume |
| **Enterprise & Midmarket drag profit via waterfall** | Segment-level pricing tiers needed to protect overall margin |

---

## 📊 Dashboard Structure

### 🔹 Dashboard 1 — Sales Overview
Revenue performance for sales leadership:
- **Total Sales: $118.73M** | Gross Sales: $127.93M | Discounts: $9.21M
- Monthly sales trend — peak in **October ($21.7M)**, trough in **June ($5.6M)**
- Sales by segment — **Government ($53M) leads, Small Business ($42M) second**
- Top product: **Paseo at $33M**
- Country breakdown — USA, Canada, Germany, France strongest

### 🔹 Dashboard 2 — Profit Analysis
Margin and profitability for finance teams:
- **Total Profit: $16.89M | Profit Margin: 14%**
- Profit trend — peaks **October ($3.4M)**, dips **March–April (below $1M)**
- Most profitable: **Government segment ($11.4M profit)**
- Loss segment: **Enterprise (-$0.6M)**
- Waterfall chart — profit increases from Government & Small Business, decreases from Enterprise & Midmarket
- Country profitability leaders: **Canada, France, USA**

### 🔹 Dashboard 3 — Units Sold Analysis
Volume tracking for operations and supply chain:
- **Total Units Sold: 1,000,000+ | Avg per Transaction: 1.61K**
- 6 unique products in portfolio
- Volume peak: **October (0.20M units)**
- Top segment by volume: **Government (0.47M units)**
- Top country: **Canada (0.25M)**, France (0.24M)
- Top product by volume: **Paseo**, followed by Vtt

---

## 🧠 DAX Measures

```DAX
-- Core Sales KPIs
Total Sales      = SUM(financials[Sales])
Gross Sales      = SUM(financials[Gross Sales])
Total Discounts  = SUM(financials[Discounts])
Net Revenue      = [Gross Sales] - [Total Discounts]

-- Profit Measures
Total Profit     = SUM(financials[Profit])
Profit Margin %  = DIVIDE([Total Profit], [Total Sales])
Total COGS       = SUM(financials[COGS])

-- Units
Total Units Sold = SUM(financials[Units Sold])
Avg Units per Transaction =
    DIVIDE([Total Units Sold], COUNTROWS(financials))

-- Discount Impact
Discount Rate % =
    DIVIDE([Total Discounts], [Gross Sales])

-- Segment Profitability Flag
Segment Status =
IF(
    CALCULATE([Total Profit], ALLEXCEPT(financials, financials[Segment])) < 0,
    "Loss ⚠️",
    "Profitable ✅"
)

-- Monthly Sales Rank
Monthly Sales Rank =
RANKX(
    ALL(financials[Month Name]),
    [Total Sales],
    ,
    DESC,
    DENSE
)

-- Top Product
Top Product =
CALCULATE(
    FIRSTNONBLANK(financials[Product], 1),
    TOPN(1, VALUES(financials[Product]), [Total Sales], DESC)
)

-- Profit by Status (for waterfall)
Profit Increase =
CALCULATE([Total Profit], financials[Status] = "Profit")

Profit Decrease =
CALCULATE([Total Profit], financials[Status] = "Loss")
```

---

## 🛠 Tools & Technologies

| Tool | Purpose |
|------|---------|
| Power BI Desktop | 3-page interactive dashboard |
| DAX | Sales, profit, margin, units & segment KPIs |
| Power Query | Data cleaning, status column engineering, date fields |
| Global Financial Dataset | Multi-country, multi-segment raw data |

---

## 📂 Dataset Attributes

| Column | Description |
|---|---|
| Segment | Customer segment (Government, Small Business, Enterprise, etc.) |
| Country | Country of sale |
| Product | One of 6 products (Paseo, Vtt, etc.) |
| Units Sold | Volume of units per transaction |
| Sale Price | Price per unit |
| Gross Sales | Revenue before discounts |
| Discounts | Discount amount applied |
| Sales | Net sales (Gross - Discounts) |
| COGS | Cost of goods sold |
| Profit | Net profit per transaction |
| Date / Year / Month | Time dimension |
| Status | Engineered field: Profit / Break-even / Loss |

---

## 📂 Repository Structure

```
Sales-Profit-Units-Dashboard-PowerBI/
│
├── data/
│   └── financials.csv
│
├── powerbi/
│   └── Sales_Profit_Units_Dashboard.pbix
│
├── Screenshot 2025-11-27 222756.png     ← Dashboard 1: Sales
├── Screenshot 2025-11-27 222812.png     ← Dashboard 2: Profit
├── Screenshot 2025-11-27 222823.png     ← Dashboard 3: Units
└── README.md
```

---

## 🔮 Future Improvements

- Add **price elasticity analysis** — how discount rate affects units sold
- Build **country-level drill-through pages** for market-specific reporting
- Add **What-If parameter** — simulate profit impact of reducing discounts by 10–20%
- Integrate **Python margin optimization model** — suggest ideal discount thresholds per segment
- Publish to **Power BI Service** for live financial reporting

---

## 👨‍💻 Author

**Khush Panchal** — Data Analyst
Specializing in financial analytics, business performance & data storytelling

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/khush-panchal-96b557352)
[![GitHub](https://img.shields.io/badge/GitHub-Portfolio-black?style=flat&logo=github)](https://github.com/khush3521)

---

⭐ If you found this project valuable, please consider starring this repository!
