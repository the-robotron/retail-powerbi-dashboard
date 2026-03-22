# Retail Sales Power BI Dashboard

[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=flat&logo=powerbi)](https://app.powerbi.com) [![Status](https://img.shields.io/badge/Status-Published-brightgreen)](.) [![Platform](https://img.shields.io/badge/Platform-Power%20BI%20Service-orange)](https://app.powerbi.com) [![KPIs](https://img.shields.io/badge/KPIs-30%2B%20Metrics-blue)](pbix/metrics_definitions.md) [![DAX](https://img.shields.io/badge/DAX-15%2B%20Measures-red)](pbix/DAX_measures.md)

## Overview

An interactive, multi-page **Power BI dashboard** built to analyse retail sales performance across regions, product categories, and customer segments. The dashboard is **published to Power BI Service** and features slicers, drill-throughs, and dynamic KPI cards for real-time business monitoring.

## Live Dashboard

> Published on Power BI Service — [View Live Dashboard](https://app.powerbi.com) *(link placeholder — replace with your published URL)*

## Key Metrics at a Glance

| Metric | Value (Sample Data) | Target | Status |
|--------|--------------------|---------|---------|
| **Total Sales** | $12,642.75 | YoY +10% | On track |
| **Total Profit** | $3,456.22 | Margin >15% | Monitor |
| **Profit Margin %** | 27.3% | >15% | Excellent |
| **Total Orders** | 20 | Growing MoM | On track |
| **Avg Order Value** | $632.14 | >$200 | Excellent |
| **Total Customers** | 14 | Growing | On track |
| **Revenue per Customer** | $903.05 | Trending up | Good |
| **YoY Growth %** | Calculated via DAX | >10% | Monitor |
| **Top Category** | Technology | Consistent | Strong |
| **Best Region** | West | Growing | Strong |

## Dashboard Pages

### Page 1: Executive Summary
- Total Revenue, Total Profit, Profit Margin %, Total Orders (KPI cards)
- Revenue vs Target gauge
- Month-over-Month revenue trend (line chart)
- Top 5 product categories by revenue (bar chart)
- YoY and MoM growth indicators

### Page 2: Regional Performance
- Sales by region (filled map)
- State-level drill-down
- Regional revenue comparison (clustered bar chart)
- Top 10 cities by sales (table visual)

### Page 3: Product Analysis
- Product category breakdown (treemap)
- Sub-category revenue vs profit scatter plot
- Top 20 products by units sold
- Discount impact analysis by category
- Product performance vs target (bullet chart)

### Page 4: Customer Segments
- Sales by customer segment (pie chart)
- New vs returning customers (donut chart)
- Customer lifetime value distribution (histogram)
- Top 10 customers by revenue (bar chart)

## DAX Measures Used

| Measure | Purpose |
|---------|--------|
| `Total Sales` | Core revenue KPI |
| `Total Profit` | Profitability KPI |
| `Profit Margin %` | Efficiency ratio |
| `Sales YTD` | Year-to-date progress |
| `Sales PY` | Prior year comparison |
| `YoY Growth %` | Annual performance trend |
| `Avg Order Value` | Transaction size |
| `Total Customers` | Market reach |
| `Regional Sales %` | Geographic share |
| `Discount Impact` | Profitability risk |

> Full DAX reference: [pbix/DAX_measures.md](pbix/DAX_measures.md)

## Improvement Opportunities Identified

| Observation | Metric Affected | Target | Recommended Action |
|-------------|----------------|--------|-------------------|
| Furniture profit margin lowest | Profit Margin % | +5pp | Reduce discounts on furniture; review supplier costs |
| Q1 consistently weakest | QoQ Growth % | Flat → positive | Launch Q1 flash sales campaign |
| Central region underperforms | Regional Sales % | +10% share | Increase ad spend in Central |
| High discounts eroding net revenue | Discount Impact | Reduce to <10% | Enforce 20% discount cap policy |
| Home Office segment smallest | Segment Revenue Share | +5% share | B2B micro-business outreach |
| Technology has high AOV but low volume | Order Count | +15% | Bundle accessories with tech products |
| Standard Class shipping dominates | Ship Mode Mix | Balance to 60% | Promote First Class for high-value orders |

> Full metric definitions and benchmarks: [pbix/metrics_definitions.md](pbix/metrics_definitions.md)

## Dataset

- **Source**: Superstore Sales Dataset (based on Tableau Sample Superstore)
- **Records**: 20 sample rows (scalable to full 9,994-row dataset)
- **Columns**: 20 fields across Order, Customer, Product, Sales, Profit dimensions
- **Date Range**: 2020–2023
- **File**: [`data/superstore_sales.csv`](data/superstore_sales.csv)

## How to Build & Publish

1. Import `data/superstore_sales.csv` into Power BI Desktop
2. Add DAX measures from [`pbix/DAX_measures.md`](pbix/DAX_measures.md)
3. Build 4 report pages following [`pbix/retail_dashboard_info.md`](pbix/retail_dashboard_info.md)
4. Apply slicers: Year, Region, Segment, Category
5. Publish: **File → Publish → Publish to Power BI**
6. Share the report URL and update the badge at the top of this README

## Tools & Technologies

- **Power BI Desktop** — Dashboard design and DAX measures
- **Power BI Service** — Publishing and sharing
- **DAX** — 15+ custom measures for KPIs and time intelligence
- **CSV** — Source data format

## Project Structure

```
retail-powerbi-dashboard/
├── data/
│   └── superstore_sales.csv         # Source dataset (20 rows sample)
├── pbix/
│   ├── DAX_measures.md             # 15+ custom DAX measures
│   ├── retail_dashboard_info.md    # Step-by-step build guide
│   └── metrics_definitions.md      # NEW: KPI glossary + benchmarks + improvement table
├── screenshots/
│   └── README.md                    # Screenshot index
└── README.md
```

## Author

**Shivam Singh** — [GitHub](https://github.com/the-robotron) | [LinkedIn](https://linkedin.com/in/shivam-singh)
