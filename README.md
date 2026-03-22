# Retail Sales Power BI Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow) ![Status](https://img.shields.io/badge/Status-Published-brightgreen) ![Platform](https://img.shields.io/badge/Platform-Power%20BI%20Service-orange)

## Overview

An interactive, multi-page **Power BI dashboard** built to analyse retail sales performance across regions, product categories, and customer segments. The dashboard is **published to Power BI Service** and features slicers, drill-throughs, and dynamic KPI cards for real-time business monitoring.

## Live Dashboard

> Published on Power BI Service — [View Live Dashboard](https://app.powerbi.com) *(Link placeholder — replace with your published URL)*

## Dashboard Pages

### Page 1: Executive Summary
- Total Revenue, Total Orders, Average Order Value (KPI cards)
- Revenue vs Target gauge
- Month-over-Month revenue trend (line chart)
- Top 5 product categories by revenue (bar chart)

### Page 2: Regional Performance
- Sales by region (filled map)
- State-level drill-down
- Regional revenue comparison (clustered bar chart)
- Top 10 cities by sales (table visual)

### Page 3: Product Analysis
- Product category breakdown (treemap)
- Sub-category revenue vs profit scatter plot
- Top 20 products by units sold
- Product performance vs target (bullet chart)

### Page 4: Customer Segments
- Sales by customer segment (pie chart)
- New vs returning customers (donut chart)
- Customer lifetime value distribution (histogram)
- Segment-wise profit margin analysis

## Key KPIs Tracked

| KPI | Description |
|---|---|
| Total Revenue | Sum of all sales in selected period |
| Revenue Growth % | MoM and YoY revenue growth |
| Profit Margin | Net profit as % of revenue |
| Average Order Value | Revenue / Number of orders |
| Customer Count | Unique customers in period |
| Return Rate | % of returned orders |

## DAX Measures

```dax
-- Total Revenue
Total Revenue = SUM(Orders[Sales])

-- Revenue Growth MoM
Revenue Growth MoM % =
VAR CurrentMonth = [Total Revenue]
VAR PreviousMonth = CALCULATE([Total Revenue], DATEADD('Date'[Date], -1, MONTH))
RETURN DIVIDE(CurrentMonth - PreviousMonth, PreviousMonth, 0)

-- Profit Margin
Profit Margin % = DIVIDE(SUM(Orders[Profit]), SUM(Orders[Sales]), 0)

-- YTD Revenue
YTD Revenue = TOTALYTD([Total Revenue], 'Date'[Date])

-- Running Total
Running Total Revenue =
CALCULATE(
    [Total Revenue],
    FILTER(
        ALL('Date'),
        'Date'[Date] <= MAX('Date'[Date])
    )
)
```

## Data Model

```
Orders (Fact Table)
    ├── order_id, order_date, ship_date
    ├── customer_id (FK)
    ├── product_id (FK)
    ├── sales, quantity, discount, profit

Customers (Dimension)
    ├── customer_id, name, segment, region

Products (Dimension)
    ├── product_id, name, category, sub_category

Date (Dimension - Calendar Table)
    └── date, year, quarter, month, week
```

## Dataset

- **Source**: Superstore Sales Dataset (Kaggle / Tableau Sample)
- **Period**: 2021 – 2024
- **Records**: ~10,000 orders
- **Regions**: East, West, Central, South (USA)

## Features

- **Slicers**: Year, Region, Category, Customer Segment
- **Drill-through**: Click on any region or product to see detail page
- **Tooltips**: Hover over visuals for contextual metrics
- **Bookmarks**: Saved views for executive, regional, and product perspectives
- **Row-level Security (RLS)**: Region-based access control configured
- **Scheduled Refresh**: Data refreshes daily via Power BI Service

## Tools Used

| Tool | Purpose |
|---|---|
| Power BI Desktop | Dashboard design and DAX |
| Power BI Service | Publishing and sharing |
| Power Query (M) | Data transformation and cleaning |
| Excel / CSV | Source data |

## Project Structure

```
retail-powerbi-dashboard/
├── data/
│   └── superstore_sales.csv
├── pbix/
│   └── Retail_Sales_Dashboard.pbix
├── screenshots/
│   ├── executive_summary.png
│   ├── regional_performance.png
│   ├── product_analysis.png
│   └── customer_segments.png
└── README.md
```

## How to Use

1. Download `pbix/Retail_Sales_Dashboard.pbix`
2. Open in **Power BI Desktop** (free download from Microsoft)
3. Update the data source path if needed in Power Query
4. Click **Refresh** to load the data
5. To publish: `Home > Publish > Select your workspace`

## Key Findings

- **Technology** category generates the highest revenue (~36%) but **Office Supplies** drives the most orders
- **West region** leads in revenue; **Central region** has the lowest profit margin
- **Corporate segment** has the highest average order value
- Q4 consistently shows a **30% revenue spike** due to holiday sales
- Discounts above 30% are **negatively correlated** with profit margin

## Author

**Shivam Singh** — [GitHub](https://github.com/the-robotron) | [LinkedIn](https://linkedin.com/in/shivam-singh)
